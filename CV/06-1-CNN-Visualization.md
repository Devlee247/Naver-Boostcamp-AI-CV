## 1. Visualizing CNN

### 1.1 What is CNN visualization?

- CNN is a black box
- **Input image** → Low level feature → Middle level feature → High level featyure → **Output prediction**


### 1.2 Vanilla example: filter visualization

- Filter viz. & Activation viz. 진행 (1st conv. layer)
- 이후 layer는 사람이 해석하기가 어려운 형태이다.


### 1.3 How to visualize neural network

- Analysis of **model behaviors
모델 자체의 특성을 분석**하는데 초첨을 둠
- **Model decision** explanation
**모델의 출력을 분석**하는 데 초점을 둠


## 2. Analysis of model behaviors

### 2.1 Embedding feature analysis

- Analyzing high level feature
- **Nearest neighbors (NN) in a feature space**
- **Dimensionality reduction**
t-distributed stochastic neighbor embedding (t-SNE)

### 2.2 Activation investigation

- Analyzing mid&high level feature
- **Layer activation**
- **Maximally activating patches**
- **Class visualization** - Gradient ascent

## 3. Model decision explanation

### 3.1 Saliency test

- **Occlusion map** - Prediction scores change according to the location of mask
    
    
- **via Backpropagation**

### 3.2 Backpropagate features

- Rectified unit (backward pass)

### 3.3 Class activation mapping

- **CAM**
Visualize which part of image contributes to the final decision
→ Global average pooling (GAP) layer instead of the FC layer
    
    하지만 구조를 변경해야함
- **Grad-CAM**
Get the CAM result without modifying and re-training the original network