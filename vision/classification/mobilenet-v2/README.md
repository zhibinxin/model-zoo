<!--- SPDX-License-Identifier: Apache-2.0 -->

# MobileNet v2

## Description
MobileNet improves the state-of-the-art performance of mobile models on multiple tasks and benchmarks as well as across a spectrum of different model sizes. MobileNet is based on an inverted residual structure where the shortcut connections are between the thin bottleneck layers. The intermediate expansion layer uses lightweight depthwise convolutions to filter features as a source of non-linearity. Additionally, it removes non-linearities in the narrow layers in order to maintain representational power.

## Model
|Model              |Download                       |ONNX version   |Opset version  |Top-1 accuracy (%) |Top-5 accuracy (%) |
|-------------------|:------------------------------|:--------------|:--------------|:------------------|:------------------|
|MobileNet v2-1.0   |[13.6 MB](mobilenetv2-7.onnx)  |1.2.1          |7              |70.94              |89.99              |

## Dataset
[ImageNet (ILSVRC2012)](http://www.image-net.org/challenges/LSVRC/2012/).

## References
* **MobileNet-v2** Model from the paper [MobileNetV2: Inverted Residuals and Linear Bottlenecks](https://arxiv.org/abs/1801.04381)

* [MXNet](http://mxnet.incubator.apache.org), [Gluon model zoo](https://mxnet.incubator.apache.org/api/python/gluon/model_zoo.html), [GluonCV](https://gluon-cv.mxnet.io)

* [Intel® Neural Compressor](https://github.com/intel/neural-compressor)

* [https://github.com/onnx/models](https://github.com/onnx/models/tree/main/vision/classification/mobilenet)

## Contributors
* [ankkhedia](https://github.com/ankkhedia) (Amazon AI)
* [abhinavs95](https://github.com/abhinavs95) (Amazon AI)
* [mengniwang95](https://github.com/mengniwang95) (Intel)
* [airMeng](https://github.com/airMeng) (Intel)
* [ftian1](https://github.com/ftian1) (Intel)
* [hshen14](https://github.com/hshen14) (Intel)

## License
Apache 2.0
