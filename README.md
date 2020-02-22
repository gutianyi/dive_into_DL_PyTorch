[TOC]

# 动手深度学习 pytorch 

### <u>Day1</u>

线性回归;softmax;mlp

##### 线性回归

**过程**:

1. 读取数据集 建立dataloader
2. 定义模型 
3. 初始化模型参数

```python
init.normal_(net[0].weight, mean=0.0, std=0.01)
init.constant_(net[0].bias, val=0.0)  # or you can use `net[0].bias.data.fill_(0)` to modify it directly
```

4. 定义损失函数  优化函数

5. 训练

**Tips:**

* pytorch 中loss和optimizer是累加的  loss_func 是得到sum()值 https://www.zhihu.com/question/303070254



##### Tensor中的backward()

>  正常情况下需要标量才能进行backward 或者使用

**下面情况下  不使用标量也可以用backward()函数来求导：**

```python
y.backward(torch.tensor([1.0,1.0,1.0,1.0]))
```

所以我们可以得到：

- 如果你要求导的是一个**标量**，那么**gradients默认为None**，所以前面可以直接调用`J.backward()`就行了

- 如果你要求导的是一个**张**量，那么**gradients应该传入一个Tensor**。

  有时候我们可能会有多个输出值，比如loss=[loss1,loss2,loss3]，那么我们可以**让loss的各个分量分别对x求导**，这个时候就采用：
  `loss.backward(torch.tensor([[1.0,1.0,1.0,1.0]]))`



