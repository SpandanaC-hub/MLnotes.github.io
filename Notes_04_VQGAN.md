In the paper ["Taming transformers for High-Resolution Image Synthesis"][https://arxiv.org/pdf/2012.09841.pdf], the authors aim to learn a context rich codebook of the images using a convolutional approach and learn long-range interactions within the image using transformer architecture. They include an adversarial loss component to ensure that the codebook includes important l
### VQ-VAE (Vector Quantized VAE)
#### Why the need for vector quantized latent space?
A good latent space would ideally cluster semantically similar data points close to each other and place semantically dissimilar points far apart. Also, majority of the data distribution would be embedded in a  compact volume in the latent space and not extend to infinity. In autoencoders, learned latent space does not have to hold these properties. In VAEs, due to the gaussian prior on the latent space distribution, ensuring the latent space distribution is compact. But VAE learn a continuous latent representation of data, whereas VA-VAE learns a discrete representation.
- Why a discrete latent representations? A lot of the data we encounter in the real world favors a discrete representation. For instance, images have a discrete objects with discrete features. And many algorithms liek transformers are designed to work with discrete data, so having a discrete representation for data makes working with these algorithms easier.

#### How to discretize latent representation?
We create a codebook, which is a list of vectors. The codebook is used to quantize the latent representation by comparing it to the vectors in the codebook and selecting the codebook vector that is closst in euclidean space.
The expressivity of the quantized latent space is explained by the fact that the encoder output in the VAE is a series of vectors, so for a given image the encoder outputs a series of vectors that are respectively quantized based on minimum euclidean distance. So for an encoder that outputs 32x32 grid vectors, quantization results in 32x32xd tensor, where d is the codebook vector dimension.
Note: like the encoder and decoder, the codebook vectors are learned via gradient descent

