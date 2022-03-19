1. **Semantic segmentation**
    1. **What is semantic segmentation?**
    → Image classification을 하나의 pixel 단위로 진행하는 것
    → Image 내에 같은 클래스가 여럿 있어도 서로 분류하지 않는다.
        
    2. **Where can semantic segmentation be applied to?**
    · Medical images
    · Autonomous driving
    · Computational photography
    ****
2. **Semantic segmentation architectures**
    1. **Fully Convolutional Networks (FCN)**
    → First end-to-end architecture for semantic segmentation
    → input : image of an arbitrary size
    → output : sgmentation map of the corresponding size to the input
        
         
        Fully **convolutional** layer : Output a classification map which has spatial coordinates
        
        A 1x1 convolution layer classifies every feature vector of the convolutional feature map 
        
        **It’s time to enlarge the score map by upsampling!**
        
         Upsampling methods
        
        - Unpooling
        - **Transposed convolution**
            
        - **Upsample and convolution**
        먼저 NN or Bilinear를 사용해서 interpolation → conv
        
        Receptive field
        
        
    2. **Hypercolumns for object segmentation**
        
        
    3. **U-Net**
    - Fully Convolutional  
        
    4. **DeepLab**
    Conditional Random Fields (CRFs)