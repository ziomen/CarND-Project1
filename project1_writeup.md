#**Finding Lane Lines on the Road** 

---

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

---
### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

#My pipeline consisted of 5 steps. 

First, I converted the images to grayscale, to have a better contrast from the background.

Second, I passed a Gaussian smoothing.

Third I applied a Canny edge detection function to all the image.

Forth I applied a trapezoidal mask to isolate the region of interest including only the left and right edges of the lanes.

Fifth I applied the Hough transform to detect the segments of the lanes.

Below an example of the first pass annotated original image.

![reference first result] (/output images/MAUsolidWhiteRight_initial.jpg)


At this point in order to draw a single line on the left and right lanes, I modified the draw_lines() function by:

* Collected all the points of the detected segments sepaarating left and right x and y coordinates. In order to do that, I calculated the slope and I collected all the positive slopes as the right lane and the negative slopes as the left lane.

* Calculated the polynomial fit using the np.polyfit () function for both the right and the left lanes

* Extrapolated the lane marking for the right and left lanes using the polynomial fit of the first order using np.poli1D

Below an example of the refined annotated original image.

![reference final result] (/output images/MAUsolidWhiteRight.jpg)

###2. Identify potential shortcomings with your current pipeline

I used positive and negative slopes to separate the right and left lines. It works well on the test images where the lanes are pretty well separated and in the center of the image. In case of curves or in case of single lane or crossing lanes etc. this would not be applicable.

I also applied the line fucntion to the point img.shape[] to determine the coordinates at the bottom of the image to make sure that the whole lane was always annotated. 

###3. Suggest possible improvements to your pipeline

To anticipate the definition and apply the region of interest before the Canny Edge detection, to work on a smaller set and reduce the non relevant artifacts.

Work on preprocessing to remove noise from the edge detection to mitigate the effect of artifacts.
