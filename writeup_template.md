# **Finding Lane Lines on the Road**

## Writeup Report

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

My pipeline consisted of 5 steps.
1. I converted the images to grayscale,
2. I did a GaussianBlur to remove the noises
3. I used the canny transform to find the edges
4. Use the hough transform to find the Lines
5. Overlay the found lines on the original images

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by calculating the average slope and center of the lines and separating the left lines from the right lines. Then I used the slope and center to extrapolate the right/left lines and drew a single right/left line.

Here's an example with the lines drew on solidWhiteCurve.jpg:

[image1]: ./test_images/output.jpg "Output"


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when there's a big curve in the road, the lines are not detected very well.  

Another shortcoming could be when there's a object in front of my car, the line detection could be affected.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to do a better filtering on the slope of the detected lines.

Another potential improvement could be to use color filter. 
