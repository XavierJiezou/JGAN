# Jittor 第二届草图生成风景比赛

https://cg.cs.tsinghua.edu.cn/jittor/tutorial/2020-5-2-16-43-pytorchconvert/

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

## 结果

| 模型    |       request_id       |    附件    | 提交人 |       提交时间      | 状态 | mask accuary | 美学评分 | FID      | 总分   |
|---------|:----------------------:|:----------:|--------|:-------------------:|------|--------------|----------|----------|--------|
| pix2pix | 2022060514012058791511 | result.zip | 邹学超 | 2022-06-05 14:01:20 | 完成 | 0.7847       | 4.5244   | 107.4902 | 0.1775 |
