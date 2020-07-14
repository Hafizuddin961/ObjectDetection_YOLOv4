# ObjectDetection_YOLOv4
This project use YOLOv4 architecture to detect multiple object in image or video. 

# YOLOv4
Briefing a little bit on YOLOv4 and object detection architecture.<br>
Object detectors typically compose of several components, which are the:
1) Input
2) Backbone
3) Neck
4) Head

### 1) Input
This is where image input

### 2) Backbone
There was a choice Between CSPResNeXt50, CSPDarknet53, and EfficientNet B3 — based on theoretical justification and several experiments CSPDarknet53 neural network was shown to be the most optimal model. This project is using Darknet framework

### 3) Neck
sub-sets of the backbone, where the serves to enhance the feature discriminability and robustness using the likes of FPN, PAN, RFB etc, and the

### 4) Head
handles the prediction. This can be either using a one stage detector for dense prediction like Yolo and SSD or a two-stage detector also known as Sparse Prediction — with FRCNN and Mask RCNN

![](https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/head.png)

# Start the Detection!!!
There are some trained datasets that available to use without need to train the the data. At first for this project, the object will detect using COCO dataset where about 80 classes already be trained and the precision quite good.<br>
<br>
For the MS COCO experiments the hyper parameters were as follows:
* Training steps of 500,500
* Learning rate of 0.01 using a step decay learning rate scheduling strategy.
* These learning steps were multiplied by a factor of 0.1 at 400k steps and 450k steps respectively.
* Momentum and weight decay of 0.9 and 0.005 respectively.

# Result on Detection using COCO trained dataset

![](https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_coco/test2.png)
![](https://github.com/Hafizuddin961/Object-detection-YOLOv3/blob/master/result/melaka_medal.png)
![](https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_coco/result.gif)

# My Custom Object Detection
There are a few step to prepare data and configuration before can be trained using YOLOv4. Here are summarize for the step:
### 1) Data Collection 
I using Google's Open Images Dataset to collect the data since they already been labeled and segmented but only limited classes only https://storage.googleapis.com/openimages/web/index.html.<br>
For this project, I decided to detect 17 classes of food which are:
1) Apple 
2) Banana 
3) Bread 
4) Broccoli 
5) Burrito 
6) Cake 
7) Candy 
8) Coffee 
9) Doughnut 
10) Ice cream 
11) Muffin 
12) Pizza 
13) Potato
14) Tomato
15) Vegetable
16) Waffle 
17) Watermelon 

### 2) Data Preparation
Convert annotation from Google's Open Images into YOLO format

### 3) Configure the YOLO
The configuration is crucial to get high accuracy, availability for GPU memory to train, etc.

### 4) Train custom data set
The training time depend on number of iteration, image size, number of image, etc. For this project, it takes about 12 hour to get until 6000+ iteration

# Evaluation of training data
Each 1000 iteration was evaluate to see the performance of the model. The result as follow:

### For 4000 iteration
![](https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_image/iteration_4000/result_4000.JPG)<br>
This result shown the Mean Average Precision (mAP): 53%

### For 5000 iteration
![](https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_image/iteration_5000/result_5000.JPG)<br>
This result shown the Mean Average Precision (mAP): 58.76%

### For 6000 iteration
![](https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_image/iteration_5000/result_5000.JPG)<br>
This result shown the Mean Average Precision (mAP): 60.42%

### For 6000+ iteration
![](https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_image/iteration_5000/result_5000.JPG)<br>
This result shown the Mean Average Precision (mAP): 52.73%

# Evaluation using image
Even though 6000 iteraion shows highest precision, sometime weight on 4000 iteration outperformed some weight when I test it using input custom image. This probably happened because the validation image was not equally distributed since validation on Google's Open Image were limited. Here the result after I test using my own image:

### For 4000 iteration:

<p align="center">
  <img src="https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_image/iteration_4000/test1_4000_thresh0.png" width="426px" height="240px"/>
  <img src="https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_image/iteration_4000/test2_4000_thresh0.png" width="426px" height="240px"/>
    <img src="https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_image/iteration_4000/test3_4000_thresh0.png" width="426px" height="240px"/>
    <img src="https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_image/iteration_4000/test4_4000_thresh0.png" width="426px" height="240px"/>
    <img src="https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_image/iteration_4000/test5_4000_thresh0.png" width="426px" height="240px"/>
    <img src="https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_image/iteration_4000/test6_4000_thresh0.png" width="426px" height="240px"/>
</p>

### For 5000 iteration:

<p align="center">
  <img src="https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_image/iteration_5000/test1_5000_thresh0.png" width="426px" height="240px"/>
  <img src="https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_image/iteration_5000/test2_5000_thresh0.png" width="426px" height="240px"/>
    <img src="https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_image/iteration_5000/test3_5000_thresh0.png" width="426px" height="240px"/>
    <img src="https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_image/iteration_5000/test4_5000_thresh0.png" width="426px" height="240px"/>
    <img src="https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_image/iteration_5000/test5_5000_thresh0.png" width="426px" height="240px"/>
    <img src="https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_image/iteration_5000/test6_5000_thresh0.png" width="426px" height="240px"/>
</p>

### For 6000 iteration:

<p align="center">
    <img src="https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_image/iteration_6000/test3_6000_thresh0.png" width="426px" height="240px"/>
    <img src="https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_image/iteration_6000/test4_6000_thresh0.png" width="426px" height="240px"/>
    <img src="https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_image/iteration_6000/test5_6000_thresh0.png" width="426px" height="240px"/>
    <img src="https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_image/iteration_6000/test6_6000_thresh0.png" width="426px" height="240px"/>
</p>

### For 6000+ iteration:

<p align="center">
  <img src="https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_image/iteration_6000+/test1_6000+_thresh0.png" width="426px" height="240px"/>
  <img src="https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_image/iteration_6000+/test2_6000+_thresh0.png" width="426px" height="240px"/>
    <img src="https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_image/iteration_6000+/test3_6000+_thresh0.png" width="426px" height="240px"/>
    <img src="https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_image/iteration_6000+/test4_6000+_thresh0.png" width="426px" height="240px"/>
    <img src="https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_image/iteration_6000+/test5_6000+_thresh0.png" width="426px" height="240px"/>
    <img src="https://github.com/Hafizuddin961/ObjectDetection_YOLOv4/blob/master/test_image/iteration_6000+/test6_6000+_thresh0.png" width="426px" height="240px"/>
</p>
