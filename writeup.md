# **Finding Lane Lines on the Road** 

## Writeup

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of below 5 steps - 
- 1. Converted the images to grayscale.
- 2. Applied Gaussian smoothing with kernel_size 5.
- 3. Applied Canny to detect edges with low_threshold = 50 & high_threshold = 150.
- 4. Defined a four sided polygon to mask and created masked image.
- 5. Finding lines using Hough on edge detected image & drew the lines.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by seperating the left lines and right lines by their negative & positive slope. Then I averaged the left & right lines to compute the left line points (with left lane slope & intercept) & right line points (with right lane slope & intercept). I also changed the thickness paramter to 12.

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![solidWhiteCurve][test_images_output/solidWhiteCurve.png]

![solidYellowCurve][test_images_output/solidYellowCurve.png]

### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when there is no lane lines.

Another shortcoming could be detecting curved lane lines


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to draw a fix line when there is no lane lines.

Another potential improvement for deteting curved lane lines could be to use polynomials.
