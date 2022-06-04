# 计图挑战热身赛

## 创建环境

```bash
git clone https://github.com/Jittor/JGAN.git
cd JGAN
conda create -n jgan python=3.7
pip install jittor
conda activate jgan
```

## 修改代码

```bash
vi vi competition/warm_up_comp/CGAN.py
```

1. 第69行下插入一行：`nn.Linear(512, 1)`

```python
# TODO: 添加最后一个线性层，最终输出为一个实数
nn.Linear(512, 1)
```

2. 第74行下插入一行：`return self.model(d_in)`

```python
# TODO: 将d_in输入到模型中并返回计算结果
return self.model(d_in)
```

3. 第170行修改为：

```python
d_real_loss = adversarial_loss(validity_real, valid) # TODO: 计算真实类别的损失函数
```

4. 第173行修改为：

```python
d_fake_loss = adversarial_loss(validity_fake, fake) # TODO: 计算虚假类别的损失函数
```

5. 第198行修改为：

```python
number = "01023456789" #TODO: 写入你注册时绑定的手机号（字符串类型）
```

## 运行代码

- CPU

```bash
python competition/warm_up_comp/CGAN.py
```

- 单 GPU

不指定 GPU ID（默认0卡）

```bash
python competition/warm_up_comp/CGAN.py 
```

指定 GPU ID

```
CUDA_VISIBLE_DEVICES=1 python competition/warm_up_comp/CGAN.py 
```

- 多 GPU

```
CUDA_VISIBLE_DEVICES="0,1,2,3" mpirun -np 4 python competition/warm_up_comp/CGAN.py 
```

## 提交结果

打包成 result.zip 压缩文件，其目录结构如下：

```bash
result/
├── CGAN.py
└── result.png
```
