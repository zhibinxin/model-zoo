<!--- SPDX-License-Identifier: Apache-2.0 -->

# SqueezeNet

## Use cases
SqueezeNet models perform image classification - they take images as input and classify the major object in the image into a set of pre-defined classes. They are trained on ImageNet dataset which contains images from 1000 classes. SqueezeNet models are highly efficient in terms of size and speed while providing good accuracies. This makes them ideal for platforms with strict constraints on size.

## Description
SqueezeNet is a small CNN which achieves AlexNet level accuracy on ImageNet with 50x fewer parameters. SqueezeNet requires less communication across servers during distributed training, less bandwidth to export a new model from the cloud to an autonomous car and more feasible to deploy on FPGAs and other hardware with limited memory.

## Model

|Model        |Download  |Download (with sample test data)| ONNX version |Opset version|Top-1 accuracy (%)|Top-5 accuracy (%)|
|-------------|:--------------|:--------------|:--------------|:--------------|:--------------|:--------------|
|SqueezeNet 1.0| [5 MB](model/squeezenet1.0-12.onnx)  |  [5 MB](model/squeezenet1.0-12.tar.gz) |  1.9 | 12|56.85|79.87|

>
> **Note** 
> The performance depends on the test hardware. Performance data here is collected with Intel® Xeon® Platinum 8280 Processor, 1s 4c per instance, CentOS Linux 8.3, data batch size is 1.

## Inference
SqueezeNet 1.0 is converted from Caffe2 -> ONNX.

### Input
All pre-trained models expect input images normalized in the same way, i.e. mini-batches of 3-channel RGB images of shape (N x 3 x H x W), where N is the batch size, and H and W are expected to be at least 224. The inference was done using a jpeg image.

``float[1, 3, 224, 224]``

### Preprocessing
The images have to be loaded in to a range of [0, 1] and then normalized using mean = [0.485, 0.456, 0.406] and std = [0.229, 0.224, 0.225]. The transformation should preferrably happen at preprocessing. Check [imagenet_preprocess.py](../imagenet_preprocess.py) for code.

### Output
The model outputs image scores for each of the [1000 classes of ImageNet](../synset.txt).

``softmaxout_1: float[1, 1000, 1, 1]``

### Postprocessing
The post-processing involves calculating the softmax probablility scores for each class and sorting them to report the most probable classes. Check [imagenet_postprocess.py](../imagenet_postprocess.py) for code.

To do quick inference with the model, check out [Model Server](https://github.com/awslabs/mxnet-model-server/blob/master/docs/model_zoo.md/#squeezenet_v1.1_onnx).

## Dataset
[ImageNet (ILSVRC2012)](http://www.image-net.org/challenges/LSVRC/2012/). 

## Validation
We used MXNet as framework with gluon APIs to perform validation. Use the notebook [imagenet_validation](../imagenet_validation.ipynb) to verify the accuracy of the model on the validation set. Make sure to specify the appropriate model name in the notebook.

### Environment
onnx: 1.9.0 
onnxruntime: 1.8.0

## References
* **SqueezeNet1.0** Model from the papera [SqueezeNet: AlexNet-level accuracy with 50x fewer parameters and <0.5MB model size](https://arxiv.org/abs/1602.07360)
* [MXNet](http://mxnet.incubator.apache.org), [Gluon model zoo](https://mxnet.incubator.apache.org/api/python/gluon/model_zoo.html), [GluonCV](https://gluon-cv.mxnet.io)

* [Intel® Neural Compressor](https://github.com/intel/neural-compressor)
* https://github.com/onnx/models

## Contributors
* [abhinavs95](https://github.com/abhinavs95) (Amazon AI)
* [ankkhedia](https://github.com/ankkhedia) (Amazon AI)
* [mengniwang95](https://github.com/mengniwang95) (Intel)
* [airMeng](https://github.com/airMeng) (Intel)
* [ftian1](https://github.com/ftian1) (Intel)
* [hshen14](https://github.com/hshen14) (Intel)

## License
Apache 2.0