## 1. Instance segmentation

### 1.1 What is instance segmentation?


Instance segmentation = Semantic segmentation + distinguishing instances

### 1.2 Instance segmenters


- Mask R-CNN = Faster R-CNN + Mask branch
    - RoI extraction through **RoIAlign,** an improved version of RoI Pooling


- YOLACT (You Only Look At CoefficienTs)


- YolactEdge

## 2. Panoptic segmentation

### 2.1 What is panoptic segmentation?


Panoptic segmentation

(Stuff + Instances of Things)

### 2.2 UPSNet & VPSNet


- UPSNet
    - Semantic & Instance head → Panoptic head → Panoptic logits


- VPSNet (for video)
    1. Align reference features on to the target feature map (Fusion at pixel level)
    2. Track module associates different object instances (Track at instance level)
    3. Fused-and-tracked modules are trained to synergize each other

## 3. Landmark localization

### 3.1 What is landmark localization?


**Landmark localization** (= keypoint estimation) ****: Predicting the coordinates of keypoints.

- Facial landmark localization
- Human pose estimation

### 3.2 Coordinate regression vs. heatmap classification

- Coordinate regression : usally inaccurate and biased
- **Heatmap classification** : better performance but high computational cost

**Landmark** location to **Gaussian heatmap**

$$
G_\sigma(x,y) = exp(-{(x-x_c)^2 + (y-y_c)^2 \over 2\sigma^2})
$$

### 3.3 Hourglass network


- Unet의 구조가 모래시계처럼 생겼다 해서 Stacked Hourglass라 한다.
    - Stacked hourglass modules allow for repeated bottom-up and top-down inference that refines the output of the previous hourglass module

### 3.4 Extensions


- DensePose
DensePose R-CNN = Faster R-CNN + 3D surface regression branch
- RetinaFace = FPN + Multi-task branches
(classification, bounding box, 5 point regression, mesh regression)

FPN + Target-task branches

## 4. Detectiong objects as keypoints

### 4.1 CornerNet & CenterNet

- CornerNet
    - Bounding box = {Top-left, Bottom-right} corners
- CenterNet (1)
    - Bounding box = {Top-left, Bottom-right, Center} points
- CenterNet (2)
    - Bounding box = {Width, Height, Center} points