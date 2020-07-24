# ME_YOLO
Customization of YOLO(you only look once) algorithm + state of art loss function(GIOU) for object detection

-**YOLO** 

came on the computer vision scene with the seminal 2015 paper by Joseph Redmon et al. “You Only Look Once: Unified, Real-Time Object Detection,” and immediately got a lot of attention by fellow computer vision researchers.YOLO is a clever convolutional neural network (CNN) for doing object detection in real-time. The algorithm applies a single neural network to the full image, and then divides the image into regions and predicts bounding boxes and probabilities for each region. These bounding boxes are weighted by the predicted probabilities.YOLO is popular because it achieves high accuracy while also being able to run in real-time. below you can see yolo network architecture.

<img src="https://miro.medium.com/max/640/0*WUpMWzNu_ymDyHPp.png">

-**Generalized Intersection over Union**

A Metric and A Loss for Bounding Box Regression

The problem IOU metric for detecting bounding boxes is that ,this loss only addressed the overlapped bounding boxes and will not provide any learning for the non-overlapping cases.As you can see in the formulla below:

<img src="https://miro.medium.com/max/267/1*Ozq8lNLcF-t-90kMfutrVQ.png">

To address this, researchers propose an improvement in the form of additional penalty term to the loss, where C denotes the smallest box that can enclose predicted and ground-truth bounding box and called it Generalized IoU Loss (GIoU)

<img src="https://miro.medium.com/max/424/1*IykYEv4ZTD0_4Ijf2aHFDw.png">

By using this loss, the predicted bounding boxes will try to expand (increase the size ) its prediction towards the ground truth bounding boxes. Thus the prediction can move closer to the correct ones.



**Customizations that was applied by me:**

- *decreasing computation cost of YOLO network by doing them in the preprocessing stage*
- *using only one anchor box that was suggested by K-means algorithm*
- *completely changing Loss function of model using IOU metric*
