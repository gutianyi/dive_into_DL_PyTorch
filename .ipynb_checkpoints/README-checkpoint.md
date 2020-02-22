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
* 

