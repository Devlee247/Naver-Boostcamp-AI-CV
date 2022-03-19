## 1. Seeing the world in 3D perspective

### 1.1 Why is 3D important?

Applications

- AR/VR
- 3D Printing
- Medical applications

### 1.2 The way we observe 3D

An image is a projection of the 3D world onto a 2D space

The camera is a projection device of the 3D scene onto a 2D image plane

Triangulation - The way to obtain a 3D point from 2D images

Multiple View Geometry in computer vision → Bible

### 1.3 3D data representation

3D data representation is not unique


### 1.4 3D datasets

- ShapeNet
    - Large scale synthetic objects (51,300 3D models with 55 categories)
- ParkNet (ShapeNetPart2019)
    - Fine-grained dataset, useful for segmentation
    (573,585 part instances in 26,671 3D models)
- SceneNet
    - 5 million RGB-Depth synthetic indoor images
- ScanNet
    - RGB-Depth dataset with 2.5 million views obtained from more than 1500 scans
- Outdoor 3D scene datasets (typically for autonomous vehicle applications)
    - KITTI: LiDAR data, labeled by 3D b.boxes
    - Semantic KITTI: LiDAR data, labeled per point
    - Waymo Open Dataset: LiDAR data, labeled by 3D b.boxes

## 2. 3D tasks

### 2.1 3D recognition

- Recognizing a 3D object like the object recognition in 2D image

### 2.2 3D object detection

- Useful for autonomous driving applications

### 2.3 3D semantic segmentation

- neuroimaging

### 2.4 Conditional 3D generation

- Mesh R-CNN
    
    

## 3. 3D application example

### 3.1 Photo refocusing

- Defocusing a photo using depth map
    - Implementing an after-refocusing image feature given depth map
    - Almost same with “portrait mode” in your smartphone camera app
    - Depth map can be estimated by depth sensors or neural networks
    