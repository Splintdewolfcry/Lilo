
- [[Backpropagation]]
	- ![[firefox_qurXLu5hab.png]]
	- Selçuk hocadan yardım istediğim muhabbet buydu, farklı temellerde bile olsalar aslında göründüğünden daha fazla ortak nokta ve bağıntı var.
	- Bunu syntax la daha iyi çözebilirim

- Most important bit of transformers, the difference of [[Attention Mechanism]] from the old ways
	- ![[firefox_H7RdG5FDuo.png]]
	- [[Rnn]]'s have a shorter memory
		- ![[Pasted image 20240807203522.png]]

- [[Input Embedding]] is processed by assigning it a continuous value that represents how much weight(or attention?) should be given to a word.
	- ![[Pasted image 20240807230613.png]]
	- In this example, hi is given the most importance in order to construct what the input is like.
		- "Hi, how are you?" mostly necessitates a question afterwards or it is followed by a question sentence "how are you?". So we give hi the most significance and lower the values of things like "was"

- [[Encoder Layer]] consists of Multi-Headed Attention and Feed forward, with "Add & Norm" containing "[[Residual Info]]"
	- ![[Pasted image 20240807231113.png]]

- Multi-Headed Attention
	- Self attention's base is created by [[Query]], [[Key]] and [[Value]] prompts.  You query youtube with keys like transformers, losing focus... and it gives you an output of values that you searched for
	- ![[Pasted image 20240807231710.png]]
	- ![[24-08-07 23.17.46.png]]
	- Query and keys are used in a dot multiplication metrix that gives out scores of each value
		- ![[Pasted image 20240807231855.png]]
	- These values are then given importance
		- ![[Pasted image 20240807231900.png]]
	- In order to deal with more reliable info, you divide each word with their dimensions
		- ![[Pasted image 20240807231924.png]]
	- It then gets applied [[Softmax]] Normalization in order to get values that are between 1 and 0
		- ![[Pasted image 20240807231934.png]]
	- Then each Self Attention Head would be used (in theory) to learn new things about that sentence or info
		- ![[Pasted image 20240807232036.png]]
		- At last, they're passed onto a linear function to be later used
		- ![[Pasted image 20240807232053.png]]
	- O [videonun kalanına](https://www.youtube.com/watch?v=4Bdc55j80l8&t=559s) bakmam lazim ama yetti yani o monoton ses