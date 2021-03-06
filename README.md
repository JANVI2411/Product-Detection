<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <br> 
    <li><a href="#product-detection">Product Detection using Yolov4</a></li>
    <li><a href="#output-of-the-yolo-model">Output of the Yolo Model</a></li>
    <li><a href="#product-classification">Product Classification</a></li>
  </ol>
</details>

## Product Detection:
#### mAP : 0.90

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1m0tyYgvedOYufOlRcGjJW5UzkPxEgWM7?usp=sharing)
    
    I have trained the yolov4 model using the product dataset with 0.90 mAP.
    
    Dataset Preparation:
    1. Created "txt" files containing the coordinates of the bounding boxes for each image.
    2. Txt file format : class mid_x mid_y width height \n class mid_x mid_y width height ... for n items/image.
    3. The bounding box is normalized by Image's width and height.
    4. Created a configuration file with class=1, as we are only interested in product/no_prodct detection.
    
    Training:
    1. Trained the network for 1000 epochs.
    
    Evaluation:
    1. Calculated Precision, Recall and mAP.

## Output of the Yolo Model:

The below shown are the detected bounding boxes on the image. Please visit the Drive link to checkout more Output Images.
[Drive Link](https://drive.google.com/drive/folders/1x5H6Xn3B3Ha-t2uFy1NsouqSFxZC53Mk?usp=sharing)
<br>
<br>
<img src='./output_images/C1_P04_N1_S4_1.JPG' width=400>
<img src='./output_images/C1_P05_N2_S4_2.JPG' width=400>

## Product Classification:
#### Test Data Accuracy: 99.97%

<br>

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1Ay6A9mb1PeaiWLB9Oh-79XtckLuXfAc5?usp=sharing)
<br>
[Drive Folder of Augmented Images](https://drive.google.com/drive/folders/1btYOQfTe7QTFAMuf8ljPsvsTryisBbXB?usp=sharing)

    I also implemented classification model for products using GroceryDataset_part1/ProductImages Dataset, but I observed many product categories on the shelf are not available in the provided Dataset.
    
    Dataset Prepartion:
    1. Created Dataloader using Tensorflow "tf.data".
    2. Image Augmentation (Random flip, rotation, saturation, centre_zoom) (Drive link has been provided) 
    
    Training:
    1. Implemented Tranfer Learning. 
    2. Took an Inceptionv3 model and added a Dense layer of 10 neurons at the tail of the network.
    3. Trained it for 5 epochs and achieved 99% accuracy on Training dataset.
   

