[[TR-AR 1.1 Introduction To Audio Data]]
- By nature, a sound wave is a continuous signal, meaning it contains an infinite number of signal values in a given time. This poses problems for digital devices which expect finite arrays. To be processed, stored, and transmitted by digital devices, the continuous sound wave needs to be converted into a series of discrete values, known as a digital representation.

- If you look at any audio dataset, you’ll find digital files with sound excerpts, such as text narration or music. You may encounter different file formats such as `.wav` (Waveform Audio File), `.flac` (Free Lossless Audio Codec) and `.mp3` (MPEG-1 Audio Layer 3). These formats mainly differ in how they compress the digital representation of the audio signal. #AudioFormats

- [[Sampling]] is the process of measuring the value of a continuous signal at fixed(uniform) time steps making it _discrete_.
	- ![Signal sampling illustration](https://huggingface.co/datasets/huggingface-course/audio-course-images/resolve/main/Signal_Sampling.png)

	- The **[[sampling rate]]** (also called sampling frequency) is the number of samples taken in one second and is measured in hertz (Hz). #SignalProcessing_Definitions
		- To give you a [[point of reference]], CD-quality audio has a sampling rate of 44,100 Hz, meaning samples are taken 44,100 times per second. For comparison, high-resolution audio has a sampling rate of 192,000 Hz or 192 kHz. 
		- A common sampling rate used in training speech models is 16,000 Hz or 16 kHz. #Common_Standard

	- The choice of sampling rate primarily determines the highest frequency that can be captured from the signal. This is also known as the Nyquist limit and is exactly half the sampling rate. The audible frequencies in human speech are below 8 kHz and therefore sampling speech at 16 kHz is sufficient. 
		- Using a higher sampling rate will not capture more information and merely leads to an increase in the computational cost of processing such files. On the other hand, sampling audio at too low a sampling rate will result in information loss. 
		- Speech sampled at 8 kHz will sound muffled, as the higher frequencies cannot be captured at this rate.

	- **Consider an example: a 5-second sound at a sampling rate of 16,000 Hz will be represented as a series of 80,000 values, while the same 5-second sound at a sampling rate of 8,000 Hz will be represented as a series of 40,000 values.**


### While the sampling rate tells you how often the samples are taken, what exactly are the values in each sample?
#### Cue:  Amplitude and bit depth

- Sound is made by changes in air pressure at frequencies that are audible to humans. The **[[amplitude]]** of a sound describes the sound pressure level at any given instant and is measured in decibels (dB). *We perceive the amplitude as loudness*. To give you an example, a normal speaking voice is under 60 dB, and a rock concert can be at around 125 dB, pushing the limits of human hearing.

- In digital audio, each audio sample records the amplitude of the audio wave at a point in time. The **bit depth** of the sample determines with how much precision this amplitude value can be described. The higher the bit depth, the more faithfully the digital representation approximates the original continuous sound wave.