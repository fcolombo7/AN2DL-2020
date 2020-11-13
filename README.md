# AN2DL Challenges
Artificial Neural Networks and Deep Learning @ PoliMi, a.y. 2020

- Filippo Colombo (**@fcolombo7**)
- Giovanni Del Vecchio (**@giovannidv8**)

---
### Note
* [Hyperparameter Optimization with Scikit-Learn, Scikit-Opt and Keras](https://towardsdatascience.com/hyperparameter-optimization-with-scikit-learn-scikit-opt-and-keras-f13367f3e796)
* [K-Fold in KerasTuner](https://mc.ai/how-to-do-cross-validation-in-keras-tuner/) 
* [Hyperparameter Optimization with Keras](https://towardsdatascience.com/hyperparameter-optimization-with-keras-b82e6364ca53)
---

### Results history

| Filename      | Result        | input size  | FExtr. depth | kernel size | stride | Class. HiddenLayer | Class. units | DropOut | L2 | base_model |
| ------------- |:-------------:| -----------:|-------------:|------------:|-------:|-------------------:|-------------:|--------:|---:|-----------:|
| results_Nov11_09-10-27.csv | 0.70666 | 512x512 | 6 | 3x3 | (1,1) | 1 | 256 | - | - | - |
| results_Nov11_13-39-53.csv | 0.57333 | 254x256 | 4 | 3x3 | (2,2) | 2 | 128 | 0.2 | 0.001 | - |
| results_Nov11_09-38-44.csv | 0.58444 | 128x128 | 6 | 3x3 | 1 | 3 | 64 | - | - | - |
| results_Nov12_21-27-13.csv | 0.70666 | 256x256 | 5 | 3x3 | 1 | 1 | 512 | 0.2 | 0.001 | - |
| results_Nov12_21-36-14.csv | **0.84222** | 256x256 | - | - | - | 1 | 256 | - | - | VGG16 |
| results_Nov12_21-36-14.csv | 0.77111 | 256x256 | - | - | - | 1 | 512+128 | - | - | VGG16 |
| ----.csv | ----- | 400x400 | - | - | - | 1 | 448 | 0.1 | - | VGG16 |
