---
CreatedOn: 2025-03-02T17:43
---
- Attention Is All You Need
	- ![[Attention Is All You Need.pdf]]

Ilk transformers modeli bir machine translation taskle başlamış
- [[BLEU]] metriğini kullanarak olaya girişmişler

>Noam proposed [[scaled dot-product attention]], multi-head attention and the parameter-free position representation and became the other person involved in nearly every detail.
- [[Scaled Dot-Product Attention]]
	- ![[Scaled Dot-Product#^dfsdui]]
	- ![[Scaled Dot-Product#^w8t5tm]]
Daha önce Scaled Dot Product kullanılıyormuş lakin [[scaled dot-product attention]] ının yarattığı fark nedir ve mesela işte square root unu alırken kaybettiğimiz bilgi nedir?

> Attention mechanisms have become an integral part of compelling sequence modeling and [[transduction models]] (like KNN) in various tasks, allowing modeling of dependencies without regard to their distance in the input or output sequences [2, 19]. In all but a few cases [27], however, such attention mechanisms are used in conjunction with a recurrent network.

> The Transformer allows for significantly more parallelization and can reach a new state of the art in translation quality after being trained for as little as twelve hours on eight P100 GPUs.
- 2017 de tabii bu 8 tane P100 idi
> The NVIDIA Tesla P100 Server Graphics Card is designed for scientific and research applications. Its 3584 CUDA cores and **16GB of HBM2 vRAM** linked via a 4096-bit interface provide performance to the order of 9.3 TFLOPS at single precision, 18.7 TFLOPS at half precision, and 4.7 TFLOPS at double precision.


> We call our particular attention "Scaled Dot-Product Attention" (Figure 2). The input consists of queries and keys of dimension dk, and values of dimension dv. We compute the dot products of the query with all keys, divide each by √dk, and apply a [[softmax function]]  to obtain the weights on the values.
> 
- **We have three kinds of lists** (or vectors) called **queries**, **keys**, and **values**.
- **We compare each query to every key** by computing their dot products (multiply corresponding numbers and add).
- Because these dot products can become very large when the lists are long, **we shrink** (scale) them by dividing by the square root of the key’s length ( √dk ).
- **We turn these scaled dot products into “weights”** using something called a softmax. Think of it like turning raw scores into probabilities that sum to 1.
- **Finally, we use these weights to blend (or pick out) the values**. Each value is multiplied by its weight, and then all are added up.

- **Why the square root?**: In probability and statistics, if you add up a bunch of random variables, their total “spread” (standard deviation) typically grows proportionally to the square root of the number of terms. Dividing by √dk roughly counters that natural growth. It’s a simple but consistent way to keep these dot products from becoming too large.