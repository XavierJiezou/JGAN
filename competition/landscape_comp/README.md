# Jittor 第二届草图生成风景比赛

## 环境

```bash
git clone https://github.com/Jittor/JGAN.git
cd JGAN/
conda create -n jgan python=3.7
pip install jittor
pip install opencv-python
pip install tensorboardX
pip install protobuf==3.20.1
conda activate jgan
```

## 数据

```bash
cd competition/landscape_comp/
mkdir data
cd data/
wget https://cloud.tsinghua.edu.cn/seafhttp/files/48e14089-ec82-4f5d-8bef-4db43cf7ecad/train.zip
unzip train.zip
wget https://cloud.tsinghua.edu.cn/seafhttp/files/bfe5a730-a528-4dcc-b780-8b22b2b8ce32/val_A_labels_cleaned.zip
unzip val_A_labels_cleaned.zip
mkdir -p val/labels
mv val_A_labels_cleaned/* val/labels
```

## 模型

- [x] baseline

## 训练

- 单卡训练，需要修改脚本里的数据路径

```bash
bash scripts/single_gpu.sh
```

- 多卡训练，需要修改脚本里的数据路径

```bash
bash scripts/multi_gpu.sh
```








注：代码中注释掉了eval的部分，等到测试数据发布之后，您可以取消注释进行评测。也可在训练阶段自动分配一部分数据集为测试集进行训练。