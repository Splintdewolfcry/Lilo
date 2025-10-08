- ![[Pasted image 20250902235720.png]]
- ![[Pasted image 20250903232437.png]]
- this is a 2d array because it has 2 rows. All in all, it has 2 row, 3 columns
	- ![[Pasted image 20250903232552.png]]
- ![[Pasted image 20250906000607.png]]
- Buradaki bu forward propogation mantığının nasıl olduğunu anlatıyor.


- ![[Pasted image 20250906232743.png]]
- dense layer fonksiyonunda;
	- 3 unit var, 

![[Pasted image 20250909205705.png]]
- Tensorflow 2d array lerle calisiyor
	- array mantigi kaç tane [[]] olduğuyla ölçülüyor.

- 
	- ![[Pasted image 20250919205228.png]]
	- ![[Pasted image 20250919205211.png]]
	- ![[Pasted image 20250919211603.png]]
	- ![[Pasted image 20250919212608.png]]
	- Rowlar ilk matrixe denk geliyor
	- Columnlarsa ikinci
	- ![[Pasted image 20250919214352.png]]

Model Training Steps compared between logistic regression and Tensorflow
- ![[Pasted image 20251003214419.png]]
- ![[Pasted image 20251003214553.png]]

Cost functions for binary classification and logistic Regression
- ![[Pasted image 20251003214842.png]]
- ![[Pasted image 20251003214944.png]]


Binary, Regression with neg values and Regression with only + values
- ![[Pasted image 20251003220342.png]]

- Softmax
- Sparse means it can have only one value
	- ![[Pasted image 20251007212709.png]]
Numerical Roundoff Errors
- ![[Pasted image 20251007213141.png]]
- Numerically daha accurate olmasi icin linear activation yapip from logits ekliyorsun loss functiona
	- ![[Pasted image 20251007213718.png]]