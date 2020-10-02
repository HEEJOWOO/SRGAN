# SRGAN : https://arxiv.org/abs/1609.04802

#### <I studied while referring to various sites, but it is not enough. Thanks anytime for feedback.>
### <heejo5@naver.com>

Photo-Realistic Single Image Super-Resolution Using a GAN
--------------------------------------------------------------------------

* SRGAN 논문을 보게되면 사실적인 사진의 해상도를 4배로 올릴 수 있는 최초의 모델이라고 주장
* Skip-connection을 적용한 Residual Network 구조를 띄고 있고 새로운 목적 함수 perceptual loss또한 제안
* Perceptual loss 는 Adversial Loss 와 Content Loss를 같이 사용한 목적 함수
* SRGAN의 목표로는 Discriminator에 사용된 VGG네트워크의 상위 레벨 특징에 대해 원본 img와 Upsamling된 img를 구분하기 힘들도록 학습을 시켜야 하구 LR img를 원본 HR img와 같이 Upsampling 하는 G를 만드는 것 

PSNR/SSIM 비교
-------------
![image](https://user-images.githubusercontent.com/61686244/94898978-6ee15500-04cd-11eb-8efc-2081a89045ac.png)
* PSNR값이 bicubic 보간법이 더 높지만 실제로는 bicubic보다 낮은 psnr값을 가지고 있는 SRGAN이 더 보기에 화질이 뚜렷

LR img , HR img 관계 / Perceptual Loss + Content Loss
-----------------------------------------------------
![image](https://user-images.githubusercontent.com/61686244/94899492-65a4b800-04ce-11eb-89a3-1ac2b5542d3b.png)

Advdrsarial Loss
----------------
![image](https://user-images.githubusercontent.com/61686244/94899524-77865b00-04ce-11eb-8b29-9854d4dcb5ea.png)

Content Loss
------------
![image](https://user-images.githubusercontent.com/61686244/94899576-8a009480-04ce-11eb-8543-cd6e7a8c2072.png)

SRGAN Architecture
------------------
![image](https://user-images.githubusercontent.com/61686244/94899682-b0263480-04ce-11eb-9e0c-5a3be620d817.png)

Mos 결과
-------
![image](https://user-images.githubusercontent.com/61686244/94899773-d946c500-04ce-11eb-923b-7cea82a975ca.png)

4x upscalng 비교
---------------
![image](https://user-images.githubusercontent.com/61686244/94899822-ec599500-04ce-11eb-9c0b-4b78b017c82d.png)

4x upscaling 비교 / BSD 100
---------------------------
![image](https://user-images.githubusercontent.com/61686244/94899920-18751600-04cf-11eb-9211-be1e5df983de.png)

Conclusions
-----------
* 4배의 해상도 향상을 보이는 단일 이미지 SR을 위한 모델을 제안
* 모델은 16개의 Residual Block으로 이루어져 있음
* GAN을 기반으로 Perceptual loss로 트레이닝되는 SRGAN을 제안
* VGG 네트워크 상의 Feature map을 이용하여 계산되는 MSE 기반 Content Loss 사용
* 인간의 평가로 측정하는 점수로, 논문에서 SR로 만든 고해상도 이미지의 품질을 실제 사람들에게 평가 시킨 MOS에서 성능을 보이는 것을 확인


