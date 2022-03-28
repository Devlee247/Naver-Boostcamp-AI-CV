# (01강) Object Detection Overview

## 1. Object Detection

### 1.1 Task

- Multiple + Localization + Classification

### 1.2 Real world

- 자율 주행
- OCR
- 의료
- CCTV
- 등등

### 1.3 History


### 1.4 Evaluation

**성능**

mAP (mean average precision)

- 각 클래스당 AP의 평균
    
    필요한 개념
    
    - Confusion matrix
        - TP (True Positive) : 검출 되어야할 것이 검출됨
        - FN (False Negative) : 검출 되어야 할 것이 검출되지 않음
        - FP (False Positive) : 검출 되지 말아야 할 것이 검출 됨
        - TN (True Negative) : 검출되지 말아야할 것이 검출되지 않았음
        
        
    - Precision & Recall
    → Precision : 검출한 것 중에 얼마나 맞게 검출했는가?
        
        → Recall : 검출되어야 할 것 중에 얼마나 맞게 검출했는가?
        
        $$
        Precision = {TP \over (TP + FP)} = {TP \over All Detections}
        $$
        
        $$
        Recall = {TP \over TP+FN} = {TP \over {All Ground truths}}
        $$
        
    - PR curve
        - Prediction 결과를 confidence로 sort
        - 이후 누적 결과를 통해 Precision, Recall 그래프 생성
        - PR curve
    - AP (Average Precision)
        - PR curve의 면적
    - IOU (Intersection Over union)
        - mAP50 (mAP + IOU50)
        - mAP60 (mAP + IOU60)
        - ...
    
- 속도 : FPS, Flops
    - FPS : Frames per second
    - Flops : 연산량 횟수

### 1.5 Library

- MMDetection
- Detectron2
- YOLOv5
- EfficientDet

## 2. Lecture

### 2.1 Curriculum

### 2.2 Special mission

### 2.3 ETC