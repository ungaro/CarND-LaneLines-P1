
**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report



[//]: # (Image References)

[image1]: ./examples/lanelines_all.jpg "LaneLines"

![alt text][Lanelines]




---

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of these steps:

* Convert the images to grayscale
* Apply Gausian Blur 
* Apply Canny edge detection
* Region of interest and masking
* Apply Hough Transform to detect lane lines
* Superimpose the lane lines on the original image

In order to draw a single line on the left and right lanes, I first modified the draw_lines() function by:

* Calculated slope and center of each line. Then based on the slope, sort it into right or left lane line
* Calculate the average slope and the center of right and left lane
* Then using the Y coordinates, based on Region of Interest, figure out the X cordinates using the avg slope and center point of lane lines [equation used: (y-y') = M (x-x')]

then found a better vectorised solution as previously mentioned by https://github.com/yapjiaqing/CarND-LaneLines-P1/blob/master/P1.ipynb)



###2. Identify potential shortcomings with your current pipeline

Potential shortcomings of my approach:


Slope conditions used for detecting right and left lanes do not work in case of a curve in the road
Region of Interest is hard coded.



###3. Suggest possible improvements to your pipeline

Possible improvements to my approach:

Make Region of Interest dynamic
Modify the slope conditions, so that they work with curve in the road