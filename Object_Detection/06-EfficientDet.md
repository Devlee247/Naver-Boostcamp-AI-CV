# (06강) EfficientDet


## 1. Efficient in Object Detection

### 1.1 Model Scaling

- baseline
- width scaling (channel)
- depth scaling
- resolution scaling


### 1.2 등장배경

- 더 높은 정확도와 효율성을 가지면서 ConvNet의 크기를 키우는 방법(scale up)은 없을까?

### 1.3 어떻게? - Model Scaling

- EfficientNet : width, depth, resolution 모든 차원에서의 균형

### 1.4 무엇을? - Accuracy & Efficiency

- 동일 FLOPS 대비 높은 성능을 가져감

## 2. EfficientNet

### 2.1 등장배경

- 파라미터 수가 점점 많아지고 있는 모델들
- ConvNet은 점점 더 커짐에 따라 더 정확해지고 있음
- 점점 빠르고 작은 모델에 대한 요구 증가

### 2.2 Scale up

- Width Scaling
    - 작은 모델에서 주로 사용됨 (MobileNet, MnasNet)
    - 더 wide한 네트워크는 미세한 특징을 잘 잡아내는 경향이 있고, 학습도 쉬움
    - 하지만, 극단적으로 넓지만 얕은 모델은 high level 특징들을 잘 잡지 못하는 경향이 있음
- Depth Scaling
    - 깊이 쌓는 방법은 ConvNet에서 쓰이는 방법 (DenseNet, Inception-v4)
    - 더 풍부하고 복잡한 특징들을 잡아낼 수 있고, 새로운 태스크에도 잘 일반화됨
    - gradient vanishing problem
- Resolution Scaling
    - 고화질의 input 이미지를 이용하면 미세한 패턴을 잘 잡아낼 수 있음

### 2.3 Accuracy & Efficiency

- Compound Scaling


- Compound Scaling Method


### 2.4 EfficientNet

- MnasNet에 영감을 받음
- $ACC(m) \times [{{FLOPS(m)} \over {T}}]^w$를 최적화 목표
- Accuracy와 FLOPs를 모두 고려한 뉴럴넷을 개발함
- Nas 결과, EfficientNet-B0

## 3. EfficientDet

### 3.1 등장배경

Object Detection은 특히 속도가 중요함

- 모델의 사이즈와 연산량을 고려해 활용 여부가 결정됨
- 특히, Efficiency가 중요함

### 3.2 Challenge

- Efficient multi-scale feature fusion
    - In Neck, Simple Summation
- Model Scaling
    - Previous work focus on large backbone & Image size

### 3.3 Results
