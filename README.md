# Multi-modal Authentication Model for Occluded Faces in a Challenging Environment

We propose a multi-modal identification model for human authentication using face, voice, and demographic information(age, gender, and race). We also propose a demographic module to utilize demographic information in the proposed model. In addition, we train the proposed model using unmasked and masked faces to compensate for low performance in the case of masked faces. The overview of our proposed model is as follows:
<!-- ![multimodal3](https://user-images.githubusercontent.com/41101841/157573183-39520451-7512-4e2c-ba24-143693d6dd51.jpg) -->

![overall_model (1)](https://github.com/jeongdahye3427/multi-modal-identification/assets/41101841/a3ca4335-8cc3-4d6f-88df-721d0f3fe009)


If you can not see the figure of our model, the figure is available at 'https://url.kr/tyru93'.

Our experiment sequences are as follows:

1. Masking face
We used the MaskTheFace model to augment our sampled dataset. MaskTheFace is a publicly available package that converts the face images into masked-face images.
MaskTheFace's Github: https://github.com/aqeelanwar/MaskTheFace

```
cd MaskTheFace
pip install –r requirements.txt

cd MaskTheFace
# Generic
python mask_the_face.py --path <path-to-file-or-dir> --mask_type <type-of-mask> --verbose --write_original_image

# Example
python mask_the_face.py --path 'data/office.jpg' --mask_type 'N95' --verbose --write_original_image
```

2. Extracting demographic information(age, gender, and race)
To extract demographic information from face images, we use LightFace library, which is a face recognition and facial attribute analysis framework.
LightFace's Github: https://github.com/serengil/deepface

```
Demography/demography.ipynb
```

3. Aligning data (face-voice)
Since we used separate face images and voice files from different data sets, we had to align the face and voice data to create virtual identities for testing purposes. We randomly selected 10 classes of face and voice data and matched them one by one. The following figure shows an example of the aligning data method.

<p align='center'>
<img src='https://user-images.githubusercontent.com/41101841/157564085-cc4624e3-284f-4152-9f1a-b503c8c800a2.jpg' width=50%> 
</p>

4. Training and testing multimodal identification model
We train the proposed model using face, voice, and demographic features on unmasked and masked faces.
If you want to retrain our model with your data, execute the files below. These are mask models and unmask respectively. When you retrain our model, you have to change your data path. And, the code includes aligning the data part.

```
Model/FV_unmask_v2.ipynb
Model/FV_mask_v2.ipynb
```

If you want to train and test our model with our data, you can execute the files below with our feature files. We uploaded demographic features and face features. Because the size of the voice features is big, we uploaded voice features in google drive.

```
Model/FV_unmask_v1.ipynb
Model/FV_mask_v1.ipynb
```
