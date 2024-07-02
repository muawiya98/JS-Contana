# JSContana: Malicious JavaScript detection using adaptable context analysis and key feature extraction and feature selection model for adaptive cross site scripting attack detection 

## 1. Introduction

	JavaScript has played a crucial role in web development, making it a primary tool for
	hackers to launch assaults. Although malicious JavaScript detection methods are becoming
	increasingly effective, the existing methods based on feature matching or static word embeddings
	are difficult to detect different versions and obfuscation of JavaScript code. To solve this problem,
	we present a novel detection method that consists of adaptable context analysis and efficient key
	feature extraction. The key to our approach is context analysis based on dynamic word
	embeddings. Furthermore, as a classification module in the method, TextCNN can effectively
	extract key features.

## 2. Abstract

	Most websites use JavaScript to create dynamic interaction, which brings great
	convenience to people’s daily life, but also brings many security problems. Malicious JavaScript
	codes are challenging to detect because they can transcode malicious code by obfuscation methods,
	such as logical operation, string segmentation and string compression. Furthermore, JavaScript
	version iteration also makes detection more difficult.
	
	The existing methods for malicious JavaScript detection mainly rely on feature matching
	or static word embeddings. However, feature learning based on static word embeddings does not
	represent the real context information of code, which means the problem of polysemy in the code
	is not resolved, making undesirable detection effects. Besides, the analysis methods based on
	feature matching can only detect known malicious samples.
	
	Aiming at the problem of undesirable detection effects caused by insufficient use of code
	information in existing methods, we present a novel detection method using adaptable context
	analysis and efficient key feature extraction. To achieve this, Word2Vec and two Bidirectional
	Long Short-Term Memory (Bi-LSTM) layers are introduced into feature learning of the model. It
	is featuring learning based on dynamic word embeddings that makes full use of code information.
	
	In TextCNN, the object of convolution operation is the word vector, and convolution kernel width
	is consistent with the dimension of word vectors, which can extract features effectively. Then we
	perform a features selection process using the Tabu Search algorithm in order to reduce the
	dimensions of dynamic word embedding and improve performance.

## 3. Papers and References

	- [Paper 1 JSContana: Malicious JavaScript detection using adaptable context analysis and key feature extraction](https://www.sciencedirect.com/science/article/abs/pii/S0167404821000420)
	- [Paper 2 Dynamic feature selection model for adaptive cross site scripting attack detection using developed multi-agent deep Q learning model](https://www.sciencedirect.com/science/article/pii/S1319157823000204)

## 4. Applied Techniques

	- Technique 1 Deep Learning Model: [Building a large neural network containing various layers (Bi-LSTM, CNN, FCN) (Deep Learning)]
	- Technique 2 Feature extraxtion: [Extract the hidden state from Bi-LSTM layers and combine them (Math & ML)]
	- Technique 3 DFS: [Dynamic feature selection model for adaptive cross site scripting attack detection (Reinforcmentr Learning)]
	- Technique 4 Ensemble Learning: [Stacking Ensemble Learning (ML)]
	- Technique 5 FS-1: [Feature Selection by extract statistical information (Math & ML)]
	- Technique 6 FS-2: [Feature Selection by Tabu Search Learning (Optimization)]
	- Technique 7 FS-3: [Feature Selection by traditional sklearn models (ML)]

## 5. Methodology

	1. **Data Collection and Preprocessing:** [We collected 4,000 non-attack JavaScript files and 4,000 XSS attack files, then rendered
	them as structured data. Then we deleted the URL's and the IP's from them. Then we performed a
	grammatical analysis process to obtain Syntactic unit sequences with detailed information. Finally
	we converted it to static word vectors.
	We collected 4,000 payload files that contain an XSS attack and 4,000 files that do not
	contain an attack, then we decode them, then we perform the Generalization process, where we
	convert each number or series of numbers to the number 0 and each link to "http://u" and then we
	After that we did the segmentation process. Finally, we converted it to static word vectors.]

	2. **Model Training:** [we have trained a deep learning model to classify JavaScript files (and
	payload files), where 0 indicates that the file does not contain an attack and 1 indicates that the file
	has an attack. The figure below shows the structure of the model. We give the Embedding layer
	the following parameters (vocab_size=500000, embedding_dim=512, input_length=2048) and for
	the Bidirectional layer (units=50, input_shape=(None, 50), return_sequences=True) for both
	layers. As for the four layers of Conv1D (filters=128, activation='tanh'), but they differ from each
	other in kernel_size, where we give the first layer 7, the second 15, the third 25, and the fourth 35. Finally the fullyConnectedLayer. for the first layer (units=64, activation ='relu') and for the output
	layer (units=1, activation='sigmoid')]


## 6. Results

	[You can find the final results by looking at the report above.]