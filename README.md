# Multimodal identification model for occluded faces in the context of COVID-19

We propose a multi-modal identification model for human authentication using face, voice, and demographic information(age, gender, and race). We also propose demographic module to utilize demographic information in the proposed model. In addition, we train the proposed model using unmasked and masked faces to compensate low performance in case of masked faces. The overview of our proposed model is as follows:

<img src= 'https://user-images.githubusercontent.com/41101841/157562028-e496c430-d99e-4699-b064-d61a8cf9ba61.jpg' width=60%>

Our experiment sequences are as follows:

1. Masking face
We used MaskTheFace model to augment our sampled dataset. MaskTheFace is a publicly available package that converts the face images into masked-face images.
MaskTheFace's github: https://github.com/aqeelanwar/MaskTheFace

```
!python MaskTheFace.py
```

2. Extracting demographic information(age, gender, and race)
To extract demographic information from face images, we use LightFace libray, which is a face recognition and facial attribute analysis framework.
LightFace's github: https://github.com/serengil/deepface

```

```

3. Aligning data (face-voice)
Since we used separate face images and voice files from different data sets, we had to align the face and voice data to create virtual identities for testing purposes. We randomly selected 10 classes of face and voice data and matched them one by one. Following figure shows example of aligning data method.

<img src='https://user-images.githubusercontent.com/41101841/157564085-cc4624e3-284f-4152-9f1a-b503c8c800a2.jpg' width=50%> 

```

```

4. training and testing multimodal identification model
We train the proposed model using face, voice, and demographic features on unmasked and masked faces.
```

```
