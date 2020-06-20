# **Finding Lane Lines on the Road** 

## Writeup Template

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

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I .... 
1. Convert the image in Grayscale
2. Pass Gaussian Filter to make it smooth for canny to find good edges minimal noise
3. Pass Blur image to Canny Edge Detection
5. Prepare a mask with white Lane lines and only on region of interest i.e front where lane will appear
6. use hough lines to get coordinates of line
7. Divide those points by slope < 0 will be left lane line and others will be right
8. Average the points of left and right lanes respectively
9. once you have a points extrapolate throught in region of interest
10. Draw Lines on Image
11. Use this pipeline to provide frame by frame image and get result of image with lane lines marked

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Cannot Find Cuve Lane Lines
Not Reliable as will not work in all lighting condition
Corners , Roundabouts will not be marked as line is linear

### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

we can use Polynomial Line and instead of Linear
Find Lane Line Small block by block instead of just taking mean and extrapolating as it causes line to fluctuate a alot
