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


