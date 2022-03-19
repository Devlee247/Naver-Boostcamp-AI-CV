## (02강) Annotation Data Efficient Learning

1. Data augmentation
    1. Learning representation of dataset
    2. Data augmentation
    3. Various data augmentation methods
    4. Modern augmentation techniques
2. Leveraging pre-trained information
    1. Transfer learning
    2. Knowledge distillation
3. Leveraging unlabeled dataset for training
    1. Semi-supervised learning
    2. Self-training

### 1. Data augmentation


왼쪽의 data를 오른쪽 처럼 만들려고 노력하는 거라 생각하면 된다.

- Rotate
- Brightness
- Crop
- Shear
- Perspective
- etc

### 2. Transfer learning
→ 한 데이터 셋에서 배운 지식을 다른 데이터 셋에 활용하는 방식

- Approach 1 : Transfer knowledge from a pre-trained task to a new task

- Approach 2 : Fine-tuning the whole model

**Knowledge distillation**

Unsupervised learning - data가 label이 없는 경우

Teacher Model의 Output과 Student Model의 Output의 KL div. Loss를 줄이는 방법으로 학습. 즉 Student Model이 Teacher Model의 패턴을 따라간다?라고 생각하면 될 듯.

data가 label이 존재하는 경우 Softmax with T

Teacher Model을 따라가는 것 + Label이 있으니 Cross Entropy를 이용해 데이터를 학습하는 것을 합쳐서 학습을 한다.


**Semi-supervised learning**

Unsupervised + Supervised를 모두 합친 학습 방법이라 생각하면 된다.

**Self-training**

- Augmentation + Teacher-Student networks + semi-supervised learning
