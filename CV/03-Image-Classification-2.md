## (03강) Image Classification 2

1. **Problems with deeper layers**
    1. **Going deeper with convolutions**
        
        Larger receptive fields
        
        More capacity and non-linearity
        
    2. **Hard to optimize**
        
        Gradient vanishing / exploding problems
        Computationally complex
        Degradation problem
        
2. **CNN architectures for image classification 2**
    1. **GoogLeNet**
    Inception module
    Use 1x1 convolutions as “bottleneck” layers that reduce the number of channels
    
    Stem network : vanilla convolution networks
    Stacked inception modules
    Auxiliary classifiers (something like gradient injection..?)
    2. **ResNet**
    shortcut connection (skip connection)
    He initialization
    3. **Beyond ResNet**
3. **Sumarry of image classification**
    1. **Summary of image classification**
    2. **CNN backbones**