# (04강) Neck

## 1. Neck

### 1.1 Overview

- 마지막 feature map만 이용해서 하는 것이 아니라 중간 중간에 feature map도 이용해도 되지 않을까?
- 다양한 크기의 객체를 더 잘 탐지하기 위함
- 하위 level의 feature는 semantic이 약하므로 상대적으로 semantic이 강한 상위 feature와의 교환이 필요


### 1.2 Feature Pyramid Network (FPN)

- high level에서 low level로 semantic 정보 전달 필요
- 따라서 top-down path way 추가
    - Pyramid 구조를 통해서 high level 정보를 low level에 순차적으로 전달
        - Low level = Early stage = Bottom
        - High level = Late stage = Top
        
        
- Lateral connections
    - Nearest Neighbor Upsampling


- Backbone : ResNet

### 1.3 Path Aggregation Network (PANet)

- FPN은 Resnet을 사용하는데, Path가 너무 길어 Low-level의 feature가 High-level의 feature로 잘 전달되는가에 대한 의문이 있었다.
- 따라서 Bottom-up Path Augmentation을 이용하였다.
    
    

## 2. After FPN

### 2.1 DetectoRS

- Looking and thinking twice → 무언가 반복적으로 하면 좋은 성능이 나오네?
    - Region proposal networks (RPN)
    - Cascade R-CNN

주요 구성

- Recursive Feature Pyramid (RFP)
    
    - Atrous Spatial Pyramid Pooling (ASPP)
        
        
- Switchable Atrous Convolution (SAC)

### 2.2 Bi-directional Feature Pyramid (BiFPN)

- PANet에서 하나만 들어오는 노드를 없앰
- Weighted Feature Fusion
    - FPN처럼 단순히 Summation을 하는 것이아니라 weighted summation
    - 모델 사이즈의 증가는 거의 없음
    - 중요한 feature를 강조하여 성능 상승


### 2.3 NASFPN

**Motivation**

- 기존의 FPN, PANet
    - Top-down or bottom up pathway
- 단순 일방향(top→ bottom or bottom → top) summation보다 좋은 방법이 있을까?
- FPN architecture를 NAS (Neural architecture search)를 통해서 찾자!


- 단, COCO dataset, ResNet 기준으로 찾은 architecture, 범용적이지 못하다

### 2.4 AugFPN

- Problems in FPN
    - 서로 다른 level의 feature간의 semantic차이
    - Highest feature map의 정보 손실
    - 1개의 feature map에서 RoI 생성
- 주요 구성
    - Consistent Supervision
    - Residual Feature Augmentation
        
        
    - Soft RoI Selection