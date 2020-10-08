# SSD: Single Shot MultiBox Object Detector

## Installation
Follow this [repository](https://github.com/amdegroot/ssd.pytorch) to set up the SSD PyTorch version on your system.

## Dataset Preparation
PreProcessing.ipynb walks you through the dataset preparation steps.

Dataset Directory Strucure (PASCAL VOC 2007):

VOCdevkit/
    VOC2007/
        Annotations/ (.xml files of the 354 images)
        ImageSets/
            Main/
                train.txt (list of train image filenames)
                test.txt (list of test image filenames)
        JPEGImages/ (354 .JPG images)

## Dataset Augmentation
- Photometric Distortions
    - Random Contrast
    - Random Saturation
    - Random Hue
    - Random Brightness
    - Random Lighting Noise
    - Convert Colour Spaces
- Expand
- Random Sample Crop
- Random Mirror

## Detection Network, Package Versions and Pretrained Model
Detection Network: SSD300-VGG16
Package Versions: PyTorch 1.0.0, Torchvision 0.2.1, Pillow 6.1
Pretrained Model: https://s3.amazonaws.com/amdegroot-models/ssd300_mAP_77.43_v2.pth

## Hyperparameters and Anchor Tuning
Batch Size: 32
Initial Learning Rate: 1e-3
Momentum: 0.9
Weight decay for SGD: 5e-4
Gamma update for SGD: 0.1

In the original code:
Number of Anchor Boxes - 6 {Aspect Ratios: 1, 2, 3, 1/2, 1/3 and another 1:1 aspect ratio box}
Total Number of Boxes - 38x38x4 + 19×19×6 + 10×10×6 + 5×5×6 + 3×3×4 + 1×1×4 = 8732

In this exercise:
Number of Anchor Boxes - 1 {Aspect Ratio: 0.65}
Total Number of Boxes - 38x38x1 + 19×19×1 + 10×10×1 + 5×5×1 + 3×3×1 + 1×1×1 = 1940

Average of all bounding box width and height is: (201.353, 308.988 =)
This ratio is approximately 0.65. Hence, this was chosen as the aspect ratio of the single anchor box.

## Q&A
