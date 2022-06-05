# Faster R-CNN-3-method

## 文件结构：
```
  ├── backbone: 特征提取网络，可以根据自己的要求选择
  ├── network_files: Faster R-CNN网络（包括Fast R-CNN以及RPN等模块）
  ├── train_utils: 训练验证相关模块（包括cocotools）
  ├── my_dataset.py: 自定义dataset用于读取VOC数据集
  ├── train_mobilenet.py: 以MobileNetV2做为backbone进行训练
  ├── train_mobilenet_rdm.py: 随机初始化训练VOC
  ├── train_resnet50_fpn.py: 以resnet50+FPN做为backbone进行训练
  ├── predict.py: 简易的预测脚本，使用训练好的权重进行预测测试
  ├── validation.py: 利用训练好的权重验证/测试数据的COCO指标
  └── pascal_voc_classes.json: pascal_voc标签文件
```

## 预训练权重下载地址（下载后放入backbone文件夹中）：
* MobileNetV2 backbone: https://download.pytorch.org/models/mobilenet_v2-b0353104.pth
* ResNet50+FPN backbone: https://download.pytorch.org/models/fasterrcnn_resnet50_fpn_coco-258fb6c6.pth
* 注意下载的预训练权重记得要重命名！

## 训练方法
* 提前准备好数据集
* 提前下载好对应预训练模型权重
* 训练随机初始化mobilenetv2+fasterrcnn，使用train_mobilenet_rdm.py训练
* 训练mobilenetv2+fasterrcnn，使用train_mobilenet.py训练
* 训练resnet50+fpn+fasterrcnn，使用train_resnet50_fpn.py训练

## 测试单张图片方法
* 在网盘中下载训练好的模型，放到save_weights文件夹中
* 修改predict.py中的模型部分，用三种方法进行测试
* 修改predict.py中的模型位置，例如weights_path = "./save_weights/random-model-20.pth"
* 运行predict.py脚本


Github 代码链接：https://github.com/ivorytan/Faster-RCNN-3-method
模型下载网盘链接：链接：https://pan.baidu.com/s/1cSeU7aDIZTzTfgY6KSS2mg 提取码：go6s
