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

My pipeline consisted of 6 steps. First, I converted the images to grayscale, then I did gaussian blurring. After that I did cany edge detection with low and high threshold at 50 and 150, respectively. Then I selected region of interest with pre-defined vertices through a few trial and errors. After that, I did Hough transformation and created the line images. Finally I overlapped the hough line image with the original image to create the output.

In order to draw a continuous line from bottom to where road ends in the images, I modified the draw_lines() function by calculating the slope and intercept first. Based on the direction of the slope, I set the y-value to the bottom edge in the image and then calculated the corresponding x-value. Then draw the new line based on these new (x,y).


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be when there's big turn on the road, the bounding box will not be where the road's location is.

Another shortcoming could be if there is other line-shaped object in the video. I noticed there's some ghost white horizontal reflection in the second video clip and the program is catching it as a line too. 


### 3. Suggest possible improvements to your pipeline

A possible improvement for the first problem would be to detect if there's a huge deviation in the road line slope. When there is, redo the region of interest accordingly.

A possible improvement for the second problem is also by detecting the slope and remove any extreme cases like slope=0 or slope=ifinity (i.e. horizontal or vertical ghost lines caused by video defects). 


