# Object Detection Datasets

# 1. Overview
This repo ...

## Annotation types
General annotation types includes: Horizontal B-Box(HBB), Oriented B-Box(OBB), instance segmentation, diamond style, key point<br>
- Horizontal B-Box(HBB)<br>
  - (xmin, ymin, xmax, ymax)
  - (xcenter, ycenter, width, height)
- Oriented B-Box(OBB)<br>
- 
- instance segmentation<br>
- 
- diamond style<br>
    Used in RarePlane dataset. Each aircraft is labeled in a diamond style with annotators instructed to label the nose, left-wing, tail, and right-wing in order. This annotation style has the advantage of being simplistic, easily reproducible, convertible to a bounding box, and ensures that aircraft are consistently annotated as other formats can often lead to imprecise labeling. Furthermore, this annotation style enables us to pull out two valuable features of aircraft: Their length and wingspan.
    ![diamond style](https://www.cosmiqworks.org/wp-content/uploads/2020/04/1_gif.gif#pic_center)

    

# 2. Benchmarks and contests
## Popular benchmarks
- DOTA
- FAIR1M
- ...
## Hot contests
another link


# 3. Public datasets

## Optical
| Dataset     | Categories | Images | Image width | Instances | Annotation |   Source    | Year |
|:-----------:|:-------:|:--------:|:-------------:|:-----------:|:--------------:|:-----------:|:-----:|
| RSOD        | 4       | 976      |               | 6950        | HBB  | Google Earth, Tianditu | |
| NWPU VHR-10 | 10      | 800      | ~1000         | 3775        | HBB  | Google Earth           | 2016 |
| VEDAI       | 9       | 1210     | 512,1024      | 3640        | OBB  | Google Earth           | 2015 |
| UCAS-AOD    | 2       | 910      | ~1000         | 6029        | OBB  | Google Earth           | 2015 |
| UCAS-AOD    | 2       | 910      | ~1000         | 14235       | OBB  | Google Earth           | 2015 |
| COWC        | 1       | 53       | 2000~19,000   | 32716       | one dot        |
| HRSC2016    | 1       | 1061     | ~1100         | 2976        | oriented BB    |
| DOTA        | 15      | 2806     | 800~4000      | 118,282     | oriented BB    |
| xView       | 60      | 1128     |               | ~1,000,000  | horizontal BB  |
| DIOR        | 20      | 23463    | 800           | 190,288     | horizontal BB  |
### 2022
### 2021
### 2020
### 2015
- **VEDAI**<br>
**Categories**:9 different classes of vehicles, includs ‘plane’, ‘boat’, ‘camping car’, ‘car’, ‘pick-up’,‘tractor’, ‘truck’,‘van’, and the ‘other’.<br>
**Description**:<br>
**Reference**:<br>
- **UCAS-AOD**<br>
**Categories**:<br>
**Description**:<br>
**Reference**:<br>
Zhu, H., Chen, X., Dai, W., Fu, K., Ye, Q., Jiao, J., 2015. Orientation robust object detection in aerial images using deep convolutional neural network, in: 2015 IEEE International Conference on Image Processing (ICIP), IEEE. pp. 3735–3739.<br>
- **DLR 3K Vehicle**<br>
Liu, K., Mattyus, G., 2015. Fast multiclass vehicle detection on aerial images. IEEE Geoscience and Remote Sensing Letters 12, 1938–1942.<br>
## SAR

## Multi-Modal

# 4. Private datasets (limited usage license)
<br>

# 5. Dataset tools
- [DOTA_devkit](https://github.com/CAPTAIN-WHU/DOTA_devkit): Official DOTA dataset process code.
- [Remote-Sensing-Datasets](https://github.com/lawsonk16/Remote-Sensing-Datasets): DOTA, FAIR1M, xView process code.
