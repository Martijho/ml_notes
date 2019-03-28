#### Variational autoencoders
Creating a latent space apropriate for sampling and reconstruction is greatly
helped by variational autoencoders. At the lowest point in the autoencoder bottleneck, 
add two split dense layers, one to represent mean and one to represent standard deviation. 
Then use these vectors to sample the latent space into a vector of the same size as the
original bottleneck. 
    The goal is to end up with a continous latent space with densly packed feature "regions". 
This is aided by introducing Kullback-Leibler divergence in the loss function. 
Source: https://towardsdatascience.com/intuitively-understanding-variational-autoencoders-1bfe67eb5daf