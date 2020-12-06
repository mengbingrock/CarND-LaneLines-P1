# **Finding Lane Lines on the Road** 


**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I Apply the Canny dege detection and mask to select only the area that are interested. After applying the Hough Transform, mutiple lines could be get. Then apply the draw_lines() function to add lines to the graph.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function first caculating to average slope and x value and y values of each line found by Hough Transform. Then I added new line using the average slope and the average of x and y values to the bottom of the picture.. I did not extend the line to the top direction because I belief the line is long enough.

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline

As I did not remove lines but add new line to the existing lines found by Hough Transform. There might be some lines on the edge of the road painted out.

One potential shortcoming would be what would happen when large curvature is meet, there is possibility that right line have the inverted slope which could be recognized as left lines.



### 3. Suggest possible improvements to your pipeline

A possible improvement would be to instead of extend the line with the average slope, we could try connect the lines with neighbor lines, to resolve for the large curvature.

And to overcoming the noises, we try to average over time or spaces.

