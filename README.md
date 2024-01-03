# CodeClauseInternship_ImagetoPencilSketch-
Python script uses the OpenCV library to perform a simple image processing operation, transforming an input image into a pencil sketch.  Reads the input image named "flower.jpg" using OpenCV. 


Convert to Grayscale:
	gray_image = cv2.cvtColor(image, cv2.COLOR_RGB2GRAY): Converts the original image to grayscale.



Invert Grayscale Image:
	inverted = 255 - gray_image: Inverts the grayscale image by subtracting each pixel value from 255.



Blur Inverted Image:
	blury_image = cv2.GaussianBlur(inverted, (23, 23), 0): Applies Gaussian blur to the inverted image. The kernel size is (23, 23), and the standard deviation is 0.



Invert Blurred Image:
	blury_inverted = 255 - blury_image: Inverts the blurred image.


Create Pencil Sketch:
	pencil_sketech = cv2.divide(gray_image, blury_inverted, scale=250): Divides the grayscale image by the inverted blurred image, creating a pencil sketch effect.


Display Images:
	cv2.imshow(image): Displays the original image, grayscale image, inverted image, blurred image, and the final pencil sketch.


Save Pencil Sketch:
	cv2.imwrite("saved image.jpg", pencil_sketech): Saves the pencil sketch as a JPEG image with the filename "saved image.jpg".
