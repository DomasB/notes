**What is latent space in ML?**
-------------------------------

**‍**Latent space is the representation of compressed data, where compressed data is data encoded using fewer bits than the original representation. The figure below represents an auto-encoder architecture that takes an input image, compresses (or encodes) the image into a smaller tensor of floating point numbers and then recreates (or decodes) the original image from the compressed (encoded) representation. For the auto-encoder to reconstruct the image from the compressed data with high fidelity, it must learn to store all relevant information and disregard the noise. The encode removes any extraneous information, and only encodes the most important features. This ‘compressed state’ is the Latent Space representation of the input image.  


![latent space visualization](https://assets.website-files.com/618399cd49d125734c8dec95/6437e8cb4769a16c5e8b05df_VWVYaJ5KzUbtPztSQ30GUBgJBumdKRNO_CB57S6bUkOvKyHCnWzktORVCr8-SKmgvOBh8mF--_bq2K0HHFTkqSEJKG_SLiHkXtZyAWtN1LRpTIoxG10jSDG8iJbGTq6wvtFX5GdubRy0E6jWQ9p4ZA.png)Image Source: [Hackernoon Latent Space Visualization](https://hackernoon.com/latent-space-visualization-deep-learning-bits-2-bd09a46920df)
LLM Tags:  #ml #deep-learning #auto-encoder
LLM Tags:  #ml, #deep-learning