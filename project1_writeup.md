#**Finding Lane Lines on the Road** 

##Writeup Template

###You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


![reference final result] (/output images/MAUsolidWhiteRight.jpg)


---
### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. 
First, I converted the images to grayscale
Second, I passed a Gaussian smoothing with a kernel of 5.
Third I applied a Canny edge detection function to all the image.
Forth I applied a polygonal mask to identify the left and right edges of the lanes.
Fifth I applied the Hough transform to detect the segments of the lanes.

![reference first result] (/output images/MAUsolidWhiteInitial.jpg)

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


###2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


###3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
