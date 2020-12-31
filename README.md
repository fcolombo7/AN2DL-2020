
# AN2DL Challenges
Artificial Neural Networks and Deep Learning @ PoliMi, a.y. 2020

- Filippo Colombo (**@fcolombo7**)
- Giovanni Del Vecchio (**@giovannidv8**)

--- 
## Challenge 3

* https://github.com/chingyaoc/VQA-tensorflow
* https://medium.com/@harshareddykancharla/visual-question-answering-with-hierarchical-question-image-co-attention-c5836684a180

### Steps and results history

---
## Challenge 2

### Steps and results history
_U-Net like architecture_  
**Bipbip dataset**

| Model Name | IoU Bipbip | Input size | Num of levels | Starting filter depth size | Conv. per block | Regularization | Note |
|-----------:|-----------:|-----------:|--------------:|---------------------------:|----------------:|---------------:|-----:|
| U-Net_s32 | 0.6533 | original | 4 | 32 | 2 | - | no normalization |
| U-Net_s16_norm-input | 0.0669 | original | 4 | 16 | 2 | - | with normalization --- NO! errore sul test set |
| U-Net_s16_adapt-lr+batch_norm | 0.6543 | original | 4 | 16 | 2 | - | batch norm and adaptive learning rate |
| U-Net_sXX_adapt-lr+batch_norm+l1 | --- | original | 4 | 16/32 | 2 | l1 | batch norm and adaptive learning rate, with l1: the net does not learn (both 32 and 16) |
| U-Net_s32_adapt-lr+batch_norm+drop | 0.6642 | original | 4 | 32 | 2 | dropout=0.2 | batch norm, adaptive learning rate [1e-3 - 1e-5] |
| U-Net_s32_adapt-lr_v2+batch_norm+drop | 0.6877  | original | 4 | 32 | 2 | dropout=0.2 | batch norm, adaptive learning rate [1e-4 - 1e-5] |
| U-Net_s32_1convXblock_6depth | 0.6971 | original | 6 | 32 | 1 | - | batch norm, adaptive learning rate [1e-4 - 1e-5] |

---
## Challenge 1

### Note
* [Hyperparameter Optimization with Scikit-Learn, Scikit-Opt and Keras](https://towardsdatascience.com/hyperparameter-optimization-with-scikit-learn-scikit-opt-and-keras-f13367f3e796)
* [K-Fold in KerasTuner](https://mc.ai/how-to-do-cross-validation-in-keras-tuner/) 
* [Hyperparameter Optimization with Keras](https://towardsdatascience.com/hyperparameter-optimization-with-keras-b82e6364ca53)
---

### Results history
_CNN from skratch_ 

|Filename|Result|Input size|Feature extractor depth|kernel size|stride|N. Dense Hidden Layer |N. Neurons (dense layers)|Dropout|L2| info|
|------:|------:|------:|------:|------:|------:|------:|------:|------:|------:|------:|  
| results_Nov11_09-10-27.csv | 0.70666 | 512x512 | 6 | 3x3 | (1,1) | 1 | 256 | - | - | - |
| results_Nov11_13-39-53.csv | 0.57333 | 254x256 | 4 | 3x3 | (2,2) | 2 | 128 | 0.2 | 0.001 | other test with a larger kernel size has been done, but there were no imporvements |
| results_Nov11_09-38-44.csv | 0.58444 | 128x128 | 6 | 3x3 | (1,1) | 3 | 64 | - | - | - |
| results_Nov12_21-27-13.csv | 0.70666 | 256x256 | 5 | 3x3 | (1,1) | 1 | 512 | 0.2 | 0.001 | - |

_CNN with Transfer Learning_  

|Filename|Result|Input size|Base model|N. Dense Hidden Layer |N. Neurons (dense layers)|Dropout|L2| info|
|------:|------:|------:|------:|------:|------:|------:|------:|------:|
| results_Nov12_21-36-14.csv | 0.84222 | 256x256 | VGG16 | 1 | 256 | - | - | - |
| results_Nov12_21-36-14.csv | 0.77111 | 256x256 | VGG16 | 2 | 512+128 | - | - | - |
| results_Nov14_13-40-16.csv | 0.88444 | 400x400 | VGG16 | 1 | 448 | 0.1 | - | - | - |
| results_Nov14.csv | 0.91555 | 400x400 | VGG16 | 1 | 448 | 0.2 | - | **augmentation v2**: rotation_range=20, width_shift_range=0.3, height_shift_range=0.3, zoom_range=0.4, horizontal_flip=True, shear_range=10, channel_shift_range=100, fill_mode='reflect', rescale=1./255
|results_Nov15_10-37-55.csv| 0.94000 | 400x400 |VGG16| 1 | 512 | 0.2 | - | augmentation v2
|results_Nov15_14-31-13.csv| 0.93777 | 400x400 | VGG16 | 2 | 512+448 | 0.1 | - |augmentation v2
|results_Nov15_23-11-35.csv| 0.93333 | 400x400 |VGG16| 2 | 512+512 | 0.2 | - | augmentation v2
|results_Nov16_10-58-01.csv| 0.92000 | 400x400 | VGG16 | 2 | 512+512 | - | 0.001 | augmentation v2
|results_Nov15_10-37-55.csv| 0.94000 | 448x448 | VGG16 | 1 | 576 | 0.2 | - | augmentation v2
|results_Nov17_21-18-42.csv| 0.94000 | 448x448 | VGG16 | 1 | 600 | 0.2 | - | **augmentation v3**: rotation_range=30, width_shift_range=0.2, height_shift_range=0.2, zoom_range=0.4, horizontal_flip=True, brightness_range = [0.6, 1.0], shear_range=30, channel_shift_range=50, fill_mode='reflect', rescale=1./255
|results_Nov18_07-50-09.csv| **0.94444** | 448x448 | VGG16 | 1 | 512 | 0.2 | - | augmentation v2|
