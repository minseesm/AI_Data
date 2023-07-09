# AI_Data

## Introduction
##### Code I used while studying AI application to health issues using Pytorch, A program that can analyze and diagnose datasets for Alzheimer's and the other is for lung cancer.

## Dataset
I chose a few items from Kegel. The first dataset was downloaded from the link below as MRI photos of Alzheimer's over time. The second dataset is about information on lung cancer patients and is downloaded from the link below.

1. Alzheimer :
   Link : https://www.kaggle.com/datasets/lukechugh/best-alzheimer-mri-dataset-99-accuracy
![Screenshot 2023-07-09 at 12 27 22 PM](https://github.com/minseesm/AI_Data/assets/102398789/1f90999b-ab5d-4c32-92ca-6b39814f654b)
   It consists of a total of 11519 data and is divided into No, Very Mild, Mild, and Moderate according to Alzheimer's progress.
   Among them, 1,0240 were used as training sets and 1,279 were used as test sets.

2. Lung Cancer :
   Link : https://www.kaggle.com/datasets/mysarahmadbhat/lung-cancer
   
   There are a total of 309 data sets, and the columns consist of 
   GENDER, AGE, SMOKING, YELLOW_FINGERS, ANXIETY, PEER_PRESSURE, CHRONIC DISEASE, FATIGUE, ALLERGY,
   WHEEZING, ALCOHOL CONSUMING, COUGHING, SHORTNESS OF BREATH, SWALLOWING DIFFICULTY, CHEST PAIN, LUNG_CANCER.

   Among them, 280 were used as training sets and 29 were used as test sets.


## Environment
  Python 3.8.16
  Pytorch 2.0.1
  Matplotlib 3.7.1
  PIL (pillow) 9.4.0
  Scikit-learn 1.0.2
  Pandas 1.5.3
  Numpy 1.23.5

## Model Structure
1. Alzheimer : CNN
                (layer): Sequential(
                  (0): Conv2d(1, 32, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))
                  (1): MaxPool2d(kernel_size=2, stride=2, padding=0, dilation=1, ceil_mode=False)
                  (2): Conv2d(32, 64, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))
                  (3): MaxPool2d(kernel_size=2, stride=2, padding=0, dilation=1, ceil_mode=False)
                  (4): Conv2d(64, 128, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))
                  (5): MaxPool2d(kernel_size=2, stride=2, padding=0, dilation=1, ceil_mode=False)
                  (6): Conv2d(128, 256, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))
                  (7): MaxPool2d(kernel_size=2, stride=2, padding=0, dilation=1, ceil_mode=False)
                )
                (fc): Sequential(
                  (0): Linear(in_features=16384, out_features=4, bias=True)
                )
              )
3. LungCancer : FNN
                (layer): Sequential(
                    (0): Linear(in_features=15, out_features=200, bias=True)
                    (1): ReLU()
                    (2): Linear(in_features=200, out_features=200, bias=True)
                    (3): ReLU()
                    (4): Linear(in_features=200, out_features=1, bias=True)
                    (5): ReLU()
                  )
                )
   
## Run (with demo and pretrained)
  Alzheimer/run.py
  LungCancer/run.py

## Result
1. Alzheimer
   ### Training : 10240 photos
   ![50E_0 0001](https://github.com/minseesm/AI_Data/assets/102398789/e2ed0087-b0d1-427e-8752-36f3ff242393)

   ### Test : 1279 Photos, Accuracy : 93.9 %

3. LungCancer
   ### Training : 10240 photos
   ![200E_0 0001](https://github.com/minseesm/AI_Data/assets/102398789/2fface33-2a59-4a42-b549-6f9b5a78c14e)

   ### Test : 29 rows, Accuracy : 97.7%

   
