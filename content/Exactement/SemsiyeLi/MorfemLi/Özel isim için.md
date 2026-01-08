Özel isim köklerinde (Özel_İsim_Kökü) %0 başarı almanız, modelin bu kategoriyi tamamen "İsim_Kökü" içinde eritmesinden kaynaklanıyor. Model, "Ankara" ile "araba" arasındaki kategorik farkı (biri özel, biri cins) ayırt edecek bir sinyal alamıyor.

Özel isimleri modele öğretmek için şu **4 aşamalı stratejiyi** uygulamalısınız:

### 1. Veri Artırımı (Synthetic Data Augmentation)
267 örnek, 37.000 genel isim kökü karşısında "istatistiksel gürültü" gibi kalır. Bu sayıyı en az **5.000 - 10.000** bandına çekmelisiniz.
*   **Sözlük Kullanımı:** Türkiye yer adları, kişi adları, ülke ve kurum adlarından oluşan bir liste oluşturun.
*   **Şablon Cümleler:** Bu isimleri çeşitli eklerle (kesme işaretli ve işaretiz) cümlelere yerleştirin:
    *   "[Özel İsim]'e gittim."
    *   "[Özel İsim] dün açıklama yaptı."
    *   "[Özel İsim]'li sporcular kazandı."
*   **BIO Etiketleme:** Bu otomatik üretilen veriyi kusursuz şekilde `B-Özel_İsim_Kökü` olarak etiketleyin.

### 2. "Kesme İşareti" ve "Büyük Harf" Sinyalini Güçlendirmek
Türkçe'de özel isimlerin en büyük ayırt edicisi **Kesme İşareti (')** ve **Büyük Harf**tir. Modeliniz bunları görmezden geliyor olabilir.

*   **Cased Model Kullanımı:** Eğer "uncased" (küçük harfe çevrilmiş) bir model veya tokenizer kullanıyorsanız, özel isimleri asla ayırt edemezsiniz. Mutlaka **Cased** (büyük/küçük duyarlı) model kullanmalısınız.
*   **Apostrof (Kesme İşareti) Odağı:** Modelin kesme işaretinden önceki kısmın "Özel İsim" olduğunu anlaması için veri setinde apostrof içeren örneklerin oranını artırın. 
    *   *Örnek:* "İstanbul'da" kelimesinde model; `'` işaretini gördüğünde sol tarafın `Özel_İsim_Kökü` olma ihtimalini %99 olarak hesaplamalı.

### 3. Kayıp Fonksiyonu Ağırlıklandırma (Weighted Cross-Entropy)
Model, özel isimleri yanlış bildiğinde (yani onlara normal isim dediğinde) canı çok yanmalı.
*   Eğitim sırasında `Özel_İsim_Kökü` sınıfına diğer sınıflardan daha yüksek bir **ceza ağırlığı (weight)** verin.
*   Örneğin: Normal bir etiketi yanlış bilmenin cezası `1.0` ise, özel ismi yanlış bilmenin cezası `10.0` olsun. Bu, modelin "Ben bu azınlık grubu görmezden gelemem" demesini sağlar.

### 4. Expert LoRA Adaptörü ile "Özel İsim Dedektörü"
Daha önce konuştuğumuz LoRA yaklaşımını burada uygulayabilirsiniz:

*   **Sadece Özel İsimlere Odaklanmış Eğitim:** Genel modelin ağırlıklarını dondurun. Sadece içinde özel isim geçen ve geçmeyen dengeli bir veri kümesiyle (örn: 5.000 özel isimli, 5.000 normal isimli cümle) bir LoRA eğitin.
*   **Negatif Örnekler:** Cümle başındaki kelimeler de büyük harfle başlar ama özel isim değildir. LoRA'ya cümle başındaki "Kitap masada duruyor" örneğini verip "Kitap" kelimesinin `İsim_Kökü` olduğunu, "Ahmet masada oturuyor" örneğindeki "Ahmet"in `Özel_İsim_Kökü` olduğunu özellikle öğretin.

### Teknik Uygulama Önerisi (Feature Injection)
Eğer model mimarisine müdahale edebiliyorsanız, her token için ek bir "feature" (özellik) ekleyin:
1.  **is_capitalized:** Token büyük harfle mi başlıyor? (0 veya 1)
2.  **contains_apostrophe:** Token içinde kesme işareti var mı? (0 veya 1)
3.  **is_sentence_start:** Cümlenin ilk kelimesi mi? (0 veya 1)

Bu basit 3 sinyal, `Özel_İsim_Kökü` başarısını %0'dan %90'lara bir günde çıkarabilir.

**Özetle:** Modelin şu anki sorunu "görememek". Ona büyük harfi, kesme işaretini ve bolca özel isim örneğini bir arada sunan, bu etikete özel ağırlık veren bir LoRA eğitimi verirseniz bu sorunu çözersiniz.