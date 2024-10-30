# SAR-despeckle
Supervised Deep Learning Training Dataset for SAR despeckling. 

# Dataset 
We are now making the training dataset open-source (https://drive.google.com/file/d/1p4w7WNPiqvK2haz53uNqy_ewubcoshle/view?usp=sharing). If you download and use this dataset, please cite our paper published in J-STARS.

Owing to the unique geometric distortions as well as complicated speckle noise in SAR images it is extremely difficult to simulate geometric distortion similar to real SAR image. In addition, simulating noise as uniform and single-distributed also fails to fully represent speckle complexity. The article uses the temporal and spatial information of time series SAR images to create near-real SAR intensity datasets using an adaptive multilook method called generalized likelihood ratio test(GLRT), which outstandingly solves the problems encountered with simulated data. The resulting near-real image(noise-free reference image) can better preserve PS or strong scattering information. This dataset effectively preserves local features, structures, and edge details while significantly reducing oversmoothing and avoiding the introduction of filtering artifacts. 

It is worth mentioning that the dataset used in the paper has a total of 270 pairs (training dataset 250 and validation dataset 20) of size 512x512. The uploaded dataset is subdivided into 256x256 size. After detailed inspection of their quality, some data pairs are removed, and finally 936 pairs of data are obtained.

The dataset contains **gt image**, **original SAR intensity image** and **original SAR phase image**. This is related to our proposed SAR denoising network: phase-guided deep despeckling network **(SAR-PGD2Net)**. Based on the correlation between intensity/amplitude and phase, to improve the accuracy of speckle noise estimation, we introduce phase information in one subnetwork (speckle noise estimation subnetwork) of the proposed SAR-PGD2Net. If you don't need to use the original SAR phase image, you can ignore it.

For more detailed information, please refer to the paper.

# Phase-Guided Deep Despeckling Network(PGD2Net)
To make better use of the near-real datasets and effectively suppress speckle, we propose a deep learning architecture called PGD2Net that can achieve near real-time performance and estimates the high-quality clean intensity image. 

We first construct a speckle noise estimation subnetwork (SNENet) to generate a speckle noise image by extracting the homogeneous noise. Subsequently, we establish another subnetwork (dual-branch denoising subnetwork, DBDNet) to conduct feature interaction and estimate the clean intensity image based on a specially designed cross-attention module. PGD2Net consists of the above two subnetworks and is optimized by a combined loss function.

The code for PGD2Net is currently unavailable for open source. Thank you for your understanding. We kindly ask for your patience.

# References
Guan, Jianjun, et al. "Robust SAR Image Despeckling by Deep Learning From Near-Real Datasets." IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing (2023).
