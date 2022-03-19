## 1. Conditional generative model

### 1.1 Conditional generative model

- Translating an image given “condition”


- Generative Model
→ Generating random bag images
- Conditional generative model
→ Generating random bag images given a sketch


- (Basic) GAN vs. Conditional GAN

### 1.2 Conditional GAN and image translation

- **Image-to-Image translation**
    
    Translating an image into another image
    
    - Many applications : Style transfer, Super resolution, Colorization

## 2. Image translation GANs

### 2.1 Pix2Pix

- If only using L1 loss, blurry images are generated
- Supervised learning
- GAN (adversarial) loss induces more realistic outputs close to real distribution
- Total loss (GAN loss + L1 loss)

### 2.2 CycleGAN

- In Pix2Pix, we need “pairwise data”. However, it is hard or impossible to get a pairwise dataset.
- CycleGAN loss = GAN loss (in both direction) + Cycle-consistency loss
    - GAN loss : Translate an image in domain A to B, and vice versa
    - Cycle-consistency loss : enforce the fact that an image and its manipulated one by going back-and-forth should be same
    
    solely us GAN loss → Mode Collapse : Regardless of input, the generator could always output the same one!
    

### 2.3 Perceptual loss

- Approach for achieving high quality output
- GAN loss
    - Relatively hard to train and code
    - Do not require any pre-trained networks
    - Since no pre-trained network is required, can be applied to various applications
- Perceptual loss
    - Simple to train and code
    - Requiring a pre-trained network to measure a learned loss

## 3. Various GAN applications

- Deepfake
- Face de-identification
- Video translation