# **Yolov5 训练模型**

## **目录**

1. 准备数据集
2. 为训练集准备参数文件
3. 开始训练

## **准备数据集**

把数据集文件夹拷贝到train.py所在的文件夹，注意数据集的结构应该是这样：

        Yolo_train # 数据集的名字可以自己取，不要中文
        | - images
        |   | - train
        |   |   | - 1.jpg # 这个文件夹下放图片
        |   |   | - ...
        |   | - val
        |   |   | - 1.jpg # 这个文件夹也需要放图片，但不需要train文件夹那么多
        |   |   | - ...
        | - labels
        |   | - train
        |   |   | - 1.txt # 放images/train下对应的图片的标注文件
        |   |   | - ...
        |   | - val
        |   |   | - 1.txt # images/val下对应的图片的标注文件
        |   |   | - ...

## **为训练集准备参数文件**

打开train.py所在文件夹的data文件夹

新建一个 你的数据集名称.yaml 文件

        # 里面这么写
        path: Yolo_train/ # 文件的路径
        train: images/train # 训练数据的地址
        val: images/val # 验证数据的地址
        names: # 标签请根据实际情况填写
            0: cat
            1: dog

## **开始训练**

先切换环境

        conda activate yolov5

然后开始训练

        python train.py --data data/Yolo_train.yaml
        # --data 后面是你参数的位置
