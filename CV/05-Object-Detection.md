## 1. Object detection

### 1.1 What is object detection?

- Classification + Box localization

### 1.2 What are the applications of object detection?

- Autonomous driving
- Optical Character Recognition

## 2. Two-stage detector (R-CNN family)

### 2.1 R-CNN

1. Extract region proposals (~2k)
2. Compute CNN features (classifier)
- proposals에 대해 하나하나 CNN을 돌리기 때문에 속도가 매우 느리다

### 2.2 Fast R-CNN

- R-CNN을 개선하기 위해 나옴
- Recycla a pre-computed feature for multiple object detection
1. Convolution feature map from the original image
2. RoI feature extraction from the feature map through **RoI Pooling**
3. Class and box prediction for each RoI
- 그러나 Region proposal을 알고리즘을 이용하고 있어, 데이터만으로 성능을 향상시키기에는 한계가 있었다.

### 2.3 Faster R-CNN

- End-to-end object detection by neural region proposal
- Time-consuming selective search → **Region Proposal Network (RPN)**
- **Non-Maximum Suppressions (NMS)**

## 3. Single-stage detector

### 3.1 YOLO

- You Only Look Once

### 3.2 SSD

- Single Shot MultiBox Detector (SSD)
- The use of **multi-scale** outputs attached to **multiple feature maps** enable effectively modeling a diverse space of possible box shapes

## 4. Single-stage detector vs. two-stage detector

- **Single-stage detectors** are prone to **Class imbalance problem**

### Focal loss

- Improved cross entropy loss
- Deal with class imbalance
    - Over-weights hard or misclassified examples
    - Down-weights easy examples

### RetinaNet

- one-stage network
- **Feature Pyramid Networks (FPN) + class/box prediction branches**

## 5. Detection with Transformer

- Transformer has shown a great success in NLP

→ ViT (Vision Transformer) by Google

→ DeiT (Data-efficient image Transformer) by Facebook

→ DETR (DEtection TRansformer) by Facebook

### DETR

- Transformer를 Object Detection에 적용한 사례