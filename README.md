GenLayout
===
Generative AI to generate layouts

# LayoutVAE + Cyberagent/Crello Datasets

Trains a Variational Autoencoder (VAE) with datasets produced by
[CyberAgent/Crello](https://huggingface.co/datasets/cyberagent/crello) and
reconstructs layouts from sampled codes of the latent space.

<a href="https://colab.research.google.com/github/shishimaru/GenLayout/blob/main/LayoutVAE/LayoutVAE_with_Crello.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

Click the badge above to run the LayoutVAE in Google Colab.


## Preview of Crello Datasets

During preprocessing, layouts related to Image/Text/SVG Shape are extracted from
the original datasets, and training/validation datasets are constructed

Green rectangles indicate Images, red ones indicate Text, and gray ones indicate SVG shapes.

![datasets](./LayoutVAE/screenshots/datasets.png)

## Latent Vectors Obtained by Training VAE

After training VAE, we can obtain latent vectors of the training data by encoding
and a picture below is 2D graphic by rendering them.

Each color represents labels of `format` in the training data and we could
observe some groups were constructed because instances of same labels were
located near by the VAE training.

Orange instances represent formats related to documents such as resume, poster
and so forth. Light green ones on above area represent a format for zoom
background. And blue and purple ones represent marketing banners for SNS such as
Instagram, Facebook, TikTok and so forth.

![latent vectors](./LayoutVAE/screenshots/latent-vectors.png)

## Reconstruction of Latent Vectors

We get samplings from a grid [-2, 2] on the latent space and layouts were
generated by reconstructing them with the decoder of VAE.

![grid vectors](./LayoutVAE/screenshots/grid-vectors.png)

![reconstruction-1](./LayoutVAE/screenshots/reconstruction-1.png)

![reconstruction-2](./LayoutVAE/screenshots/reconstruction-2.png)
