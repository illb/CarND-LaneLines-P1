#**Finding Lane Lines on the Road** 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

---

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 6 steps.

* mask white and yellow pixels
* convert to gray scale
* blur the image
* canny edge detection
* mask region of interest
* find lines with hough

My modified draw_lines() function

* separate left and right lines
* remove noise
  * sum the vectors to find the mean slope
  * eliminate lines much off the average slope
* merge lines
  * predict with a single line using linear regression

###2. Identify potential shortcomings with your current pipeline

* cannot detect lanes like belows
  * shady lanes
  * too bright or too dark image source
* need calibration when camera shaking

###3. Suggest possible improvements to your pipeline

* use deep neural network to detect lane segments and objects
  * linear regression with lane segment centers
  * ensemble the results