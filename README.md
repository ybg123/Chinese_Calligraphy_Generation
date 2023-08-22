# Chinese Calligraphy Generation <br>

## Overview <br>
* Generate two styles of Chinese calligraphy from two Chinese calligrapher, Liu Gongquan and Mi Fu, at the resolution of 64px. One generated image contains one Chinese character. Code is available at `Chinese_Calligraphy_Generation_64px.ipynb`. <br>
* Number of training images, Liu Gongquan style: 6763 images at 64px; Mi Fu style: 6763 images at 64px. Dataset from kaggle [7]. <br>
* Training techniques: <br>
  * Progressive Growing of GANs [1, 4, 9]. <br>
  * Non-saturating GAN loss with R<sub>1</sub> regularization [2]. <br>
  * Differentiable Augmentation [3, 7]. <br>
* The Frechet Inception Distance (FID) [5, 6] calculated from 50000 generated images using the official implementation of FID to Pytorch [6] is **8.61** for the style of Liu Gongquan and **11.89** for the style of Mi Fu. Code is available at `FID_Calculation.ipynb`.<br>

## Generated images <br>
* Selected generated images: <br><br>

Liu Gongquan style (FID = 8.61) | Mi Fu style (FID = 11.89)
--- | ---
![lgq](generated%20images/Liu_Gongquan_Style.png) | ![mf](generated%20images/Mi_Fu_Style.png) 

* The faint black parts in the generated images are artifacts inherited from the training data. They can be effectively removed by applying a pixel-value-based filter. Code is available at `Filter.ipynb`.

Liu Gongquan style (after applying a filter) | Mi Fu style (after applying a filter)
--- | ---
![lgq](generated%20images/Liu_Gongquan_Style_filtered.png) | ![mf](generated%20images/Mi_Fu_Style_filtered.png) 

## Interpolation <br>
* Interpolation of latent space, code is available at `Interpolation.ipynb`

Liu Gongquan style| Mi Fu style
--- | ---
![lgq](generated%20images/Liu_Gongquan_style_interpolation.gif) | ![mf](generated%20images/Mi_Fu_style_interpolation.gif) 

## References <br>
<a id="1">[1]</a> Tero Karras, Timo Aila, Samuli Laine, and Jaakko Lehtinen. Progressive Growing of GANs for Improved Quality, Stability, and Variation. https://arxiv.org/abs/1710.10196 <br>
<a id="2">[2]</a> Lars Mescheder, Andreas Geiger, and Sebastian Nowozin. Which Training Methods for GANs do actually Converge? https://arxiv.org/abs/1801.04406 <br>
<a id="3">[3]</a> Shengyu Zhao, Zhijian Liu, Ji Lin, Jun-Yan Zhu. and Song Han. Differentiable Augmentation for Data-Efficient GAN Training. https://arxiv.org/abs/2006.10738 <br>
<a id="3">[4]</a> Github repository: https://github.com/aladdinpersson/Machine-Learning-Collection/tree/master/ML/Pytorch/GANs/ProGAN <br>
<a id="4">[5]</a> Github repository: https://github.com/GaParmar/clean-fid <br>
<a id="5">[6]</a> Github repository: https://github.com/mseitzer/pytorch-fid <br>
<a id="6">[7]</a> Github repository: https://github.com/mit-han-lab/data-efficient-gans <br>
<a id="7">[8]</a> Kaggle dataset: https://www.kaggle.com/datasets/yuanhaowang486/chinese-calligraphy-styles-by-calligraphers <br>
<a id="8">[9]</a> Kaggle notebook: https://www.kaggle.com/code/theoviel/conditional-progan-30-public <br>
