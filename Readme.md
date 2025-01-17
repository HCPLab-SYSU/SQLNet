# SQLNet

Official Implementation for SQLNet: Scale-Modulated Query and Localization Network for Few-Shot Class-Agnostic Counting

## Introduction

We propose a novel localization-based  CAC approach, termed Scale-modulated Query and Localization Network (SQLNet). It fully explores the scales of exemplars in both the query and localization stages and achieves effective counting by accurately locating each object and predicting its approximate size.

## Qualitative Results

The three columns are ground truth, predicted target points and predicted target bounding boxes.

![image1](asserts/example(1).png)
![image2](asserts/example(2).png)
![image3](asserts/example(3).png)
![image4](asserts/example(4).png)
![image5](asserts/example(5).png)
![image6](asserts/example(6).png)
![image7](asserts/example(7).png)
![image8](asserts/example(8).png)
![image9](asserts/example(9).png)
![image10](asserts/example(10).png)
![image11](asserts/example(11).png)


## Evaluation on Datasets

Result on FSC-147 dataset & Checkpoint:

| Val MAE | Val MSE | Test MAE | Test MSE | Checkpoint |
| :-----: | :-----: | :------: | :------: | :--------: |
|  12.40    |  42.30    |   12.49    |   80.8    |  [Download](https://drive.google.com/file/d/19t8etURqM5Qch97q-Rn5ySXd9jDAoj5g/view?usp=sharing) |

Result on CARPK dataset:

|                        |    Method   |  MAE  |  MSE  |
|:----------------------:|:-----------:|:-----:|:-----:|
| Pre-trained on FSC-147 |     GMN     | 32.92 | 39.88 |
|                        |    FamNet   | 28.84 | 44.47 |
|                        |    BMNet+   | 10.44 | 13.77 |
|                        |  SAFECount  | 16.66 | 24.08 |
|                        | SQLNet(ours) |  7.66 |  9.66 |
|   Fine-tuned on CARPK  |     GMN     |  7.48 |  9.90 |
|                        |    FamNet   | 18.19 | 33.66 |
|                        |    BMNet+   |  5.76 |  7.83 |
|                        |  SAFECount  |  5.33 |  7.04 |
|                        | SQLNet(ours) |  4.89 |  6.55 |

## Test

``` shell
python test.py --vis --data_path /path/to/dataset --model_path ./path/to/pretrain_weight.pth
```


Note: Backbone(Resnet50) pre-trained parameters are automatically loaded and only part of them will be used by our model.

## Code

* [x] Test code & Pre-trained model
* [ ] Training code