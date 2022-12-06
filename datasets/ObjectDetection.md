# Object Detection Datasets

- [Object Detection Datasets](#object-detection-datasets)
- [1. Overview](#1-overview)
  - [Typical targets](#typical-targets)
  - [Image sources](#image-sources)
  - [Annotation types](#annotation-types)
- [2. Benchmarks and contests](#2-benchmarks-and-contests)
  - [Popular benchmarks with paper and code](#popular-benchmarks-with-paper-and-code)
  - [Hot contests with solution](#hot-contests-with-solution)
- [3. Datasets by category](#3-datasets-by-category)
  - [1. ship](#1-ship)
    - [Optical](#optical)
    - [SAR (TODO)](#sar-todo)
- [3. Datasets by year: Public datasets](#3-datasets-by-year-public-datasets)
  - [Optical](#optical-1)
    - [Multi-class](#multi-class)
      - [2022](#2022)
      - [2021](#2021)
      - [2020](#2020)
      - [2018](#2018)
      - [2016](#2016)
      - [2015](#2015)
    - [Single class: ship](#single-class-ship)
      - [2021](#2021-1)
      - [2020](#2020-1)
      - [2018](#2018-1)
      - [2016](#2016-1)
  - [SAR](#sar)
    - [Multi-class](#multi-class-1)
    - [Single class: ship](#single-class-ship-1)
      - [2022](#2022-1)
      - [2021](#2021-2)
      - [2020](#2020-2)
      - [2019](#2019)
      - [2017](#2017)
  - [Multi-Modal](#multi-modal)
- [4. Private datasets (limited usage license)](#4-private-datasets-limited-usage-license)
- [5. Dataset tools](#5-dataset-tools)


# 1. Overview
This repo briefly introduced the targets, images, annotations, popular benchmark, and datasets of remote sensing object detection. It is inspired by many great repos, such as [Satellite-Imagery-Datasets-Containing-Ships](https://github.com/jasonmanesis/Satellite-Imagery-Datasets-Containing-Ships). 


## Typical targets
- **general facilities**: airport, harbor, ground track field, basketball court, storage tank, bridge,...<br>
- **special facilities**: battle field, ...<br>
- **general targets**: ship, aircraft, ...<br>
- **special targets**: search and rescue target, aircraft carrier, T62, BTR_70, ...<br>

## Image sources
- Optical (MSS)
  - space-based<br>
    - Google Earth: ~level 15 - level 20 <br>
    - worldview: ~ 0.3m - *
    - GaoFen: ~ 0.6m - 50m
    - ...
  - air-based
    - ~ 0.01m - 1m
- Imaging radar (SAR)
  - space-based
    - GaoFen3: ~ 1m - 10m
  - air-based
- Non imaging radar

## Annotation types
General annotation types includes: Horizontal B-Box(HBB), Oriented B-Box(OBB), instance segmentation, diamond style, CEDAI, key point, and so on.<br>
- **Horizontal B-Box(HBB)**<br>
  - (xmin, ymin, xmax, ymax)<br>
    ![HBB_xyxy](../images/HBB_xyxy.png)<br>
  - (xcenter, ycenter, width, height)<br>
    ![HBB_xywh](../images/HBB_xywh.png)<br>
  - ...
- **Oriented B-Box(OBB)**<br>
  - (xcenter, ycenter, width, height, angle)<br>
    ![OBB_xywha](../images/OBB_xywha.png)<br>
  - (x1, y1, x2, y2, x3, y3, x4, y4)<br>
    ![OBB_xy4](../images/OBB_xy4.png)<br>
  - ...
- **instance segmentation**<br>
  - ...
- **diamond style**<br>
    Used in RarePlane dataset. Each aircraft is labeled in a diamond style with annotators instructed to label the nose, left-wing, tail, and right-wing in order. This annotation style has the advantage of being simplistic, easily reproducible, convertible to a bounding box, and ensures that aircraft are consistently annotated as other formats can often lead to imprecise labeling. Furthermore, this annotation style enables us to pull out two valuable features of aircraft: Their length and wingspan.<br>
    ![diamond style](https://www.cosmiqworks.org/wp-content/uploads/2020/04/1_gif.gif)<br>

- **VEDAI**<br>
  Used in VEDAI dataset. The annotation contains the image ID, the coordinates of the center in the image, the orientation of the vehicle, the 4 coordinates of the 4 corners, the class name, a flag stating if the target is entirely contained in the image, a flag stating if the vehicle is occluded.<br>
  ![VEDAI_annotation](../images/VEDAI_annotation.png)<br>
  ![VEDAI](../images/VEDAI.png)<br>
  

# 2. Benchmarks and contests
## Popular benchmarks with paper and code
- **DOTA**<br>
  - [Datasets](https://captain-whu.github.io/DOTA/dataset.html)<br>
  - [Tasks](https://captain-whu.github.io/DOTA/evaluation.html)<br>
  - Paper with code
    - [DOTA-1.0](https://paperswithcode.com/sota/object-detection-in-aerial-images-on-dota-1)
- **FAIR1M**
  - [Datasets](https://www.gaofen-challenge.com/benchmark) <br>
  - [Tasks](https://www.gaofen-challenge.com/benchmark) <br>
- ...
## Hot contests with solution
TODO

# 3. Datasets by category
## 1. ship 
### Optical
- **OBB**
  - in multi-class<br>
    - FAIR1M
    - DOTA
    - DIOR: 2702 of the 23463 images contain ~63000 ship instances.
    - NWPU VHR-10
  - specific<br>
    - ShipRSImageNet
    - FGSD2021
    - FGSD
    - AirbusShip
    - HRSC2016
    
- **HBB**
  - in multi-class<br>
    - DOTA
    - DIOR
    - VISO
    - xView
    - TGRS-HRRSD 
  - specific<br>
    - ShipRSImageNet
    - S2-SHIPS
    - GF1-LRSD
    - MSDS
    - PSDS
    - AirbusShip
    - HRSC2016
  
### SAR (TODO)
- **BB**
  - xView3-SAR
  - CEMEE2022
  - RSDD-SAR
  - SRSDD-v1.0
  - DSSDD
  - SSDD
  - AIR-SARShip-2.0
  - FUSAR-Ship
  - LS-SSDD-v1.0
  - HRSID
  - SAR-Ship-Dataset
  - OpenSARShip-2.0
  - ...

# 3. Datasets by year: Public datasets

## Optical
### Multi-class
| Dataset     | Categories | Images | Image width | Instances | Annotation |   Source    | Year | Available | remarks |
|:-----------:|:-------:|:--------:|:-------------:|:-----------:|:--------------:|:-----------:|:-----:|:----:|:--------:|
| SODA-A      | 9       | 2510     | -             | 800203      | OBB  | -                     | 2022  | no | not released now |
| FAIR1M      | 37      | 15000    | 1000-10000    | ~1,000,000  | OBB  | Google Earth, GF      | 2021  | yes |  |
| DIOR        | 20      | 23463    | 800           | 192,518     | HBB,OBB  | Google Earth      | 2022  | yes | |
| DOTA-2.0    | 18      | 11,268   | 800-20000     | 1,793,658   | OBB,HBB  | Google Earth, GF2, JL1| 2021  | yes |  |
| SaRNet       | 1       | 2552     | 1000         | 4206        | HBB  | ~ 0.5m                | 2021  | yes | |
| VISO       | 1       | 15455    | 12000*5000   | 853911      | HBB  | JiLin-1               | 2020  | yes | video for tracking |
| RarePlanes  |10 attributes| 253      |    512        | 14700   | diamond |WorldView3 0.31,1.24m| 2020 | yes | |
| xView       | 60      | 1128     | 2000-4000     | ~1,000,000  | HBB  | 0.3m                   | 2018 | yes | |
| TGRS-HRRSD  | 13      | 21761    | -             | 55740       | HBB  | 0.15-1.2m              | 2018 | yes | |
| NWPU VHR-10 | 10      | 800      | ~1000         | 3775        | HBB  | Google Earth           | 2016 |yes | |
| COWC        | 1       | 53       | 2000~19,000   | 32716       | VEDAI|    0.15m               | 2016 |yes | |
| VEDAI       | 9       | 1210     | 512,1024      | 3640        | OBB  | Google Earth           | 2015 |yes | |
| UCAS-AOD    | 2       | 910      | ~1000         | 6029        | OBB,HBB  | Google Earth           | 2015 |yes | |
|DLR 3K Vehicle| 20     | 20       | 5616          | 14235       | OBB  | Google Earth           | 2015 |yes | |
| RSOD        | 4       | 976      |               | 6950        | HBB  | Google Earth, Tianditu | 2015 | yes | |

#### 2022
- [**SODA-A (A large-scale Small Object Detection dAtaset)**](https://shaunyuan22.github.io/SODA/)<br>
  - **Categories**: <br>
  - **Description**: SODA is a large-scale benckmark for Small Object Detection, including SODA-D and SODA-A, which concentrate on Driving and Aerial scenarios respectively. SODA-A comprises 2510 high-resolution images of aerial scenes, which has 800203 instances annotated with oriented rectangle box annotations over 9 classes.<br>
  - **Reference**:<br>
[Towards Large-Scale Small Object Detection: Survey and Benchmarks](https://arxiv.org/abs/2207.14096)<br>
  - [Download link]()<br>

- [**FAIR1M**](https://www.gaofen-challenge.com/benchmark)<br>
  - **Categories**: Boeing 737, Boeing 777, Boeing 747, Boeing 787, Airbus A320, Airbus A220, Airbus A330, Airbus A350, COMAC C919, COMAC ARJ21, other-airplane, passenger ship, motorboat, fishing boat, tugboat, engineering ship, liquid cargo ship, dry cargo ship, warship, other-ship, small car, bus, cargo truck, dump truck, van, trailer, tractor, truck tractor, excavator, other-vehicle, baseball field, basketball court, football field, tennis court, roundabout, intersection, and bridge.<br>
  - **Description**: FAIR1M-1.0 in 2021, FAIR1M-2.0 in 2022<br>
  - **Reference**:<br>
[FAIR1M: A Benchmark Dataset for Fine-grained Object Recognition in High-Resolution Remote Sensing Imagery](https://arxiv.org/abs/2103.05569)<br>
  - [Download link](https://www.gaofen-challenge.com/benchmark)<br>

- **DIOR**<br>
  - **Categories**:<br>
  - **Description**: DIOR in 2020, DIOR-R in 2022. "DIOR" is a large-scale benchmark dataset for object detection in optical remote sensing images, which consists of 23,463 images and 192,518 object instances annotated with horizontal bounding boxes. "DIOR-R" is an extended version of DIOR annotated with oriented bounding boxes, which shares the same images with DIOR.<br>
  - **Reference**:<br>
Ke Li, Gang Wan, Gong Cheng*, Liqiu Meng, Junwei Han*. Object detection in optical remote sensing images: a survey and a new benchmark. ISPRS Journal of Photogrammetry and Remote Sensing, 159: 296-307, 2020.<br>
Gong Cheng, Jiabao Wang, Ke Li, Xingxing Xie, Chunbo Lang, Yanqing Yao, Junwei Han. Anchor-free Oriented Proposal Generator for Object Detection. IEEE Transactions on Geoscience and Remote Sensing, 2022.<br>
  - Download link [Google Drive](https://drive.google.com/open?id=1UdlgHk49iu6WpcJ5467iT-UqNPpx__CC) or [BaiduNetDisk](https://pan.baidu.com/s/1iLKT0JQoKXEJTGNxt5lSMg)<br>

#### 2021

- [**DOTA (A Large-Scale Dataset for Object Detection in Aerial Images)**](https://captain-whu.github.io/DOTA/index.html)<br>
  - **Categories**:<br>
DOTA-v1.0: plane, ship, storage tank, baseball diamond, tennis court, basketball court, ground track field, harbor, bridge, large vehicle, small vehicle, helicopter, roundabout, soccer ball field and swimming pool.<br>
DOTA-v1.5: plane, ship, storage tank, baseball diamond, tennis court, basketball court, ground track field, harbor, bridge, large vehicle, small vehicle, helicopter, roundabout, soccer ball field, swimming pool and container crane.<br>
DOTA-v2.0: plane, ship, storage tank, baseball diamond, tennis court, basketball court, ground track field, harbor, bridge, large vehicle, small vehicle, helicopter, roundabout, soccer ball field, swimming pool, container crane, airport and helipad.<br>
  - **Description**: DOTA-1.0 in 2018, DOTA-1.5 in 2019, DOTA-2.0 in 2021<br>
  - **Reference**:<br>
[Object Detection in Aerial Images: A Large-Scale Benchmark and Challenges](https://arxiv.org/pdf/2102.12219)<br>
  - [Download link](https://captain-whu.github.io/DOTA/dataset.html)<br>


- [**SaRNet: Satellite Imagery for Search And Rescue Dataset**](https://github.com/michaelthoreau/SearchAndRescueNet)<br>
  - **Categories**: target<br>
  - **Description**: This is a single class dataset consisting of tiles of satellite imagery labeled with potential 'targets'. Labelers were instructed to draw boxes around anything they suspect may a paraglider wing, missing in a remote area of Nevada. Volunteers were shown examples of similar objects already in the environment for comparison. The missing wing, as it was found after 3 weeks, is shown below.<br>
![SaRNet](https://camo.githubusercontent.com/30b03d6ae846b1077d27ba3d177fe85c4d74dd038d289850799ecc5e31b4bae5/68747470733a2f2f6d69636861656c747075626c69632e73332e616d617a6f6e6177732e636f6d2f696d616765732f616e6f6d616c795f736d616c6c2e6a7067)<br>
  - **Reference**:<br>
[SaRNet: A Dataset for Deep Learning Assisted Search and Rescue with Satellite Imagery](https://arxiv.org/pdf/2107.12469.pdf)<br>
  - [Download link](https://michaeltpublic.s3.amazonaws.com/sarnet.zip)<br>

#### 2020

- [**VISO (VIdeo Satellite Objects)**](https://github.com/QingyongHu/VISO)<br>
  - **Categories**: plane, car, ship, and train<br>
  - **Description**: This dataset is a large-scale dataset for moving object detection and tracking in satellite videos, which consists of 40 satellite videos captured by Jilin-1 satellite platforms. Each image has a resolution of 12000x5000 and contains a great number of objects with different scales. Four common types of vechicles, including plane, car, ship, and train, are manually-labeled. A total of 853,911 instances are labeled by axis-aligned bounding boxes.<br>
  - **Reference**:<br>
Detecting and Tracking Small and Dense Moving Objects in Satellite Videos: A Benchmark<br>
  - Download link [Google Drive](https://drive.google.com/file/d/11G0pqEMletzPtueGbgD-Pq9stQAcvpWw/view?usp=sharing) [BaiduYun](https://pan.baidu.com/s/1N7PocwTZC9SEA0fEymPOPA)(Sharing code: viso)<br>

- [**RarePlanes**](https://www.cosmiqworks.org/rareplanes-public-user-guide/)<br>
  - **Categories**:10 fine grain attributes including: aircraft length, wingspan, wing-shape, wing-position, FAA wingspan class, propulsion, number of engines, number of vertical-stabilizers, if it has canards, and aircraft role.<br>
  - **Description**:RarePlanes is a unique open-source machine learning dataset that incorporates both real and synthetically generated satellite imagery from Maxar and AI.Reverie. The real portion of the dataset consists of 253 Maxar WorldView-3 satellite images spanning 112 locations with ~14,700 hand annotated aircraft. The accompanying synthetic dataset is generated via AI.Reverie’s simulation platform and features 50,000 synthetic satellite images with over 600,000 aircraft annotations. <br>
  - **Reference**:<br>
All aircraft sketches are attributable to Wikipedia user Steelpillow: https://commons.wikimedia.org/wiki/User:Steelpillow/Aircraft<br>

#### 2018

- [**XView**](http://xviewdataset.org/#dataset)<br>
  - **Categories**: <br>
  - **Description**: 1.0 million Object Instances, 60 Classes, 0.3 meter
Resolution, 1,415 km2<br>
  - **Reference**:<br>

- **TGRS-HRRSD**<br>
  - **Categories**: 13 categories are: ship, airplane, baseball diamond, basketball court, bridge, crossroad, ground track field, harbor, parking lot, storage tank, T-junction, tennis court and vehicle.<br>
  - **Description**:<br>
    - It consists of 21761 images acquired from Google Earth and Baidu Map with the spatial resolution from 0.15m to 1.2 m. The above 21761 images have various sizes and are in .jpeg format with 24-bit color depth.
    - There are 13 object categories and 55740 object instances in TGRS-HRRSD. 
    - The TGRS-HRRSD dataset contains 3975 ship instances.
    - Every image has a corresponding .xml file which contains the image's dimensions, the class name, and the 4 coordinates (of the lower left and upper right points) of each bounding box, for every instance that is shown in the image.
  - **Reference**:<br>
  - [Download link](https://www.kaggle.com/haashaatif/tgrshrrsd-dataset)<br>

#### 2016
- **NWPU VHR-10**<br>
  - **Categories**:  airplane, ship, storage tank, baseballdiamond, tennis court, basketball court, ground track field, harbor, bridge,and vehicle<br>
  - **Description**:<br>
  - **Reference**:<br>
[Learning Rotation-Invariant Convolutional Neural Networks for Object Detection in VHR Optical Remote Sensing Images](https://ieeexplore.ieee.org/document/7560644)<br>
  - [Download link](https://1drv.ms/u/s!AmgKYzARBl5cczaUNysmiFRH4eE)<br>

- [**COWC(Cars Overhead With Context)**](https://gdo152.llnl.gov/cowc/)<br>
  - **Categories**: car<br>
  - **Description**:The Cars Overhead With Context (COWC) data set is a large set of annotated cars from overhead. It is useful for training a device such as a deep neural network to learn to detect and/or count cars. <br>
  - **Reference**:<br>
[A Large Contextual Dataset for Classification, Detection and Counting, of Cars with Deep Learning](https://gdo152.llnl.gov/cowc/mundhenk_et_al_eccv_2016.pdf)<br>
  - [Download link](ftp://gdo152.ucllnl.org/pub/cowc/)<br>

#### 2015
- **VEDAI (Vehicle Detection in Aerial Imagery)**<br>
  - **Categories**:9 different classes of vehicles, includs ‘plane’, ‘boat’, ‘camping car’, ‘car’, ‘pick-up’,‘tractor’, ‘truck’,‘van’, and the ‘other’.<br>
  - **Description**:<br>
The annotation contains the image ID, the coordinates of the center in the image, the orientation of the vehicle, the 4 coordinates of the 4 corners, the class name, a flag stating if the target is entirely contained in the image, a flag stating if the vehicle is occluded.<br>
  - **Reference**:<br>
[Vehicle Detection in Aerial Imagery: A small target detection benchmark., Sébastien Razakarivony and Frédéric Jurie, Journal of Visual Communication and Image Representation, 2015](https://hal.archives-ouvertes.fr/hal-01122605v2/document)<br>
  - [Download link](https://downloads.greyc.fr/vedai/)<br>

- **UCAS-AOD**<br>
  - **Categories**:airplane, vehicle<br>
  - **Description**:OBB aerial imagery dataset includes airplane, vehicle, and background.<br>
  - **Reference**:<br>
[Zhu, H., Chen, X., Dai, W., Fu, K., Ye, Q., Jiao, J., 2015. Orientation robust object detection in aerial images using deep convolutional neural network, in: 2015 IEEE International Conference on Image Processing (ICIP), IEEE. pp. 3735–3739.](https://ieeexplore.ieee.org/document/7351502)<br>
  - [Download link, not official](https://hyper.ai/datasets/5419)<br>

- **DLR 3K Vehicle**<br>
  - **Categories**:<br>
  - **Description**:The automatic detection of vehicles from aerial imagery is of interest for various applications such as traffic management, parking surveillance, and urban planning. The airborne optical sensors enable a fast wide-area recording of traffic data and parking information. In comparison to the ground-based sensors, using aerial images for monitoring the traffic in an area is much more time and cost efficient.<br>
  - **Reference**:<br>
Liu, K., Mattyus, G., 2015. Fast multiclass vehicle detection on aerial images. IEEE Geoscience and Remote Sensing Letters 12, 1938–1942.<br>
  - [Download link](https://pba-freesoftware.eoc.dlr.de/MunichDatasetVehicleDetection-2015-old.zip)<br>

- [**RSOD**](https://github.com/RSIA-LIESMARS-WHU/RSOD-Dataset-)<br>
  - **Categories**: aircraft, oiltank, playground and overpass<br>
  - **Description**:The format of this dataset is PASCAL VOC. The dataset includes 4 files, and each file is for one kind of object. Please download the dataset files from BaiduYun. aircraft dataset, 4993 aircrafts in 446 images. playground, 191 playgrounds in 189 images.overpass, 180 overpasses in 176 images. oiltank, 1586 oiltanks in 165 images.<br>
  - **Reference**:<br>
[Y. Long, Y. Gong, Z. Xiao and Q. Liu, "Accurate Object Localization in Remote Sensing Images Based on Convolutional Neural Networks," in IEEE Transactions on Geoscience and Remote Sensing, vol. 55, no. 5, pp. 2486-2498, May 2017. doi: 10.1109/TGRS.2016.2645610](http://ieeexplore.ieee.org/abstract/document/7827088/)<br>
  - [Download link](https://github.com/RSIA-LIESMARS-WHU/RSOD-Dataset-)<br>

### Single class: ship

| Dataset     | Categories | Images | Image width | Instances | Annotation |   Source    | Year | Available | remarks |
|:-----------:|:-------:|:--------:|:-------------:|:-----------:|:--------------:|:-----------:|:-----:|:----:|:-----------------:|
| ShipRSImageNet| 50     | 2198+550+687na| ~930   | 17573    | HBB,OBB | 0.12-6m   | 2021  | yes | cx,cy,w,h,angle and x1,y1,...x4,y4   |
| FGSD2021    | -        | 424+212  |200-5000| -        | OBB     | ~ 0.5m    | 2021  | yes | cx,cy,w,h,angle   |
| S2-SHIPS    | 3        | 16       |1783×938| 1053     | HBB     | ~ 10m     | 2021  | yes | 12 bands, uint16, with NDWI,seg mask, water mask |
| GF1-LRSD    | 1        | 4406     | 512    | 7172     | HBB     | GF1 WFV ~16m| 2021  | no  |  |
| FGSD        | 43       | 2612     |  930   | 5634     | OBB     | 0.12-1.93m | 2020  | no  | cx,cy,w,h,angle |
| MSDS        | 1        | 2993     |  900   | 4710     | HBB     | Google Earth | 2020  | no  |  |
| PSDS        | 1        | 1310     |  900   | 9662     | HBB     | PERUSAT-1 ~0.7m | 2020  | no  |  |
| Airbus Ship | 1        | 192556   |  768   | 81723    | OBB     | -            | 2018  | yes | mask with run-length encoding (RLE) format |
| HRSC2016    | 27       | 626+444  | ~1100  | 2976     | HBB,OBB | Google Earth 0.4~2m       | 2016 |yes |cx,cy,w,h,angle |

na: no annotation

#### 2021
- **ShipRSImageNet**<br>
  - **Categories**: 4-level. Level 0 distinguishes whether the object is a ship, namely "Class". Level 1 further classifies the ship object category, named as "Category". Level 2 further subdivides the categories based on level 1 ("Subcategory"). Level 3 is the specific type of ship, named "Type".<br>
  - **Description**:<br>
    - ShipRSImageNet contains over 3435 images with 17573 ship instances, annotated with both horizontal and orientated bounding boxes.<br>
    - The above 3435 images were obtained from various sensors, satellite platforms, locations, and seasons.<br>
    - Each image is around 930×930 pixels and contains ships with different scales, orientations, and aspect ratios.<br>
    - The spatial resolution of the images ranges from 0.12 to 6 m.<br>
    - These 3435 images were collected from:<br>
    The xView dataset (532 images).<br>
    The HRSC2016 dataset (1057 images).<br>
    The FGSD dataset (1846 images).<br>
    The Airbus Ship Detection Challenge (21 images).<br>
    Chinese satellites, such as GaoFen-2 and JiLin-1 (17 images).<br>
    - Ships in ShipRSImageNet are hierarchically classified into four levels (0-3) and 50 categories (49 ship types and "Dock").<br>
    - The ShipRSImageNet was divided in training, validation and test sets which contain 64% (2198), 16% (550) and 20% (687) of the original images respectively.<br>
    - Each ship instance has a corresponding set of annotations which are:<br>
    A horizontal bounding box ↦ (xmin, ymin, xmax, ymax).<br>
    An oriented bounding box ↦ (xc, yc, w, h, θ).<br>
    A polygon annotation ↦ (x1, y1, x2, y2, x3, y3, x4, y4).<br>
    - The above annotations are available in Pascal VOC and MS COCO dataset formats.<br>
    - **only trainval annotations are in the published dataset, missing test annotations**
  - **Reference**:<br>
  [ShipRSImageNet: A Large-Scale Fine-Grained Dataset for Ship Detection in High-Resolution Optical Remote Sensing Images](https://ieeexplore.ieee.org/document/9512396)<br>
  - [Download link](https://drive.google.com/file/d/1wApkaSoa9mXRfXQiq6lTtlVrv4cSc6vv/view)<br>
  
- [**FGSD2021**](https://github.com/zf020114/CHPDet)<br>
  - **Categories**: in chinese, e.g. 阿利·伯克级, 霍普级, ...<br>
  - **Description**: A Dataset for Fine-Grained Ship Detection in High Resolution Satellite Images. Annotated with cx,cy,w,h,angle<br>
  - **Reference**:<br>
[Arbitrary-Oriented Ship Detection through Center-Head Point Extraction](https://arxiv.org/abs/2101.11189)<br>
  - [Download link with extract code 'nudt'](https://pan.baidu.com/s/1vuHCjsZQX8DMHG05mvT0GA)<br>

- **S2-SHIPS**<br>
  - **Categories**: 3 classes with ids ∈ {1, 3, 4} which are named 'Ship', 'Doubt' and 'Moored Ship' respectively.<br>
  - **Description**:<br>
    - This dataset includes 16 L2A (BOA reflectance) images of coastline, ports, and the Suez canal.
    - These images were derived from the original Sentinel-2 images and their dimensions are 1783 × 938 pixels.
    - The above images contain 1053 distinct ship instances with varying sizes from 100-5000 m2.
    - Every image is a different scene for which they are available:
      - The 12 atmospherically corrected Sentinel-2 bands (.tiff).
      - The NDWI index in .tiff and .png file formats.
      - A true color image in .tiff and .jpg file formats.
      - A RGB image (.png).
      - The image's segmentation mask (.png).
      - A water mask (.tiff).
    - The above georeferenced images (.tiffs) they are all reprojected to EPSG 3857 and their datatype is UInt16.
    - The georeferenced images of the scenes have the same spatial resolution which is ≈10 m.
    - The segmentation masks where provided also in the Numpy file format (.npy).
    - An annotation .json file with segmentation masks and horizontal bounding boxes is also provided.
    - The above annotations follow the conventions of the MS COCO dataset format.
  - **Reference**:<br>
  [Ship Detection in Sentinel 2 Multi-Spectral Images with Self-Supervised Learning](https://www.mdpi.com/2072-4292/13/21/4255)<br>
  - [Download link](https://drive.google.com/file/d/1zDgz6wr5kxikPR7o9nJ2IjMcaqwtiLLu/view)<br>

- **GF1-LRSD**<br>
  - **Categories**: ship<br>
  - **Description**:<br>
    - The images in this dataset were obtained from level 1A Gaofen-1 (WFV) scenes.
    - GF1-LRSD consists of 4406 images of size 512x512 pixels with 8-bit color depth.
    - The above images contain a total of 7172 ship instances.
    - The spatial resolution of the images equals to 16m per pixel.
    - For the annotation of the targets, horizontal rectangular boxes were used which follow the PASCAL VOC format.
  - **Reference**:<br>
  [LR-TSDet: Towards Tiny Ship Detection in Low-Resolution Remote Sensing Images](https://www.mdpi.com/2072-4292/13/19/3890/html)<br>
  - Download link: currently no available<br>



#### 2020
- **FGSD (Fine-Grained Ship Detection)**<br>
  - **Categories**: 3-level, 1 Level-1 category : ship, 4 Level-2 categories : warship, carrier, submarine and civil ship, 43 Level-3 categories : container, oil tanker, yacht, hovercraft, etc<br>
  - **Description**: The specific dataset contains 2612 images from 17 large ports including China, Japan, the United States and Spain. The above images have dimensions of 930 × 930 pixels and their spatial resolutions range from 0.12m to 1.93m. These images contain 5634 ship instances. There are 43 categories of ships and a 'dock' category in the dataset. Ship samples in FGSD were annotated with both common used bounding box and rotated bounding box. The rotated bounding box is annotated as (xc, yc, w, h, θ). Each image has a corresponding annotation file, which includes the source-port’s ID, the resolution and corresponding Google Earth's resolution level of the image.<br>
  - **Reference**:<br>
[FGSD: A Dataset for Fine-Grained Ship Detection in High Resolution Satellite Images](https://arxiv.org/abs/2003.06832)
  - Download link: mail to ckyan@bupt.edu.cn<br>

- **MSDS (Mini Ship Data Set)**<br>
  - **Categories**: ship<br>
  - **Description**: 2993 images of 900 × 900 pixels, using Google Earth satellite images.<br>
  - **Reference**:<br>
  [New Approaches and Tools for Ship Detection in Optical Satellite Imagery](https://iopscience.iop.org/article/10.1088/1742-6596/1642/1/012003)<br>
  - Download link: currently no available<br>

- **PSDS (Peruvian Ship Data Set)**<br>
  - **Categories**: ship<br>
  - **Description**: 1310 images with size of 900 × 900 pixels, from 22 satellite images of PERUSAT-1 with 0.7 m spatial resolution.<br>
  - **Reference**:<br>
  [New Approaches and Tools for Ship Detection in Optical Satellite Imagery](https://iopscience.iop.org/article/10.1088/1742-6596/1642/1/012003)<br>
  - Download link: currently no available<br>

#### 2018
- **Airbus Ship Detection Challenge Dataset**<br>
  - **Categories**: ship<br>
  - **Description**:<br>
    - he specific dataset consists of 192556 images with size of 768 × 768 pixels.
    - These 192556 images contain 81723 ship instances.
    - The images in .jpeg format, with 24-bit (8 bits per channel) color depth.
    - For every one of these images there is a corresponding .csv file. The above .csv file contains the encoded pixel coordinates of each ship's oriented rectangular mask in run-length encoding(RLE) format, for every ship instance in the specific image.
    - [deal with RLE mask.](https://www.kaggle.com/code/julian3833/2-understanding-plotting-rle-bounding-boxes)
  - **Reference**:<br>
  [Kaggle Airbus Ship Detection Challenge Dataset](https://www.kaggle.com/c/airbus-ship-detection)<br>
  - [Download link](https://www.kaggle.com/c/airbus-ship-detection/data)<br>

#### 2016
- [**HRSC2016(High resolution ship collections 2016)](https://www.kaggle.com/datasets/guofeng/hrsc2016)**<br>
  - **Categories**:<br>
  3-level class, 4 categories 27 types<br>
   aircraft carrier: Nimitz class aircraft carrier, Enterprise class aircraft carrier, Kitty Hawk class aircraft carrier, Admiral Kuznetsov aircraft carrier, Ford-class aircraft carriers, Midway-class aircraft carrier, Invincible-class aircraft carrier<br>
   warcraft: Arleigh Burke class destroyers, WhidbeyIsland class landing craft, Perry class frigate, Sanantonio class amphibious transport dock, Ticonderoga class cruiser, Abukuma-class destroyer escort, Austen class amphibious transport dock, Tarawa-class amphibious assault ship, USS Blue Ridge (LCC-19), Command ship A, Warcraft A, Medical ship<br>
   merchant ship: Container ship, Car carrier A, Hovercraft, yacht, Container ship A, Cruise ship, Car carrier B<br>
   Submarine: Submarine<br>
  - **Description**:High resolution ship collections 2016 (HRSC2016) is a data set used for scientific research. Currently, all of the images in HRSC2016 were collected from Google Earth.<br>
  - **Reference**:<br>
[[1] Liu Z, Yuan L, Weng L, et al. A High Resolution Optical Satellite Image Dataset for Ship Recognition and Some New Baselines[C]//ICPRAM. 2017: 324-331.](http://159.226.21.68/bitstream/173211/14545/1/A%20High%20Resolution%20Optical%20Satellite%20Image%20Dataset%20for%20Ship%20Recognition%20and%20Some%20New%20Baselines.pdf)<br>
[[2] Ship Rotated Bounding Box Space for Ship Extraction From High-Resolution Optical Satellite Images With Complex Backgrounds](http://159.226.21.68/bitstream/173211/14544/1/Ship%20Rotated%20Bounding%20Box%20Space%20for%20Ship%20Extraction%20from%20High-Resolution%20Optical%20Satellite%20Images%20with%20Complex%20Backgrounds.pdf)<br>
  - [Download link](https://www.kaggle.com/datasets/guofeng/hrsc2016)<br>

- **TODO**<br>
  - **Categories**:<br>
  - **Description**:<br>
  - **Reference**:<br>
  - [Download link]()<br>


## SAR
### Multi-class

| Dataset     | Categories | Images | Image width | Instances | Annotation |   Source    | Year | Available | remarks |
|:-----------:|:-------:|:--------:|:-------------:|:-----------:|:--------------:|:-----------:|:-----:|:----:|:-----------------:|




### Single class: ship

| Dataset     | Categories | Images | Image width | Instances | Annotation |   Source    | Year | Available | remarks |
|:-----------:|:-------:|:--------:|:-------------:|:-----------:|:--------------:|:-----------:|:-----:|:----:|:-----------------:|
| xView3-SAR      | 1       | 991      |  -    | 220,000+ | HBB  | Sentinel-1,20m | 2022  | yes |  |
|CEMEE2022 Challenge| 7       | 1000     |  1024 | -        | OBB  | -              | 2022  | yes | register for data |
| RSDD-SAR        | 1       | 7000     |  512  | 10263    | OBB  | GF-3, TerraSAR-X | 2022  | yes |  |
| SRSDD-v1.0      | 6       | 666      |  1024 | 2884     | OBB  | GaoFen-3,1m    | 2021  | yes | x1,y1,...x4,y4 |
| DSSDD           | 1       | 1236     |  256  | 3540     |HBB,OBB| Sentinel-1   | 2021  | yes | cx,cy,w,h,angle, VV,VH |
| SSDD2021        | 1       | 1160     |  500  | 2358     |HBB,OBB| RadarSat-2, TerraSAR-X,Sentinel-1, 1-15m | 2021  | yes |  |
| AIR-SARShip-2.0 | 1       | 300      |  1000 | -        | HBB  | GaoFen3 1m,3m | 2020  | yes | 1-channel, 16-bit |
| FUSAR-Ship Dataset v1.0|98| 6358     |  512  | ~5000    | -    | GaoFen-3    | 2020  | yes |  |
| LS-SSDD-v1.0    | 1       | ~9000    |  800  | -        | HBB  | Sentinel-1   | 2020  | yes |  |
| HRSID          | 1       | 5604      |  800  | 16951    |HBB,IS| Sentinel-1B imageries, 36 TerraSAR-X and 1 TanDEM-X, 0.5,1,3m     | 2020  | yes | with instance segmentation |
| SAR-Ship-Dataset| 1       | 43819    |  256  | 59535    | HBB  | Sentinel-1, GaoFen-3 3-25m | 2019  | yes | x,y,w,h |
| OpenSARship-2.0 | 1       | 34528    | 30-120| -        |HBB,OBB| Sentinel-1 3-22m | 2017  | yes | with AIS message |

#### 2022
- **xView3-SAR**<br>
  - **Categories**:<br>
  - **Description**:<br>
    - 991 SAR scenes from Sentinel-1 at 20m resolution with 220,000+ vessel/non-vessel AIS-based annotations with length information.
    - Each xView3-SAR scene has additional, co-registered bathymetry, wind speed, wind quality, and other ancillary information.
    - The dataset has a total of ~1,422 gigapixels (4.7x larger than MS-COCO).
    - Each SAR image is in Interferometric Wide (IW) swath mode.
    - Anntotations are created automatically through a sophisticated AIS-extrapolation algorithm, as well as manually with human experts.
    - Each label has a confidence metric associated with its length at HIGH, MEDIUM, or LOW.
  - **Reference**:<br>
  [xView3-SAR: Detecting Dark Fishing Activity Using Synthetic Aperture Radar Imagery](https://arxiv.org/abs/2206.00897)<br>
  - [Download link](https://iuu.xview.us/)<br>

- **CEMEE2022 Challenge**<br>
  - **Categories**: 7, S1 to S7<br>
  - **Description**:<br>
    - register for challenge and dataset
    - labeled as x1 y1 x2 y2 x3 y3 x4 y4
  - **Reference**:<br>
  - [Download link](http://cemee.org.cn/#/customer/match/893eb51e-d665-45d5-ad94-c164307bdb57)<br>

- [**RSDD-SAR (Rotated Ship Detection Dataset in SAR Images)**](https://radars.ac.cn/web/data/getData?dataType=SDD-SAR_en&pageType=en)<br>
  - **Categories**:<br>
  - **Description**:<br>
    - [RSDD-SAR Dataset Instruction](https://radars.ac.cn/fileLDXB/cms/news/info/2022/07/af9ec429bab44aa49d5e506c54b98283/RSDD-SAR%20Dataset%20Instructions.pdf)
    - Rotated Ship Detection Dataset in SAR Images (RSDD-SAR) was built based on the domestic GF-3 satellite and the ESA TerraSAR-X satellite. This dataset consists of 84 scenes GF-3 data slices, 41 scenes TerraSAR-X data slices, and 2 scenes uncropped large images, includes 7,000 slices and 10,263 ship instances of multi-observing modes, multi-polarization modes and multi-resolutions, and has the characteristics of arbitrary rotation direction, large aspect ratio, high proportion of small targets and rich in scenarios. Figure.1 shows an example of the typical scenarios in RSDD-SAR.
    - The size of slice in RSDD-SAR is unified to 512×512 pixels, the format of slice is a 3-channel, 24-bit, grayscale .JPG images, and the annotation of slice is a .XML format file. The annotation file records the polarization mode, resolution, rotated bounding box annotation and other information. The rotated bounding box annotation adopts the long-edge definition method, including the center point coordinate, long edge, short edge, and angle. For an example of the annotation file, see the ‘RSDD-SAR Dataset Instructions’. 2 scenes uncropped images and their annotations are the same as the slice.
  - **Reference**:<br>
  [XU Congan, SU Hang, LI Jianwei, et al. RSDD-SAR: Rotated ship detection dataset in SAR images[J]. Journal of Radars, in press. doi: 10.12000/JR22007.](https://radars.ac.cn/en/article/doi/10.12000/JR22007)<br>
  - [Download link](https://radars.ac.cn/web/data/getData?dataType=SDD-SAR_en&pageType=en)<br>

#### 2021
- **SRSDD-v1.0 (SAR Rotation Ship Detection Dataset)**<br>
  - **Categories**: 6, includes: ore-oil, bulk-cargo, Fishing, LawEnforce, Dredger, Container<br>
  - **Description**:<br>
    - It consists of 30 panoramic SAR tiles of the Chinese Gaofen-3 with a resolution of 1 m in range direction and azimuth.
    - These original SAR images are in spotlight (SL) mode with a HH and VV polarizations.
    - The above imageries were cropped to 666 smaller images with dimensions of 1024x1024 pixels.
    - SRSDD-v1.0 contains 2884 ship instances which are distributed among 6 different categories:
      - ore-oil (carrier) ↦ 166 ship instances
      - bulk-cargo ↦ 2053 ship instances
      - Fishing ↦ 288 ship instances
      - LawEnforce ↦ 25 ship instances
      - Dredger ↦ 263 ship instances
      - Container ↦ 89 ship instances
    - In the dataset, each instance's location is annotated by a oriented quadrilateral bounding box [(x1, y1), (x2, y2), (x3, y3), (x4, y4)]. The first point of the bounding box (x1, y1) denotes the starting point, which refers to the top left corner of a ship.
    - Annotations for an image are saved in a text file with the same file name. In the first line, "imagesource" is given. In the second line, "gsd"(ground sample distance=1) is given. From third line to the last line in the annotation text file, annotation for each instance is given.
    - For every instance, a "difficult" label is provided, which indicates whether the instance is difficult to be detected (1 for difficult, 0 for not difficult).
  - **Reference**:<br>
  [SRSDD-v1.0: A High-Resolution SAR Rotation Ship Detection Dataset](https://www.mdpi.com/2072-4292/13/24/5104)<br>
  - [Download link wth code: aC1Q](https://pan.baidu.com/s/1EonxuMSDVCnICwSsfWjYew)<br>

- **DSSDD (Dual-polarimetric SAR Ship Detection Dataset)**<br>
  - **Categories**:<br>
  - **Description**:<br>
   - The specific dataset contains 50 dual-polarimetric SAR images from Sentinel-1.
   - The above images were cropped to 1236 image slices with the size of 256x256 pixels.
   - These 1236 images have VV and VH polarizations which were then fused into R,G,B channels for the creation of the pseudo-color image.
   - The colour depth of the images (.png) is 8 bits/channel.
   - The 16-bit original images (.tif) are also provided.
   - This dataset includes 3540 ship instances.
   - Each ship was labeled with both a rotatable bounding box (RBox) and a horizontal bounding box (BBox).
   - Each image slice has a corresponding XML format annotation file, indicating the slice size, slice name, and annotation type:
   - The RBox label is tagged as “robndbox”, where "cx", "cy", "w", "h", and "angle" indicate the center coordinates, height, width, and angle of a box, respectively.
   - Correspondingly, the BBox label is tagged as "bndbox", where "xmin", "xmax", "ymin", "ymax" refer to the top left corner and the lower right corner coordinates of a box, respectively.
  - **Reference**:<br>
  [A Dual-Polarimetric SAR Ship Detection Dataset and a Memory-Augmented Autoencoder-Based Detection Method](https://www.mdpi.com/1424-8220/21/24/8478)<br>
  - [Download link](https://github.com/liyiniiecas/A_Dual-polarimetric_SAR_Ship_Detection_Dataset)<br>

- **SSDD2021 (SAR Ship Detection Dataset)**<br>
  - **Categories**: ship<br>
  - **Description**:<br>
    - It consists of 1160 SAR images with dimensions of 500×350 pixels.
    - This specific dataset includes 2358 ship instances.
    - The spatial resolutions of SAR images are from 1 to 15 meters per pixel.
    - These 1160 images were obtained from RadarSat-2, TerraSAR-X and Sentinel-1 satellites.
    - The above 1160 images is are in .jpeg format with 24 bit color depth.
    - Dataset images have mixed HH, HV, VV, and VH polarizations.
    - In the new version of SSDD, three kinds of annotational information are provided:
      - Horizontal bounding box.
      - Rotated bounding box.
      - Pixel-based segmentation.
    - The above annotations are in Pascal VOC and MS COCO dataset formats, except of rotated bounding boxes, which are only available on Pascal VOC format.
  - **Reference**:<br>
  [SAR Ship Detection Dataset (SSDD): Official Release and Comprehensive Data Analysis](https://www.mdpi.com/2072-4292/13/18/3690)<br>
  - [Download link](https://drive.google.com/file/d/1glNJUGotrbEyk43twwB9556AdngJsynZ/view?usp=sharing)<br>

#### 2020
- [**AIR-SARShip-2.0**](https://radars.ac.cn/web/data/getData?dataType=SARDataset_en&pageType=en)<br>
  - **Categories**: ship<br>
  - **Description**: High-resolution SAR ship objection detection dataset-2.0 (AIR-SARShip-2.0) releases 300 images. The resolution of images includes 1m and 3m, imaging mode covers both spotlight and strip, and polarization is single polarization. The scene type includes ports, islands and reefs, and seas of different grades. The target contains thousands ships with more than ten categories such as transport vessels, oil tankers and fishing boats.<br>
  - **Reference**:<br>
[Xian Sun, Zhirui Wang, Yuanrui Sun, et al. AIR-SARShip-1.0: High Resolution SAR Ship Detection Dataset[J]. Journal of Radars, in press. doi: 10.12000/JR19097](https://radars.ac.cn/en/article/doi/10.12000/JR19097)<br>
  - [Download link](https://radars.ac.cn/web/data/getData?dataType=SARDataset_en&pageType=en)<br>

- **FUSAR-Ship Dataset v1.0**<br>
  - **Categories**: 15 ship categories, 98 ship subcategories<br>
  - **Description**:<br>
    - FUSAR-Ship dataset has a total of 15 ship categories, 98 ship subcategories, consisted of 126 GF-3 scenes covering various scenarios. The imaging mode of those 126 images is ultrafine strip-map (UFS) mode.
    - It includes over 5000 ship chips with AIS messages and some other types of marine   targets and background clutters.
    - The above single-band ship images have dimensions of 512 × 512 pixels.
    - These images are in .tiff format and their color depth is 8 bits.
    - These image chips are stored under subfolder named after its 'category/subcategory'. The filename of each sample follows the convention: Ship_CxxSyyNzzzz.tiff, where xx is the index of category, yy is the index of subcategory and zzzz is the index of this particular sample.
    - Dataset images have VV and HH polarizations.
    - The matchup metadata is compiled in the file 'meta.csv' or 'meta.xls', which follow the format of: id mmsi length width polarMode centerLookAngle heightspace widthspace path.
  - **Reference**:<br>
  [FUSAR-Ship: building a high-resolution SAR-AIS matchup dataset of Gaofen-3 for ship detection and recognition](https://link.springer.com/article/10.1007/s11432-019-2772-5)<br>
  - [Download link](https://emwlab.fudan.edu.cn/resources/)<br>

- **LS-SSDD-v1.0**<br>
  - **Categories**:<br>
  - **Description**:<br>
    - It consists of 15 large-scale SAR images, obtained from Sentinel-1 satellite, with size of 24000 × 16000 pixels.
    - These 15 large-scale SAR images were cut into 9000 sub-images with dimensions of 800 × 800 pixels.
    - Every image has a corresponding .xml file which contains one bounding box for each one of image's instances.
    - Dataset images have VV and VH polarizations.
  - **Reference**:<br>
  [LS-SSDD-v1.0: A Deep Learning Dataset Dedicated to Small Ship Detection from Large-Scale Sentinel-1 SAR Images](https://www.mdpi.com/2072-4292/12/18/2997/html)<br>
  - [Download link](https://github.com/TianwenZhang0825/LS-SSDD-v1.0-OPEN)<br>

- **HRSID**<br>
  - **Categories**:<br>
  - **Description**:<br>
    - The specific dataset contains 116 co-polarized and 20 cross-polarized SAR imageries.
    - The original imageries for constructing HRSID are 99 Sentinel-1B imageries, 36 TerraSAR-X and 1 TanDEM-X imageries.
    - The above 136 panoramic SAR imageries cropped to 5604 high-resolution SAR images.
    - These 5604 images have dimensions of 800 × 800 pixels, resolution of 96 dpi, and there are in .jpeg format.
    - The colour depth of the images is 8 bits (one channel).
    - The extracted 5604 high-resolution SAR images contain 16951 ship instances.
    - The spatial resolutions of SAR images are 0.5, 1 and 3 meters per pixel.
    - The annotations of each instance are the corresponding bounding box and the ship's outline.
    - The annotations of each SAR image constitute a .json file in MS COCO dataset format.
  - **Reference**:<br>
  [HRSID: A High-Resolution SAR Images Dataset for Ship Detection and Instance Segmentation](https://ieeexplore.ieee.org/abstract/document/9127939)<br>
  - [Download link](https://github.com/chaozhong2010/HRSID)<br>

#### 2019
- **SAR-Ship-Dataset**<br>
  - **Categories**:<br>
  - **Description**:<br>
    - It consists of 43819 ship chips of 256 × 256 pixels.
    - The specific dataset includes 59535 ship instances.
    - This dataset was created using 102 Chinese Gaofen-3 images and 108 Sentinel-1 images.
    - For Gaofen-3, the images have spatial resolutions of 3 m, 5 m, 8 m, 10m, and 25 m per pixel, and for Sentinel-1 the spatial resolutions of the images are 1.7 × 4.3 to 3.6 × 4.9 and 20 × 22 meters.
    - For Gaofen-3 the imaging modes are Ultrafine Strip-Map (UFS), Fine Strip-Map 1 (FSI), Full Polarization 1 (QPSI), Full Polarization 2 (QPSII), and Fine Strip-Map 2 (FSII).
    - For Sentinel-1, the imaging modes are S3 Strip-Map (SM), S6 SM, and IW-mode.
    - Each ship chip corresponds to an Extensible Markup Language (XML) file, indicating the ship's location, the ship chip name, and the image shape.
  - **Reference**:<br>
  [A SAR Dataset of Ship Detection for Deep Learning under Complex Backgrounds](https://www.mdpi.com/2072-4292/11/7/765)<br>
  - [Download link](https://github.com/CAESAR-Radi/SAR-Ship-Dataset)<br>

#### 2017
- **OpenSARShip 2.0**<br>
  - **Categories**:<br>
  - **Description**:<br>
    - OpenSARShip 2.0 consists of 34528 image chips cropped from a total of 87 Sentinel-1 images.
    - The whole products are in the interferometric wide swath (IW) mode.
    - The OpenSARShip contains two available products of the IW mode: the single look complex (SLC) and the ground range detected (GRD) products.
    - These 87 Sentinel-1 images, 52 from GRD and 35 from SLC imageries, are selected from 10 typical intense marine traffic scenes globally in latest years.
    - For Sentinel-1 the spatial resolutions of the images 2.7 × 22 to 3.6 × 22 and 20 × 22 meters.
    - Dataset images have mixed VV and VH polarizations.
    - Each ship image corresponds to an automatic identification system (AIS) message.
    - The detailed information of each ship chip, containing the AIS messages, the SAR ship signatures, and the messages provided by the MarineTraffic website, is listed in an XML file named Ship.xml
    - The image sizes range from 30 × 30 to 120 × 120 pixels.
    - For every Sentinel-1 SAR image, four subfolders provide the different formats of ship chips: original data, visualized data in greyscale, visualized data in pseudo-color, and calibrated data.
  - **Reference**:<br>
  [OpenSARShip 2.0: A large-volume dataset for deeper interpretation of ship targets in Sentinel-1 imagery](https://ieeexplore.ieee.org/document/8124929)<br>
  - [Download link](http://opensar.sjtu.edu.cn)<br>

## Multi-Modal

- **TODO**<br>
  - **Categories**:<br>
  - **Description**:<br>
  - **Reference**:<br>
  []()<br>
  - [Download link]()<br>

# 4. Private datasets (limited usage license)
TODO<br>

# 5. Dataset tools
- [DOTA_devkit](https://github.com/CAPTAIN-WHU/DOTA_devkit): Official DOTA dataset process code.
- [Remote-Sensing-Datasets](https://github.com/lawsonk16/Remote-Sensing-Datasets): DOTA, FAIR1M, xView process code.
