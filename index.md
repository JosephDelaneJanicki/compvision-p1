---
title: Project 1 – Image Processing
---

# Project 1: Projections, Histograms, Derivatives, Sharpening, Anisotropic Diffusion

## Perspective vs (Approx.) Orthographic
In the **perspective image**, parallel edges in the 3D scene **converge** in the 2D projection, forming a vanishing point (estimated near (918.2, 264.9)).  
This demonstrates **foreshortening**: objects farther from the camera appear smaller and compressed in scale.  

In the **orthographic-like image** (captured by stepping back and cropping), the same edges appear nearly parallel with minimal convergence.  
This more closely approximates an **orthographic projection**, where parallel rays remain parallel.  the program automatically crops the image to a percent based on a perameter

**Visual takeaway:** Perspective emphasizes depth but distorts shapes with distance, while the orthographic-style framing preserves proportions more consistently across the scene.


![](outputs\perspective_annotated.png)  
![](outputs\ortho_annotated.png)

## Histogram Equalization
Panel for test image 1:  
![](outputs\hist_eqti1.png)  
Panel for test image 2:  
![](outputs\hist_eqti2.png)  
Panel for test image 3:  
![](outputs\hist_eqti3.png)  
Creative task (Solaris the cat):  
![](outputs\mine\hist_eqSolaris.png)

## Histogram Matching
Example for test images:  
![](outputs\match\testimage1_hist_match.png)  
![](outputs\match\testimage2_hist_match.png)  
![](outputs\match\testimage3_hist_match.png)

## Derivative vs DoG
![](outputs\dog\testimage4_dog_compare_sigma1.50.png)  
![](outputs\dog\testimage5_dog_compare_sigma1.50.png)  
![](outputs\dog\testimage6_dog_compare_sigma1.50.png)

## Unsharp Masking
Moon example:  
![](outputs\sharp\moon_sharpen_sigma1.0.png)  
CT example:  
![](outputs\sharp\ct_sharpen_sigma1.0.png)

## Anisotropic Diffusion vs Gaussian
![](outputs\aniso\noisytestimage1_aniso_vs_gauss_K20.0_it15_lam0.2_sig1.5.png)  
![](outputs\aniso\noisytestimage2_aniso_vs_gauss_K20.0_it15_lam0.2_sig1.5.png)

