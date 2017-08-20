# **Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./test_images_output/gray.jpg "Grayscale"
[image2]: ./test_images_output/blur.jpg "Gaussian Smoothing"
[image3]: ./test_images_output/canny.jpg "Canny Edges"
[image4]: ./test_images_output/region.jpg "Region of Interest"
[image5]: ./test_images_output/hough.jpg "Hough Transform"
[image6]: ./test_images_output/result.jpg "Result"
[image7]: ./test_images_output/raw_solidWhiteCurve.jpg "Result"

---

### Reflection

### 1. Pipeline Description

My pipeline consisted of 6 steps:

1. Convert the image to gray scale.
![alt text][image1]
2. Blur the grayscale image with ``gaussian_blur`` with kernel size 7.
![alt text][image2]
3. Canny edges detection with threshold ratio of 1:3.
![alt text][image3]
4. Set the region of interest
![alt text][image4]
5. Apply the Hough transform, the parameters were modified until a satisfactory result.
6. Draw the lines in the original image. Resulting the final image:
![alt text][image7]

### 2. Drawing the lane lines

In order to draw a single line on the left and right lanes, the new ``draw_lane_lines_from_hough`` function gets all detected rough lines and performs the following steps to draw the lane lines:

1. For each rough line, determines by its slope if it is a right side line (positive slope) or left side line (negative slope).
2. Finds the average left line and the average right line.
3. Calculates the intersection points of the average lines and a horizontal line passing through the top of the region of interest, and the intersection points of the average lines and the horizontal line of the bottom of the image.
4. Draws the lines between the calculated intersection points.
![alt text][image5]

Resulting in the processed image, with the lane lines detected:
![alt text][image6]


### 2. Potential shortcomings

One potential shortcoming would be what would happen when the Hough transform returns no lines or scrambled lines by any reason as occurred in the challenge video. To pass through this problem, the pipeline draws the average lines of the last frames, but it has a limit, if no lines are detected in a relative large amount of time the pipeline could not detect the lane lines appropriately.


### 3. Possible improvements

A possible improvement would be to create a sample distribution of the detected lines and use statistic methods to calculate the lane lines position probabilities, instead of a simple mean of the line positions.
