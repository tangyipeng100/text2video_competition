

# 文生视频项目文档

本项目旨在探究不同数据筛选方式对文生视频大模型性能的影响。以下是项目的核心流程、所需资源以及模型训练与评测的简要介绍。

![](./文生视频.jpg)

## 项目概述

该项目的主要目标是通过高效的数据筛选和高质量视频文本对的生成，提升文生视频大模型的整体性能。我们基于现有的预训练模型进行数据处理、模型训练和评测，旨在探索数据质量对生成效果的影响。

## 资源需求

- **计算资源**: NVIDIA A100 GPU (2卡)
- **存储资源**: 1TB

## 数据筛选流程

### 1. 视频片段筛选

我们通过多个筛选器对提供的原始视频数据进行筛选。筛选器根据视频的运动特征、图像美学、文字识别、敏感内容和水印等方面的特征，保留高质量的样本。这一步的目标是提高后续模型训练数据的质量，确保模型学习到的信息更为有效。

### 2. 视频描述生成

在视频片段经过筛选后，我们使用视频字幕生成模型为每个视频片段生成描述文本。生成的文本与视频片段配对，形成高质量的视频-文本对，这些对将用于后续模型的训练。

### 3. 带有描述的样本筛选

对于生成了描述的视频片段，我们进一步使用相似性分析与困惑度筛选等方法，筛选出符合预期质量的样本，进一步提升数据的精确度与模型训练的有效性。

### 4. 高质量视频文本对的生成

这一阶段的结果是高质量的视频文本对，它们将被用于文生视频模型的训练和评测。

## 模型训练与推理

### 1. 模型训练

模型训练采用标准的流程，基于高质量的视频文本对，使用预设的训练参数进行训练。训练过程中使用了混合精度训练策略，以提高效率并减少计算资源的消耗。

### 2. 模型推理

在模型训练完成后，我们使用优化的推理脚本对视频进行推理。模型将生成相应的视频描述，并进行视频的生成与重构。

## 模型评测

评测部分直接通过线上平台对模型的生成效果进行打分。该评测过程涵盖了模型生成视频的文本相关性、视频质量以及生成的一致性等多个指标。

## 致谢
感谢 上海人工智能实验室组织的书生:浦语大模型实战营学习活动 和 提供的强大算力支持~  
感谢 OpenXLab 对项目部署的算力支持  
感谢 浦语小助手 对项目的支持  
[InternLM](https://github.com/InternLM/InternLM)  
[Tutorial](https://github.com/InternLM/Tutorial)



