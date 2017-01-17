# Keras Image Caption

This image captioning model is trained on [2014 Microsoft COCO dataset](https://competitions.codalab.org/competitions/3221). It can reach a 0.765 CIDErD score, and it also win the **1st place** with a score 0.67822 Root Mean Square Percentage Error.

## Prerequisites

- Python 3.5+
- Keras
- Pandas
- Numpy

## Features

Most of the features used in the model can be found in the dataset, while the image feature is extracted by [Inception-v3](https://arxiv.org/abs/1512.00567). You can find the pre-trained weight file on tensorflow site.

We take the result from the last pooling layer, which is a 2048-D vector, as image feature.

## Training

The training set contains 102,739 images selected from MSCOCO 2014.

You can start training by:

```
python train.py [initial weights]
```

## Evaluation

The result is evaluated on 20,548 testing images selected from MSCOCO2014, and use CIDErD as the metric.

We have offered a simple evaluation code that will randomly pick images from testing set, produce and print out the generated captions and the ground truth:

```
python evaluation.py [weights file path]
```

## Demo

```
python demo.py [weighs file path]
```

We are able to reach 0.765 CIDErD school, and win the 1st place in the competition.

## Acknowledgements

- Image extractor : [mjhucla : TF-mRNN](https://github.com/mjhucla/TF-mRNN)
- Beamsearch : [udibr : beamsearch](https://gist.github.com/udibr/67be473cf053d8c38730)
