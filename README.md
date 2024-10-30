# SAR-despeckle
Supervised Deep Learning Training Dataset for SAR despeckling. 

# Dataset 
If you download and use this dataset, please cite the following paper. 

Owing to the unique geometric distortions as well as complicated speckle noise in SAR images it is extremely difficult to simulate geometric distortion similar to real SAR image. In addition, simulating noise as uniform and single-distributed also fails to fully represent speckle complexity. The article uses the temporal and spatial information of time series SAR images to create near-real SAR intensity datasets using an adaptive multilook method called generalized likelihood ratio test(GLRT), which outstandingly solves the problems encountered with simulated data. This dataset effectively preserves local features, structures, and edge details while significantly reducing oversmoothing and avoiding the introduction of filtering artifacts.

It is worth mentioning that the dataset used in the paper has a total of 270 pairs (training dataset 250 and validation dataset 20) of size 512x512. The uploaded dataset is subdivided into 256x256 size. After detailed inspection of their quality, some data pairs are removed, and finally 936 pairs of data are obtained.

The dataset contains **gt image**, **original SAR intensity image** and **original SAR phase image**. This is related to our proposed SAR denoising network: phase-guided deep despeckling network **(SAR-PGD2Net)**. Based on the correlation between intensity/amplitude and phase, to improve the accuracy of speckle noise estimation, we introduce phase information in one subnetwork (speckle noise estimation subnetwork) of the proposed SAR-PGD2Net. If you don't need to use the original SAR phase image, you can ignore it.

For more detailed information, please refer to the paper.

# References
Guan, Jianjun, et al. "Robust SAR Image Despeckling by Deep Learning From Near-Real Datasets." IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing (2023).
