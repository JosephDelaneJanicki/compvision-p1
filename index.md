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

Histogram equalization spreads out the intensity distribution of the image.  

In the test image, the original histogram was clustered around certain gray levels, causing low contrast.  
After equalization, the histogram is more uniform, stretching pixel values across the full range.  

**Effect:** Dark regions brighten, light regions darken, and overall contrast improves, making details more visible.

Panel for test image 1:  
![](outputs\hist_eqti1.png)  
Panel for test image 2:  
![](outputs\hist_eqti2.png)  
Panel for test image 3:  
![](outputs\hist_eqti3.png)  
Creative task (Solaris the cat):  
![](outputs\mine\hist_eqSolaris.png)

## Histogram Matching

Histogram matching forces the intensity distribution of a source image to resemble a **target histogram**.  

Compared to equalization, this does not simply spread intensities uniformly, but instead reshapes them toward a specific style.  
Visually, this allows adapting one image to look more like another (e.g., transferring contrast or tonal qualities).  

**Observation:** The matched images follow the target distribution closely, though small gaps/spikes appear due to discrete mapping.

Example for test images:  
![](outputs\match\testimage1_hist_match.png)  
![](outputs\match\testimage2_hist_match.png)  
![](outputs\match\testimage3_hist_match.png)

## Derivative vs DoG

Two approaches were compared:  
1. **Naive:** Smooth with a Gaussian, then apply derivative filters ([-1, 0, 1] in x/y).  
2. **DoG (Derivative of Gaussian):** Convolve directly with derivative-of-Gaussian filters.  

**Results:** Both methods produce very similar edge maps, showing that smoothing before differentiation ≈ differentiating a smoothed function.  
Minor differences arise from numerical precision and discretization, but the core edges are consistent across both.

![](outputs\dog\testimage4_dog_compare_sigma1.50.png)  
![](outputs\dog\testimage5_dog_compare_sigma1.50.png)  
![](outputs\dog\testimage6_dog_compare_sigma1.50.png)

## Unsharp Masking

Sharpening was done by subtracting a Gaussian-smoothed image from the original to isolate **high-frequency details**, then adding them back.  

By adjusting the weight α:  
- Small α (1–2): subtle sharpening, improved clarity.  
- Larger α (4–8): strong sharpening, but also amplifies noise and halos.  

**Observation:** Moderate values improve detail (e.g., lunar surface textures). Excessive sharpening exaggerates noise and creates artifacts.

Moon example:  
![](outputs\sharp\moon_sharpen_sigma1.0.png)  
CT example:  
![](outputs\sharp\ct_sharpen_sigma1.0.png)

## Anisotropic Diffusion vs Gaussian

Anisotropic diffusion smooths images while preserving edges, unlike Gaussian smoothing which blurs edges indiscriminately.  

- **Exponential diffusion function:** Reduces noise effectively while maintaining most edge structures.  
- **Reciprocal diffusion function:** Preserves sharp edges even more aggressively but can over-sharpen or create patchy regions.  

Compared to Gaussian smoothing, anisotropic diffusion provides clearer boundaries while still reducing noise.  

**Limitation:** Requires careful tuning of parameters (K, iterations). Too many iterations oversmooth the image; too few leave noise.  
**Possible improvement:** Hybrid methods combining anisotropic diffusion with modern edge-preserving filters (e.g., bilateral filtering or non-local means).

![](outputs\aniso\noisytestimage1_aniso_vs_gauss_K20.0_it15_lam0.2_sig1.5.png)  
![](outputs\aniso\noisytestimage2_aniso_vs_gauss_K20.0_it15_lam0.2_sig1.5.png)


