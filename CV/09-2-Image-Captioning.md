## Image captioning

### Encoder

- CNN을 이용
- pretrained ImageNet ResNet-101을 사용한다
- 마지막 2 레이어를 제외하고 사용한다 → 우리는 classification을 하는 것이 아니므로

### Decoder

- RNN + attention module
- Encoder로부터 나온 vector를 RNN에 넣는다
- Using Beam searchn