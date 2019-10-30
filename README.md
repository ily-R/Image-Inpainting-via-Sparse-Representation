# Image-Inpainting-via-Sparse-Representation

**Bin Shen and Wei Hu and Zhang, Yimin and Zhang, Yu-Jin, Image Inpainting via Sparse Representation Proceedings of the 2009 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP ’09)**

This project takes in a destored image and fill in the damaged pixels using a sparse representation of a dictionary that is build by intact patches.

*Please refer to the notebook for in-depth analysis and full results.* [Image Inpainting step by step](https://nbviewer.jupyter.org/github/ily-R/Image-Inpainting-via-Sparse-Representation/blob/master/main.ipynb)

## Intro:

The task of Inpainting in Computer Vision is well known and widely used in this field. It consists in automatically filling the missing pixels in an image . There are two approaches in the literature. An example-based approach that searches for the nearest patch in the intact region of the patch containing the missing pixels. The nearest one is defined by a distance, for example, in [3], they used a simple eucildian distance. On the other hand, in the PDE (Partially Differential Equations) approach, they fill the missing part step by step from the bounds to the center of the distortion.

## Results:

#### Region filling:

<p align="center">
  <img src="https://github.com/ily-R/Image-Inpainting-via-Sparse-Representation/blob/master/README_DATA/result1.JPG?raw=true" alt="capture reconstruction"/>
</p>
<p align="center">
  <img src="https://github.com/ily-R/Image-Inpainting-via-Sparse-Representation/blob/master/README_DATA/result2.JPG?raw=true" alt="capture reconstruction"/>
</p>
<p align="center">
  <img src="https://github.com/ily-R/Image-Inpainting-via-Sparse-Representation/blob/master/README_DATA/result3.JPG?raw=true" alt="capture reconstruction"/>
</p>

#### Noise removal:

<p align="center">
  <img src="https://github.com/ily-R/Image-Inpainting-via-Sparse-Representation/blob/master/README_DATA/result4.JPG?raw=true" alt="capture reconstruction"/>
</p>

## Discussion:
#### Advantages :

* It gives very good results that are realistic for us, we just have to make a good tuning of the parameters
* Even if in the article it is said that it is not made for the suppression of noise, but we could test it and apply it to Noise and it works well because each pixel or small group of pixels will be considered as a missing region to tackle !
* Simple model to understand, intuitive and interpretable.
#### Disadvantages:

* It is very slow in execution even with small images (300, 300) compared to the images of our time in 2019, it has therefore a mediocre complexity .
* The higher the resolution of the image as well as its quality, the more the results are bad
* Several parameters for tuning for example: h, stride, alpha, max_iter, ... , which complicates the task to get the best fitting

## Reference:

Julien Mairal Sparse coding and Dictionnary Learning for Image Analysis INRIA Visual Recognition and Machine Learning Summer School, 2010

A. Criminisi, P. Perez, K. Toyama Region Filling and Object Removal by Exemplar-Based Image Inpainting IEEE Transaction on Image Processing (Vol 13-9), 2004
