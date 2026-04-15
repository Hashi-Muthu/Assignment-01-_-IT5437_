# Assignment-01-_-IT5437_
IN4640 Assignment 1 on Intensity Transformations and
Neighborhood Filtering
Ranga Rodrigo
March 22, 2026
1. Apply the following intensity transform to the image in Fig. 1:
Figure 1: Runway image for 1.
(a) Gamma correction with γ = 0.5.
(b) Gamma correction with γ = 2.
(c) Contrast Stretching (linear piecewise transformation)
s(r) =



0, r < r1,
r − r1
r2 − r1
, r1 ≤ r ≤ r2,
1, r > r2,
where
r : input pixel intensity, normalized to the range [0,1].
s(r) : output pixel intensity after contrast stretching.
r1 = 0.2, r2 = 0.8
2. Consider the image shown in Fig. 2
1
.
(a) Apply gamma correction to the L plane in the L
∗a
∗b
∗
color space and state the γ value.
(b) Show the histograms of the original and corrected images.
3. Write your own function to equalize the histogram of an image. Apply this function to the
runway image.
1
Figure 2: Image for gamma correction.
Figure 3: Woman standing in front of an open door.
4. Fig. 3 is a photo of a woman standing in front of an open window
2
. Convert this to grayscale.
(a) Use Otsu thesholding to obtain the binary mask for the foreground comprising the
woman and the room. Report the resulting threshold value.
(b) Carry out histogram equalization only for the foreground region. What are the hidden
features that are revealed in the resulting image?
5. Gaussian filtering:
(a) Using NumPy, compute a normalized 5×5 Gaussian kernel for σ = 2.
(b) Visualize a 51×51 computed Gaussian kernel as a 3D surface plot, where the kernel
coefficients represent the height.
(c) Apply Gaussian smoothing to a given grayscale image using the manually computed
Gaussian kernel.
(d) Do the same using OpenCV’s built-in cv.GaussianBlur() function.
6. Derivative of Gaussian:
(a) Consider the two–dimensional Gaussian function
G(x, y) =
1
2πσ2
exp
µ
−
x
2 + y
2
2σ2
¶
.
1https://www.adobe.com/creativecloud/photography/discover/highlights-and-shadows.html
2Ronak Valobobhai, https://unsplash.com/photos/a-woman-standing-in-front-of-an-open-door-6YzA45_
b2vA.
2
Show that its first–order partial derivatives are given by
∂G
∂x
= −
x
σ2
G(x, y),
∂G
∂y
= −
y
σ2
G(x, y).
(b) Using NumPy, compute normalized 5×5 kernels corresponding to the derivatives of a
Gaussian for σ = 2 in the x- and y-directions.
(c) Visualize a 51×51 derivative-of-Gaussian kernel (for either the x or y direction) as a
3D surface plot, where the kernel coefficients represent the height.
(d) Apply the computed derivative-of-Gaussian kernels to a given grayscale image to obtain
the image gradients in the horizontal and vertical directions.
(e) Using OpenCV, compute the image gradients by applying cv.Sobel(). Compare the
results with those obtained above and comment on any observed differences.
7. Write a program to zoom images by a given factor s ∈ (0,10]. You must use a function to
zoom the image, which can handle
(a) nearest-neighbor, and
(b) bilinear interpolation.
I have included several images, large originals, and their zoomed-out versions. Test you
algorithm by computing the normalized sum of squared difference (SSD) when you scale-up
the given small images to match the size of the large original images. The SSD should be
small when comparing with the original images.
8. Fig. 4 is an image corrupted with salt and pepper noise.
(a) Apply Gaussian smoothing.
(b) Apply median filtering.
Figure 4: Image corrupted with salt and pepper noise.
9. Carry out image sharpening on am image of your choice.
10. Bilateral filtering:
(a) Write a Python function to manually implement a bilateral filter for grayscale images.
Take as input a grayscale image, a kernel diameter, a spatial standard deviation σs,
and a range (intensity) standard deviation σr
3
(b) Apply Gaussian smoothing using OpenCV’s cv.GaussianBlur() function.
(c) Bilateral filtering using OpenCV’s cv.bilateralFilter() function.
(d) Your manually implemented bilateral filter from part (a).
11. Relationship Between Spatial Filtering and Frequency Response
3
:
Consider a 2D image f (x, y) and a filter h(x, y), where the filtered image is
g(x, y) = f (x, y)∗ h(x, y).
(a) Using the Convolution Theorem, explain how spatial domain filtering corresponds to
an operation in the frequency domain.
(b) For each of the following filters, describe their qualitative effect in the frequency domain
and relate it to their spatial behavior:
• Averaging (box) filter
• Gaussian filter
• Laplacian filter
(c) Explain why Gaussian filtering avoids ringing artifacts compared to an ideal low-pass
filter.
(d) An image is corrupted by high-frequency noise. Justify which of the above filters is
most suitable for noise reduction, using both spatial and frequency domain arguments.
12. Illumination Correction using Homomorphic Filtering
4
:
An image affected by non-uniform illumination can be modeled as:
f (x, y) = i(x, y)· r(x, y),
where i(x, y) represents illumination and r(x, y) represents reflectance.
(a) Explain the significance of this multiplicative model.
(b) Describe how a logarithmic transformation can be used to separate illumination and
reflectance.
(c) Propose an algorithm (or pseudo-code) for homomorphic filtering, including:
• Log transformation
• Frequency-domain filtering
• Inverse transformation
(d) Compare homomorphic filtering with histogram equalization. In what situations would
homomorphic filtering be preferred?
(e) Apply the method to an image of your choice and briefly comment on:
• Illumination correction
• Contrast enhancement
• Any artifacts observed
GitHub Profile
You must include the link to your GitHub (or some other SVN) profile, so that I can see that you
have worked on this assignment over a reasonable duration. Therefore, make commits regularly.
However, I will use only the pdf for grading to save time.
3Needs knowledge beyond what was covered in class.
4Needs knowledge beyond what was covered in class. Optional.
4
Submission
Upload a report (eight pages or less) named as your_index_a01.pdf. Include the index number and
the name within the pdf as well. The report must include important parts of code, image results,
and comparison of results. The interpretation of results and the discussion are important in the
report. Extra-page penalty is 20 marks per page.
5
