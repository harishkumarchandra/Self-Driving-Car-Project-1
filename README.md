# **Finding Lane Lines on the Road** 

![](https://raw.githubusercontent.com/ypwhs/resources/master/white.gif)

---

### Reflection

### 1. Pipeline Discription:

1. Converting image to grayscale
2. Applying a Gaussian blur to the image
3. Applying Canny edge detection
4. Masking the image so that only the region of interest is processed
5. Running the Hough transform to identify lines
6. Converting those lines into straight lines
7. Smoothing the result with a moving average filter
8. Plotting the lines on top of the image

In order to draw a single line on the left and right lanes, I created the function draw_straight_lines().
This function works as follows:
1. Separate the right and left line based on their slope
2. Average the line ending x,y coordinates for each side
3. Calculate the slope and intercept of each average line
4. Using the slope and intercept, extend the lines to the bottom and apex of the lane
5. Update the moving average of the last few lines and the new lines
6. Plot the moving average lines

### 2. Potential shortcomings:

1. While this pipeline works on the first two videos, I am getting a error on the optional third video. 
2. At intersections with sharp angles, the code cannot draw over the entire lane marking.

### 3. Possible improvements 

1. One improvement would be cleaner code.
2. If matrix math (NumPy) was used more often, this code could probably be more efficient and compact.
3. The optimal parameters for Gaussian smoothing, the Hough transform, moving average, etc.
