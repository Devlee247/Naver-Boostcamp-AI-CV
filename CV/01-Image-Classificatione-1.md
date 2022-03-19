## (01강) Image Classification1

What is Computer Vision?

### Alexnet

**LeNet-5** (98년 Yann LeCun에 의해 소개된 simple CNN architecture)

Conv - Pool - Conv - Pool - FC - FC


이 구조에서 많은 부분을 차용함

- Bigger
- Trained with ImageNet (large amount of data)
- Using better activation function **(ReLU)**, regularization technique **(Dropout)**

**Overall architecture**

당시에는 memory 부족으로 인해 2-way로 진행했다.


1-way로 다시 바꾼 구조


3D에서 2D로 바꾸어 줄 때,

- **nn.AdaptivaAvgPool2d((6, 6))**
- **torch.flatten(x, 1)**

두 가지 선택지가 있다. 이 논문에서는 flatten을 선택했다라고 하심.

Local Response Normalization (LRN, deprecated) - 지금은 Batch Normalization을 더 사용한다.


특징

- 11x11의 큰 filter size를 사용했는데 지금은 그렇지 않다.

**Receptive field in CNN**

픽셀의 관심영역을 나타낸다.


### VGGNet

- Deeper architecture
    - 16 and 19 layers
- Simpler architecture
    - NO local response normalization
    - Only 3x3 conv filters blocks, 2x2 max pooling
