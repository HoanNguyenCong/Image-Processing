# 1. Image Stitching
**Pipline**

- Detect features (SIFT best matching keypoints)
- Compute Homography matrices
- Select best **H** matrix using `Random Sample consensus (RANSAC) algorithm` 
- Projective transfom source images to create new image plan (`dest image`)
- Blend dest image to remove stitches
## 1.1. 2x2 Image Transformation
![](https://www.cs.princeton.edu/courses/archive/fall00/cs426/lectures/transform/img021.gif)
## 1.2. 3x3 Image Transformation
![Homogeneous transformation](https://miro.medium.com/v2/resize:fit:800/1*emAmhmVX6UkJFnR6Byqjpg.png)
## 1.3. Compute Homography matrix (Homogeneous transformation)
![Homograpgy matrix](https://forums.fast.ai/uploads/default/original/2X/1/1acb50c0bbf769a476b344467519711f859d11d0.png)

## 1.4. Dealing with Outlier: RANSAC
## 1.5. Warping and Blending Images


# 2. References
## 2.1 SIFT - Scale-Invariant Feature Transform
- Detect blob using `Difference of Gaussian` (approximate Laplacian of Gaussian)
- Compute blob orientation using Image gradient
- **Keypoints** = Blobs with orientations
- Compute **Descriptors** (vector feature shape 1x128) from blob areas
- Compute distances between descriptors (Ex: L2 norm)
- Select good matches (pairs of keypoints) using matcher (Ex: Brute force, KNN)
- From these good matches, we can compute Homogenous transform matrix
-  https://docs.opencv.org/4.x/da/df5/tutorial_py_sift_intro.html

![SIFT Algorithm](https://www.researchgate.net/profile/Hiroshi-Kawaguchi/publication/220242450/figure/fig4/AS:669020810387456@1536518399011/Original-SIFT-algorithm-flow.png)

## 2.2 Image pyramid
- [Image pyramid - opencv](https://docs.opencv.org/4.x/da/df5/tutorial_py_sift_intro.html)
- [Image pyramid - medium](https://medium-com.translate.goog/analytics-vidhya/a-beginners-guide-to-computer-vision-part-4-pyramid-3640edeffb00?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=vi&_x_tr_pto=wapp)

## 2.3 Affine transformations
- [Affine transformation](https://docs.opencv.org/4.x/d4/d61/tutorial_warp_affine.html)

![](https://docs.opencv.org/4.x/Warp_Affine_Tutorial_Theory_0.jpg)

