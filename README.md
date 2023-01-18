### General Idea

1. Train autoencoder
2. Make a latent dim representation for all corpus
3. Cluster with K-Means
4. Apply PCA and compress it until 2D
5. Viz!


### I did an oopsie 😵
Currently I vectorize the text into dense representation with BoW which is the number generated is an index from the BoW dictionary. If I cluster the dense representation, it will calculate the distance beetwen a particular word with other word IN THE DICTIONARY (not the semantic similiarity). Oopsie, the dictionary is made randomly and of course the cluster will mean nothing.

How to overcome this? I need word embeddings. The problem is I still don't understand how to perform the "decoder part" when training. I think I need to somehow convert from decoder embedding layer into indices/dense representation (no?) to be able to calculate the MSE loss. Or should I just calculate the loss between input embedding vs output embedding? I think the second option more promising.  