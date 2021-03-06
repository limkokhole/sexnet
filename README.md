
##　sexnet
本程序的主要目的是训练简单的网络能够高效的进行不良图片的二分类.

主要包括两个部分:

1. 训练GAN网络 ,包括生成器和判别器
本网络利用生成对抗网络(Generative Adversarial Nets , GAN) 训练生成图片. 网络架构主要采用类似[DCGAN](https://arxiv.org/abs/1511.06434),  训练方法借鉴最新论文[Wasserstein GAN .](https://arxiv.org/abs/1701.07875)

2. Finetune 网络, 主要是在GAN网络的判别器作为网络提取层, 添加三个全连接层, Finetune网络参数, 使得网络能够用于二分类判别. 

### 训练结果
最终实现了一个极小化的网络:

- 只有四层卷积, 三层全连接
- 全连接的隐藏层的隐藏元只有2048 而非4096
- 输入图片只要64*64即可
- 参数数量, 网络深度都小于AlexNet 和　VGG．
- 内存占用更加

### 文件说明
WGAN-0.ipynb : 最初用来训练WGAN的代码
WGAN.ipynb : 加深了生成器之后用来训练的WGAN代码, 参考WGAN官方实现
finetune.ipynb : 在WGAN-0的判别器的基础之上真假全连接层进行finetune  
Test.ipynb: 测试集的准确率计算

### 声明
**禁止使用本程序进行任何非法行为**


