# **Finding Lane Lines on the Road** 

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./test_images_output/solidWhiteCurve.jpg "test image"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps:

1) Converting to grayscale.
2) Applying Canny Edge Detection.
3) Cut the image polygon style to obtain the relevant part of the image.
4) Using the Hough transformation to obtain the lines out of the image. 
5) Overlay the lines with the initial image to see the detected lines.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function.
I left the initial lines in blue to see the edge detection.
After that I separated the lines by their slope in left and right lines. The coordinates were stored in a new array.
I used the numpy function polyfit to approximate the lines and the relevant paramters for a polynom of first degree.
After that it is possible to calculate the x-values with some choosen y-values and also to plot the final lines.
I have choosen the color green for right and red for left.

![alt text][image1]

### 2. Identify potential shortcomings with your current pipeline

One potential shortcoming would be what would happen when there is no line detected. It would end with an error.

Another shortcoming could be that the lane detection is only valid for straight lanes.

The function is not very robust when there are horizontal lines (street damage camera error) in the image.

### 3. Suggest possible improvements to your pipeline

It would be advisable to check the solutions between the steps to check e.g. for empty arrays.

It would be possible to change the polynom in a higher degree.

It is possible to improve computing e.g. cut the relevant part of the image earlier to reduce data.

It would be possible to connect the lane detection loops and the results to make the function more robust.

