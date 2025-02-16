# convert-an-image-into-a-pencil-sketch-effect.
This Python script uses OpenCV (cv2) to convert an image into a pencil sketch effect. (Image processing)

image = cv2.imread('cute.jpg')
gray_image = cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
cv2.imwrite('cute_gray.jpg',gray_image)

inverted = 255-gray_image
blurred = cv2.GaussianBlur(inverted,(21,21),0)
cv2.imwrite('cute_blur.jpg',blurred)

invertedblur = 255-blurred
pencilsketch = cv2.divide(gray_image,invertedblur,scale = 256.0)
cv2.imwrite('cute.jpg',pencilsketch)
