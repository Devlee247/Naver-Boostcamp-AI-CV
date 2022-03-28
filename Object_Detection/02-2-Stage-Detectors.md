# (02강) 2 Stage Detectors

## 1. R-CNN

### 1.1 Overview


1. Input Image
2. Extract Regoin proposals
    - Sliding window → 무수히 많은 후보 영역이 나오게 된다.
        
        
    - Selective Search
        
        
3. Compute CNN features
4. Classify Regions

### 1.2 Pipeline

1.  입력 이미지 받기
2. Selective Search를 통해 약 2000개의 RoI를 추출
3. RoI의 크기를 조절해 모두 돌일한 사이즈로 변형
    - CNN의 마지막인 FC layer의 입력 사이즈가 고정이므로 이 과정을 수행한다.
4. RoI를 CNN에 넣어 feature를 추출
    - 각 region마다 4096-dim feature vector 추출 (2000x4096)
    - Pretrained AlexNet 구조 활용
        - AlexNet 마지막에 FC layer 추가
        - 필요에 따라 finetuning 진행
5. 1) CNN을 통해 나온 feature를 SVM에 넣어 분류 진행
    
    2) CNN을 통해 나온 feature를 regression을 통해 bounding box를 예측
    

### 1.3 Training

- AlexNet
    
    
- Linear SVM
    
    
- Bbox regressor
    
    

### 1.4 Shortcomings

- 2000개의 Region을 각각 CNN 통과
- 강제 Warping, 성능 하락 가능성
- CNN, SVM classifier, bounding box regressor 다 따로 학습
- End-to-End X

## 2. SPPNet

### 2.1 Overview

- RCNN의 2000개의 Region을 각각 CNN에 통과시키는 것과, 강제 Warping 하는 것을 개선함


### 2.2 Spatial Pyramid Pooling


- Conv layers를 통해 나온 feature로부터 다양한 RoI(2000여개)를 추출
- 이후 Spatial Pyramid Pooling Layer를 이용하여 고정된 크기의 vector로 변환

### 2.3 Shortcomings

- CNN, SVM classifier, bounding box regressor 다 따로 학습
- End-to-End X

## 3. Fast R-CNN

### 3.1 Pipeline


1. CNN으로부터 feature 추출 (VGG16)
2. RoI Projection을 통해 feature map 상에서 RoI를 계산
3. RoI Pooling을 통해 일정한 크기의 feature가 추출
4. Fully connected layer 이후, Softmax Classifier과 Bounding Box Regressor

### 3.2 Training

- multi task loss 사용
    - (classification loss + bounding box regression)
- Loss function
    - Classification : Cross entropy
    - BB regressor : Smmoth L1
- Hierarchical sampling
    - R-CNN의 경우 이미지에 존재하는 RoI를 전부 저장해 사용
        - 한 배치에 서로 다른 이미지의 RoI가 포함됨
    - Fast R-CNN의 경우 한 배치에 한 이미지의 RoI만을 포함
        - 한 배치 안에서 연산과 메모리를 공유할 수 있음

### 3.3 Shortcomings

- 진정한 의미의 End-to-End가 아니다→ Selective search

## 4. Faster R-CNN

### 4.1 Pipeline

- Fast R-CNN에 RPN(Regoin Proposal Network)가 추가된 형태


1. 이미지를 CNN에 넣어 feature maps 추출
2. RPN을 통해 RoI 계산 (Region Proposal Network)
    - 기존의 selective search 대체
    - Anchor box 개념 사용
    - binary classification (객체 존재유무)
    - bounding box regression 수행
    
    

### 4.2 Training

- RPN 단계에서 classification과 regressor 학습을 위해 앵커박스를 positive/negative samples로 구분
- Region proposal 이후 Fast RCNN 학습을 위해 positive/negative samples로 구분

### 4.3 Results

- Selective search를 이용해 2000개의 proposals를 뽑은 것보다, RPN을 이용해 300개를 뽑았을 때가 성능이 더 높은 걸 알 수 있다.


### 4.4 Shortcomings

- RCNN의 문제점들을 해결했다.
- 하지만 2 stage이다 보니 속도의 한계가 여전히 존재한다.
