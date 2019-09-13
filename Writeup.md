# **Finding Lane Lines on the Road** 

## Writeup 


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

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I did cany edge detection with low and high threshold at 50 and 150, respectively. Then I selected region of interest with pre-defined vertices through a few trial and errors. After that, I did Hough transformation and created the line images. Finally I overlapped the hough line image with the original image to create the output.

In order to draw a continuous line from bottom to where road ends in the images, I modified the draw_lines() function by calculating the slope and intercept first. Based on the direction of the slope, I set the y-value to the bottom edge in the image and then calculated the corresponding x-value.


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
