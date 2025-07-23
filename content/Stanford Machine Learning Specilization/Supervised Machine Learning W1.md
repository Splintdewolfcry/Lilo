- Machine Learning muhabbetleri adamın checkers öğrenmek istemesiyle başlıyor,
	- Algoritma kendine karşı binlerce oyun atarak öğreniyor

- ![[Pasted image 20250713233147.png]] x ve y mantığı
	- matematikteki fonksiyonlarda da bunu öğreniyorduk

![[Pasted image 20250713233412.png]] Supervised learning mantığı cevabı vermekte yatıyor, doğru cevabı söylüyorsun bundan bir infer datası elde ediyor

- ![[Pasted image 20250713233607.png]]
- Classification ın artısı daha limitli bir sonucu tahmin etmeye çalışıyorsun, 0 veya 1 var

- ![[Pasted image 20250713234344.png]]
- Clustering, panda örneği

![[Pasted image 20250714000022.png]]
- Şu soktuğumun notasyon mantığını oturup kendim anlayamadım ya düzgün BAU'dayken
	- oof of

![[Pasted image 20250714000257.png]]
[[x]] = [[input]] or [[feature]]
[[ŷ]] = [[prediction]] or [[estimate]] that the function outputs
[[y]] = [[value]] or [[target]]
[[f]] = [[function]] or [[hypotheses]]

![[Pasted image 20250714001706.png]]
- f içerisindeki w ve b parametlerini kullanarak grafiğin eğrisini ve constantını belirliyoruz
	- Buna bi bakış açısı olarak sallıyorum housing prices mantığında metrekare başına sabit genelde 1.5k ekliyoruz(Sivas için), x'in eğimi de mesela merkeze yakınlaştıkça ne kadar fiyat arttığı olabilir

- ![[Pasted image 20250714003333.png]]
- [[Cost Function]] ı yarın açıklamasını yaz, bi nevi neyi anlayıp anlamadığımı görmek için

[[2025-07-15]]
- Linear grafiği mantığında düşünmen lazım
	- Her bir data noktası için;
	- predictiondan actual value yı cıkartıp, mesafe için cezalandıracağımız için karesini alıyoruz
	- Daha sonra bunları (sigma aracılığıyla) her biri için topluyoruz(m tane veri noktası var) sonra da sonucu 1/2m olarak alıyoruz
- We're looking to minimize this, minimize it to as close as to 0

Gradient descent aracılığıyla cost function'daki local minimumu bulmaya çalışıyoruz,
- Bunu yaparken eğim gittikçe azaldığı için bu değer azalıyor ve eskisi kadar büyük adım atmıyor, o tepeden

![[Pasted image 20250715231615.png]]

## Course 1 Module 2
[[2025-07-19]]
- ![[Pasted image 20250719211117.png]]
- Now we're introduced multiple features in our examples
	- $x_j$ dediği mesela x1 dediği zaman orada size in feet i seçme durumu
	- artık vektörel değerlerle karşı karşıyayız
	- i yukarıda
	- j aşağıda

- ![[Pasted image 20250719212713.png]]
- Vektörizasyon dediğimiz şey aslında o değişkenin ya da atadığımız denotion metodunun bir liste tutması olacak
	- Burada vektör x dediği, 4 feature lı bir datasete sahip olduğumuz için x1 x2 x3 ve x4
	- W vektörü de aynı şekilde
- Bunu dot product şeklinde yazmamız da 1. nin 1.iyle çarpılması yani
	- w vektörüyle x vektörünün çarpımı w1 . x1 + w2 . x2 gibi oluyor