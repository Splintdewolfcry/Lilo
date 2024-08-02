### Works
- https://huggingface.co/ElenaRyumina/face_emotion_recognition
	- Birebir aradığımız şeylerden biri
	- Canlı video içerisinde çalışıyor, ve minnoş
	- Denenmesi gerekiyor (endpoint'i var)
		- https://github.com/ElenaRyumina/EMO-AffectNetModel


- https://huggingface.co/ehcalabres/wav2vec2-lg-xlsr-en-speech-emotion-recognition
	- Speech üzerinden
	- emotions = ['angry', 'calm', 'disgust', 'fearful', 'happy', 'neutral', 'sad', 'surprised']


- https://huggingface.co/harshit345/xlsr-wav2vec-speech-emotion-recognition
	- Başarılı speech üzerinden analiz
		- ![[Pasted image 20240802232734.png]]





- https://huggingface.co/saribasmetehan/bert-base-turkish-sentiment-analysis
	- Türkçe bazlı
	- Ama daha ilkel versiyonlar üzerinden çalışıyor
	- Üç sentiment kullanmış
		- - "Positive" : LABEL_1
		- "Notr" : LABEL_0
		- "Negative" : LABEL_2
- https://huggingface.co/savasy/bert-base-turkish-sentiment-cased
	- Yukarıdakiyle yakın muhabbetler
		- Accuracy is about **95.4%**




- https://huggingface.co/j-hartmann/emotion-english-distilroberta-base?text=Oh+wow.+I+didn%27t+know+that.
	- Yapmaya çalıştığımız şeyin text versiyonu (tüm duygular) ^nxw9tc
	- Metodu anlamak, datayı bulabilmek açısından yararlı olabilir çünkü kullandığı data miktarı, onları testi/yaptıkları önemli
	- Colab i de var(demo)
- https://huggingface.co/pysentimiento/robertuito-emotion-analysis
	- https://github.com/pysentimiento/pysentimiento
	- ![[Modeller#^nxw9tc]]
-  https://huggingface.co/ayoubkirouane/BERT-Emotions-Classifier
	- Yine bert based
- https://huggingface.co/finiteautomata/beto-emotion-analysis


- https://huggingface.co/xmj2002/hubert-base-ch-speech-emotion-recognition
	- Çan çin çon speech üzerinden duygusal analiz
- https://huggingface.co/Aniemore/rubert-tiny2-russian-emotion-detection
	- Ruski versiyonu
- https://huggingface.co/Lajavaness/wav2vec2-lg-xlsr-fr-speech-emotion-recognition
	- Fr versiyonu ama bu wav2vec2 diğer bir sürü yerde kullanıldığını gördüm, o yüzden bir umut vadediyor gibi
	- Çok küçük bir dataset olduğu için iyi sonuç alamamışlar, daha proof of concept bir şey yaratmaya çalışmışlar
	- Birisinin thesisi 


- https://huggingface.co/OEvortex/Emotional-llama-8B
	-  Engage in open-ended dialogue while displaying emotional intelligence
	- Recognize and validate user emotions and emotional contexts
	- Provide supportive, empathetic, and psychologically-grounded responses
	- Avoid insensitive, harmful, or unethical speech
	- Continuously improve emotional awareness and dialogue skills