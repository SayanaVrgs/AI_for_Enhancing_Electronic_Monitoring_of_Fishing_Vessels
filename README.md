# AI for Enhancing Electronic Monitoring of Fishing_Vessels
![logo](https://github.com/SayanaVrgs/AI_for_Enhancing_Electronic_Monitoring_of_Fishing_Vessels/blob/main/fishboat.jpg)
## Overview

One of the major tasks undertaken at the Department of Fisheries (DoF), Canada is catch monitoring. Catch monitoring provides in depth information about the fishing activities on any given fishing expedition. Despite its advantages, and its global use for monitoring, adoption of electronic monitoring system in major fishing regions is still slow. There are two major challenges for this system’s widespread adoption, namely: 
1. The large storage requirement for the video footage recorded, and
2. The long time required by analysts to review the video footage.
   
A single fishing trip can generate a huge amount of video data. Also, a large amount of time and additional resources would be required to analyse such huge sets of data. Currently, only certain portions of videos (chosen at random or identified due to some discrepancy) are audited for monitoring purpose. Hence, the data provided by the monitoring system is not being utilised efficiently. The need of the hour is an automated solution, using AI, to effectively utilise the data captured by EMs for efficient monitoring purpose.

## Dataset
For this project, the input data was obtained from The Nature Conservancy’s Fishnet Open Images Database, a large dataset of EM imagery for fish detection. The data consists of an image file having over 86000 images and a csv file that provided labels based on the object identified in each of these images. The labels included: Albacore, Bigeye tuna, Black marlin, Blue marlin, Brama, Escolar, Great barracuda, Indo Pacific sailfish, Lancetfish, Mahi mahi, Long snouted lancetfish, Marlin, Mola mola, Oilfish, Opah, Pelagic stingray, Pomfret, Rainbow runner, Shark, Roudie scolar, Shortbill spearfish, Sickle pomfret, Skipjack tuna, Snake mackerel, Striped marlin, Swordfish, Thresher shark, Tuna, Wahoo, Yellowfin tuna, Human, Unknown and NoFish.

## Model used
Convolutional Neural Networks for Object Detection - RetinaNet
Our model was implemented on [Keras RetinaNet](https://github.com/fizyr/keras-retinanet) which is based on the Retinanet architecture. It used pre-trained COCO dataset model to implement this project. The input file for the model is a csv file with only image ID, bounding box and label. A total of four models were created.

## Results and performance
<img align="center" alt="coding_lady" width="800" height="500" src="https://media.tenor.com/S59bPkT0pqcAAAAC/programming.gif">

The above sample image shows the predictions overlayed. Different colour bounding boxes represent different object classes detected.
In order to measure the performance of the models, we used mAP, mean average precision. The mAP compares the ground-truth bounding box to the detected box and returns a score.
The higher the score, the more accurate the model is in its deductions. Table 1 summarises the mAP for the four models.
The below table summarises the mAP for our four models:
|  | Model 1 | Model 2 | Model 3| Model 4 |
| ------------- | ------------- | ------------- | ------------- | -------------|
| Validation Dataset | 24.38%  | 24.38%  | 24.09%  | 40.94%  |
| Test Dataset  | 24.10%  | 24.34%  | 24.12% | 40.13%  |
