import cv2

image=cv2.imread('C:\\black-background-with-goku-dragon-ball-z.jpg')
cv2.imshow("Tiger",image)


#RESIZE

resized=cv2.resize(image,(300,300))
cv2.imshow("Resized_image",resized)


#ROTATE

rotated=cv2.rotate(resized,cv2.ROTATE_90_CLOCKWISE)
cv2.imshow("Rotated_image",rotated)

#COLOR CONVERSION

color_conversion=cv2.cvtColor(resized,cv2.COLOR_HSV2RGB)
cv2.imshow("New Color",color_conversion)

#GRAY IMAGE

gray_image=cv2.cvtColor(resized,cv2.COLOR_BGR2GRAY)
cv2.imshow("gray Color",gray_image)

#EDGES

edges=cv2.Canny(resized,100,200)
cv2.imshow("edged",edges)

#Image Threshold

binary=cv2.threshold(gray_image,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)[1]
cv2.imshow("Binary_Image",binary)

#Blur

blurred=cv2.GaussianBlur(resized,(35,35),0)
cv2.imshow("Blur_Image",blurred)

#Histogram Equallizer

equalize=cv2.equalizeHist(gray_image)
cv2.imshow("Equalized",equalize)

#Contour

contour,_=cv2.findContours(edges,cv2.RETR_EXTERNAL,cv2.CHAIN_APPROX_SIMPLE)
fin=cv2.drawContours(resized,contour,-1,(0,150,255),1)
cv2.imshow("Contour",fin)




cv2.waitKey(0)
cv2.destroyAllWindows()
import cv2
import numpy as np
image = cv2.imread("C:\\StockCake-Majestic tiger resting_1742191045.jpg")
image = cv2.resize(image,(300,300))
gaussion = cv2.GaussianBlur(image,(7,7),0)
median = cv2.medianBlur(image,5)
bilateral = cv2.bilateralFilter(image,9,75,75)

cv2.imshow("Orginal",image)
cv2.imshow("Gaussion Blur",gaussion)
cv2.imshow("Median Blur",median)
cv2.imshow("Bilateral Filtering",bilateral)

cv2.waitKey(0)
cv2.destroyAllWindows()
