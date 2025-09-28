How to Run the Code
-------------------
1. Install dependencies: numpy, matplotlib, opencv-python
   pip install numpy matplotlib opencv-python

2. Example usage:

   # Part 1: Perspective vs Ortho
   python src/main.py --task part1 --images images/desk_close.jpg images/desk_far.jpg --outdir outputs --write-note

   # Part 2: Histogram Equalization
   python src/main.py --task hist_eq --images images/testimage1.png --outdir outputs/histEQ
   python src/main.py --task hist_eq --images images/testimage2.png --outdir outputs/histEQ
   python src/main.py --task hist_eq --images images/testimage3.png --outdir outputs/histEQ
   python src/main.py --task hist_eq --images images/solarisDark.png --outdir outputs/mine

   # Part 3: Histogram Matching
   python src/main.py --task hist_match --images images/testimage1.png images/testimage2.png images/testimage3.png --target images/target.png --outdir outputs/match

   # Part 4: Derivative of Gaussian
   python src/main.py --task deriv --images images/testimage4.png images/testimage5.png images/testimage6.png --outdir outputs/dog

   # Part 5: Sharpening
   python src/main.py --task sharpen --images images/moon.png images/ct.png --outdir outputs/sharp

   # Part 6: Anisotropic Diffusion
   python src/main.py --task aniso --images images/noisytestimage1.png images/noisytestimage2.png --k 20 --iters 15 --lam 0.2 --sigma 1.5 --outdir outputs/aniso

3. Outputs will appear in the specified --outdir.
