# Songs_Similarity
The goal is to find the similarity between songs, similarity is found by cosine similarity and euclidean similarity.
Cosine similarity measures the cosine of the angle between two vectors. It's particularly useful when dealing with text or high-dimensional data where the magnitude of the vectors might vary. Cosine similarity ranges from -1 to 1, where:
1 indicates that the vectors are exactly the same.
0 indicates that the vectors are orthogonal (no similarity).
-1 indicates that the vectors are diametrically opposed (opposite similarity).
The Euclidean similarity is also known as "inverse similarity" based on the Euclidean distance, it is the reverse of Euclidean distance.
For these matrixes, data should be in vectors, whatever the original form is, i.e., text, audio etc.
For vector purposes, I have considered the "librosa" library to deal with the audio data.
The problem I encountered to me was that "librosa" work with wav files, so I had to write a function that converts the mp3 to wav first before passing  "librosa" for vectorization, this is done with the "subprocess" library.
MFCCs considered that combine the mel scale and cepstral coefficients. They are obtained by first converting the power spectrum of an audio signal into the mel scale, then taking the logarithm of the magnitudes, and finally applying a Discrete Cosine Transform (DCT) to the resulting values. The resulting coefficients are MFCCs.
The next problem encountered was that the vector's form should be 1D so I converted the vectors into 1D form.
I faced the problem of length shape as some songs as 1 song can be of 1 minute, and others can be of 2 minutes maybe, but to find the similarity, the shape should be same. To solve this problem, I have considered the concept of a Pad / truncate array.
I have tested the songs roughly of 1-minute length of the same singer but the different songs and the similarity was less than 0.3, which means the songs are different as the text in the song is different.
Then to make sure the code is working fine I considered the same song as song1 and song2. The similarity score in this case was 1.0 which means songs are similar.
