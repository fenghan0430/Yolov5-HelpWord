# **模型识别**

准确来说不是识别，而是使用模型进行推理

## **目录**

1. 确定模型位置
2. 准备图片和视频
3. 推理

## **确定模型位置**

在训练的输出中就已经说明了模型的位置，看输出：

        Results saved to ..\yolov5-master1\runs\train\exp9

在runs\train\exp9(根据实际情况改变)中找到weights文件夹。里面有best.pt，和last.pt，best.pt是一轮训练中最好的模型，我们选这个。

## **准备图片和视频**

把要识别的图片和视频拷贝到detect.py所在的文件夹中

## **推理**

先切换环境

        conda activate yolov5

开始推理

        python detect.py --weights runs/train/exp9/weights/best.pt --source test.jpg
                                   # 这里记得根据实际情况更改模型地址          test.mp4
                                                                           # 这里是识别的文件

识别出来后，他的输出在 runs\detect\exp 中