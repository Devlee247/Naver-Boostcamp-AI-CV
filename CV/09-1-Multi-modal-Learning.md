## 1. Overview of multi-modal learning

Modalities in multi-modal learning

- Vision + Audio
- Vision + Taste

Challenge (1) - Different representations between modalities

Challenge (2) - Unbalance between heterogeneous feature spaces


Challenge (3) - May a model be biased on a specific modality


Despite the challenges, multi-modal learning is fruitful and important


## 2. Multi-modal tasks (1) - Visual data & Text

### 2.1 Text embedding

- Characters are hard to use in machine learning
- Map to dense vectors

### 2.2 Joint embedding

**Matching**

- Application - Image tagging
→ Can generate tags of a given image, and retrieve images by a tag keyword as well
→ Combining pre-trained unimodal models
→ Metric learning in visual-semantic space
    
    
- Application - Image & food recipe retrieval

### 2.3 Cross modal translation

**Translating**

- Application - Image captioning
→ CNN for image & RNN for sentence
Show and tell
Encoder : CNN model pre-trained on ImageNet
Decoder : LSTM module
- Text-to-image by generative model → conditional GAN

### 2.4 Cross modal reasoning

**Referencing**

- Visual question answering - Multiple streams (Image stream, Question stream)
    
    

## 3. Multi-modal tasks (2) - Visual data & Audio

### 3.1 Sound representation

- Acoustic feature extraction from waveform to spectrogram
- Sound representation - Fourier transform
→ Short-time Fourier transform (STFT)
   : Fourier transform (FT) on windowed waveform results in frequency-magnitude graph

### 3.2 Joint embedding

**Matching**

- Application - Scene recognition by sound
- SoundNet
    - Learn audio representation from synchronized RGB frames in the same videos
    - Trin by the teacher-student manner
        - Transfer visual knowledge from pre-trained visual recognition models into sound modality
    
    

### 3.3 Cross modal translation

**Translating**

- Speech2Face - speech to image
    
    
- Image-to-speech synthesis

### 3.4 Cross modal reasoning

**Referencing**

- Application - Sound source localization