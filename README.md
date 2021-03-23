# Object-Detection-with-SSD

In this project, a pre-trained Single Shot MultiBox Detection model is implemented to perform object detection on videos! 
To download the model, please follow this link as the file is too large to upload on github: https://drive.google.com/file/d/1yk85VYhQNFyy0Vgkw1pliJIUWV9mE6G4/view?usp=sharing

## SSD Basics
Similar to YOLO, SSD looks at the whole image only once and divides the full image into regions, calculating classification probabilities for each region.
This is what makes SSD different from basic CNN classification, as the location of the object must be known within the image. As such, it can be thought of each region within the whole image as a separate image, undergoing a CNN to classify whether the region is an object of interest or not.
For this Deep Learning model, PyTorch and OpenCV were used to take each frame and feed them into the pre-trained SSD model

## Detect Function
The purpose of the Detect function is take the frames of the video and convert them into Torch variables that the SSD model can accept. To do this, we first grab the frame in a numpy array, then convert this numpy array into a torch tensor. A fake batch dimension is then added to the torch tensor, which is finally converted into a Torch Variable that will be fed into the SSD model.
In addition, this function will also use OpenCV to create a red rectangle around the detected object region in each frame.

## Processing
Upon loading the pre-trained neural network, the transformations required to get the correct size and colour scales were applied to the frames.
A for loop was then utilized to go through all the frames in the input video, apply the Detect Function, and output a new video with the SSD object detections.

## Results
Please find the results in the following link: https://hjmok.github.io/josephmok_portfolio/#/SSD
