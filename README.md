
# ImageRecomendatiom
Image recomendation system base on image description using an autoencoder architecture with convolutional neural networks (CNN).



## Main architecture

The used architecture was an Autoencoder, we will use it to generate a lower dimension latent vector that corresponds with the image description of a clothe.

Each low dimension representation of an image will be used as its description, the we will compare these descriptors to recommend similar images.
## Content of the repository

- **Autoencoder_UNet.ipynb**: Jupyter notebook with the main code used for training the CNNs and plotting the different results.
- **GeneracionBinarioDataset.ipynb**: Jupyter notebook with the code used for generating the binary of the dataset.
- **Results_XXXdim**: Folder with the results of the training for an Autoencoder with a latent vector of XXX dimensions.
## Code

Each code Notebook is self explained. To execute the different trainings we used Google Colaboratory with Google Drive for loading the binary file and saving the output plots of each training.
## Results

Below we will show the results of the main architecture that we used, that was the one that had 3 latent dimensions.

### Reconstruction of the images

Below it is presented the evolution of the reconstruction of test images.

![3dim_evolution](https://raw.githubusercontent.com/guillermoiglesiashernandez/ImageRecomendation/master/Imgs/10dim-Evolution.gif)

![dim_comparison](https://raw.githubusercontent.com/guillermoiglesiashernandez/ImageRecomendation/master/Imgs/Dimension-Comparison.png)

### Losses of the training

![losses](https://raw.githubusercontent.com/guillermoiglesiashernandez/ImageRecomendation/master/Imgs/losses.png)

### Representation of the latent space

Because the latent dimension is 3, we can plot how the images are distributed in a three dimensional space.

![points_generated](https://raw.githubusercontent.com/guillermoiglesiashernandez/ImageRecomendation/master/Imgs/PointsGenerated.png)

# Recomendation system

Below are presented the results of different methods for recommending similar images.

### Recomendation using clustering

The clustering method used was KMeans with 6 clusters. The clusters are displayed below.

![clusters_generated](https://raw.githubusercontent.com/guillermoiglesiashernandez/ImageRecomendation/master/Imgs/ClustersGenerated.png)

The recomendation based on these clusters is the following.

![recomendation_euclidean](https://raw.githubusercontent.com/guillermoiglesiashernandez/ImageRecomendation/master/Imgs/recomendation_clusters_results.png)

### Recomendation using euclidean distance

![recomendation_euclidean1](https://raw.githubusercontent.com/guillermoiglesiashernandez/ImageRecomendation/master/Imgs/nearest_neighbor_results1.png)
![recomendation_euclidean2](https://raw.githubusercontent.com/guillermoiglesiashernandez/ImageRecomendation/master/Imgs/nearest_neighbor_results2.png)
![recomendation_euclidean3](https://raw.githubusercontent.com/guillermoiglesiashernandez/ImageRecomendation/master/Imgs/nearest_neighbor_results3.png)
![recomendation_euclidean4](https://raw.githubusercontent.com/guillermoiglesiashernandez/ImageRecomendation/master/Imgs/nearest_neighbor_results4.png)
![recomendation_euclidean5](https://raw.githubusercontent.com/guillermoiglesiashernandez/ImageRecomendation/master/Imgs/nearest_neighbor_results5.png)

## Dataset

The dataset [Fashion Product Images Dataset](https://www.kaggle.com/paramaggarwal/fashion-product-images-dataset) was used for the training of the networks was obtained from Kaggle, it contains approximately 44200 different images of clothes. Besides it cointains the different tags for differentiate each type of clothe we will not use them, because the objective of the work is to do an unsupervised learning.

### Dataset binary generation

First we tried to download and charge each time the whole dataset from Kaggle, but this operation was very slow because each image was treated individually.

Then we tried to save a .zip file with the content of the dataset an download it for each training, this process was also very slow and consumed too much time.

Finally we decided to generate a binary file that could be efficiently loaded, the generation of this file is described in _GeneracionBinarioDataset.ipynb_ file.
## Acknowledgements

 - [Fashion Dataset used for the training](https://www.kaggle.com/paramaggarwal/fashion-product-images-dataset)