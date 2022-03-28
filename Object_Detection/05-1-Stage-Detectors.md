# (05강) 1 Stage Detectors

## 1. 1 stage Detectors

### 1.1 Background

2 Stage Detectors

- Localization → Classification : Limitation 속도가 매우 느림

1 Stage Detectors

- Localization, Classification이 동시에 진행
- 전체 이미지에 대해 특징 추출, 객체 검출이 이루어짐
- 속도가 매우 빠름
- 영역을 추출하지 않고 전체 이미지를 보기 때문에 객체에 대한 맥락적 이해가 높음
    - Background error가 낮음
- YOLO, SSD, RetinaNet

### 1.2 History

## 2. YOLO v1

### 2.1 Overview

You Only Look Once History

- YOLO v1 : 하나의 이미지의 Bbox와 classification 동시에 예측하는 1 stage detector 등장
- YOLO v2 : 빠르고 강력하고 더 좋게
    - 3가지 측면에서 model 향상
- YOLO v3 : multi-scale feature maps 사용
- YOLO v4 : 최신 딥러닝 기술 사용
    - BOF : Bag of Freebies, BOS : Bag of Specials
- YOLO v5 : 크기별로 모델 구성
    - Small, Medium, Large, Xlarge

### 2.2 Pipeline

- 입력 이미지를 SxS 그리드 영영으로 나눔
- 각 그리드 영역마다 B개의 Bounding box와 Confidence score 계산
    - 신뢰도(confidence) = $Pr(Object) \times IOU^{truth}_{pred}$
- 각 그리드 영역마다 C개의 class에 대한 해당 클래스일 확률 계산
    - conditional class probability = $Pr(Class_i|Object)$

### 2.3 Results

- Faster R-CNN에 비해 6배 빠른 속도
- 다른 real-time detector에 비해 2배 높은 정확도
- 이미지 전체를 보기 때문에 클래스와 사진에 대한 맥락적 정보를 가직 ㅗ있음
- 물체의 일반화된 표현을 학습
    - 사용된 dataset외 새로운 도메인 이미지에 대한 좋은 성능을 보임

## 3. SSD

### 3.1 Overview

YOLO 단점

- 7x7 그리드 영역으로 나눠 Bounding box prediction 진행
    - 그리드보다 작은 크기의 물체 검출 불가능
- 신경망을 통과하며 마짐가 feature만 사용
    - 정확도 하락


- Extra convolution layers에 나온 feature map들 모두 detection 수행
    - 6개의 서로 다른 scale의 feature map 사용
    - 큰 feature map (ealry stage feature map)에서는 작은 물체 탐지
    - 작은 feature map (late stage feature map)에서는 큰 물체 탐지
- Fully connected layer 대신 convolution layer 사용하여 속도 향상
- Default box 사용 (anchor box)
    - feature map의 각 cell마다 서로 다른 scale, 비율을 가진 미리 정해진 box 생성
    - Faster R-CNN의 anchor box와 유사


### 3.2 Pipeline

**Training**

- Hard negative mining 수행
- Non maximum suppression 수행

### 3.3 Results


## 4. YOLO Follow-up

### 4.1 YOLO v2

**Concepts**

- 3가지 파트에서 model 향상
    - Better : 정확도 향상
        - Batch normalization
        - High resolution classifier
    - Faster : 속도 향상
        - BAckbone model : GoogLeNet → Darknet-19
    - Stronger : 더 많은 class 예측 (80 → 9000)

### 4.2 YOLO v3

- Darknet-53
    - Skip connection
    - Max pooling x, convolution stride 2
    - ResNet-101, ResNet-152와 비슷한 성능, FPS 높음
- Multi-scale Feature maps
    - 서로 다른 3개의 scale을 사용
    - Feature pyramid network 사용
        - High-level의 fine-grained 정보와 low-level의 semantic 정보를 얻음

## 5. RetinaNet

### 5.1 Overview

1 Stage Detector Problems

모든 그리드에서 무조건 박스를 만들어 내므로, class imbalance가 수반된다.

- Class imbalance
    - Positive sample(객체 영역) < negative sample(배경 영역)
- Anchor Box 대부분 Negative Samples (background)
    - 2 Stage detector의 경우 region proposal에서 background sample 제거 (selective search, RPN)
    - Positive / negative sample 수 적절하게 유지 (hard negative mining)

### 5.2 Focal Loss

**Concept**

- 새로운 loss function : cross entropy loss + scaling factor
- 쉬운 예제에 작은 가중치, 어려운 예제에 큰 가중치
- 결과적으로 어려운 예제에 집중
