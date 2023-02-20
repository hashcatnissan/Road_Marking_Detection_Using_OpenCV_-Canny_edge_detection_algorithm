# Importing the required libraries
from google.colab import drive
import cv2
from google.colab.patches import cv2_imshow
import numpy as np

# Mounting Google Drive file system to the Colab runtime environment
drive.mount('/content/drive')

# Setting the current working directory to a specific folder in the mounted Google Drive, where the input image file is located
%cd /content/drive/My Drive/Colab Notebooks

# Loading the input image using the cv2.imread() function and displaying it using the cv2_imshow() function
image = cv2.imread('test_image.jpg')
cv2_imshow(image)

# Waiting for user input to close the image window
cv2.waitKey(0)

# Closing all the windows
cv2.destroyAllWindows()

# Creating a copy of the input image and converting it to grayscale using cv2.cvtColor() function
laneline_image = np.copy(image)
gray_conversion = cv2.cvtColor(laneline_image, cv2.COLOR_RGB2GRAY)

# Displaying the grayscale image using the cv2_imshow() function
cv2_imshow(gray_conversion)

# Waiting for user input to close the image window
cv2.waitKey(0)

# Closing all the windows
cv2.destroyAllWindows()

# Applying Gaussian blur to the grayscale image using cv2.GaussianBlur() function to remove noise
blur_conversion = cv2.GaussianBlur(gray_conversion, (5,5), 0)

# Displaying the smoothed image using the cv2_imshow() function
cv2_imshow(blur_conversion)

# Waiting for user input to close the image window
cv2.waitKey(0)

# Closing all the windows
cv2.destroyAllWindows()

# Applying Canny edge detection algorithm on the smoothed grayscale image using cv2.Canny() function
canny_conversion = cv2.Canny(blur_conversion, 50, 155)

# Displaying the resulting edges using the cv2_imshow() function
cv2_imshow(canny_conversion)

# Waiting for user input to close the image window
cv2.waitKey(0)

# Closing all the windows
cv2.destroyAllWindows()



The code first imports the required libraries - "drive" and "cv2" - to enable file system mounting and image processing. The "cv2_imshow" function is imported from the "google.colab.patches" library for displaying images.

The code then mounts the Google Drive file system to the Colab runtime environment using the "drive.mount()" function, and sets the current working directory to the folder where the input image is located.

The input image is loaded using the "cv2.imread()" function, and displayed using the "cv2_imshow()" function. The "cv2.waitKey()" function is called to wait for user input to close the image window, and the "cv2.destroyAllWindows()" function is called to close all windows.

A copy of the input image is created using the "np.copy()" function, and converted to grayscale using the "cv2.cvtColor()" function. The grayscale image is displayed, and the "cv2.waitKey()" and "cv2.destroyAllWindows()" functions are called to wait for user input and close all windows.

Gaussian blur is applied to the grayscale image using the "cv2.GaussianBlur()" function to remove noise, and the smoothed image is displayed. The "cv2.waitKey()" and "cv2.destroyAllWindows()" functions are called to wait for user input and close all windows.

The Canny edge detection algorithm is applied to the smoothed grayscale image using the "cv2.Canny()" function, and the resulting edges are displayed. The "cv2
