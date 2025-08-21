[[2025-07-01]]
Dizin ağaçları üzerinden model eğitçez
- Her bir tier için;
	- 15'er tane dizin ağacı mantığında sözdizim apacı python üzerinden üretip
		- 100'er tane sentetik ağaç üretip
		- Yarı yarıya kontrollerini sağlarız
- Model konusunda
	- Ya free tier API ya da local modeller üzerinden gideriz
		- Nvidia Free tier'ini özellikle kullanabiliriz (aylık 100 saat)
			- Nemotron üzerinden
	- Elimizde tagged data var, TSCorpus'un datası
		- Punctuation ve numaraları temizleriz ^j0ud2b
			- PİLOT İÇİN
				- Her bir sözcük türüne (Eylem, Ad, vs..) üzerinden 150 er tane örnek,
				- Toplam taglenmiş 1200 örneğimiz olacak, 600 600 bölüşüp kontrol ederiz
				- Bu 1200 örnekle;
					- Gemini 2.5 üzerinden prompt atıp 2 sözcüklük ve 3 sözcüklük öbekler üreteceğiz
						- Bunların kontrolü sonrasında (kaç tane örnek çıkar kestiremiyorum)
				- artık sözdizim modeli oluşturmaya/eğitmeye başlarız

Tagleme
- Bazı sözcükler bağlamına göre türü değişebiliyor
	- Bir kitap (bir DET de olabilir, sıfat da)
	- Tüm kitaplar

[[2025-07-04]]
- Artik Sentetik data üretimindeyiz;
	- Az çok elimizde tümce örneği var diyorum, 1000 civarındayız
		- Gemini 2.5 Proyla anlaşılabilir ve dilbilgisel Eylem öbeği çok güzel üretiyor, Sözdizim 2 notlarını atınca
			- Devamında hem gemini playground dan hem de groq un API'ını kullanırız(PDF leri parslarız)
	- İskelet mantığı üzerinden 15-20 (hadi de 30), ağaç çizip;
		- Belirteçli belirteçsiz
		- İç Tümceli... vs
			- Bunu modele dizin ağacı üzerinden besleriz,
				- Her bir çizim için 2 ağaç gibi ilerleyeceğiz
					- Taşımaları, ağaçtaki değişim üzerinden yaparız
	- Yapabilirsek ağacı alttan çizen animasyon ve değişimi gösteren animasyon

- Bir sonrakinde;
	- Sentetik data generation devam
	- POS tagging işinde ilerlememiz lazım
		- Eylem öbeklerini güzel veriyorsa eylemleri düzeltmemize gerek yok
		- Sıfat ve zarf karıştırıyorsa mesela, onlara bunun datasını sağlayıp bunları geliştirebiliriz
	- İskelet hazırlamaya başlarız (Şu an aciliyeti yok ama elimizde olması zamanı geldiğinde çok işimize yarayacak)
	- Artık modellere giriş yapmaya başlarız 
		- Hangi modelleri kullanabiliriz
		- Küçük modelde eğer doğruluk elde edebilmeye başlarsak onun işi de aşırı kolaylaşıcak


[[2025-08-16]]
- LiSyntax icin 100 tane yeni hic gormedigi data uzerinden dogruluk testi
- numaralarin da nasil calistigini ogren

- Denemeders te on kod var
- Veriler derlenecek
	- Dilbilime Giriş ve Syntax notlarını derliyoruz 
	- Ben kendi notlarima bakacagim
	- 