# 一 统计学习方法概论

## 1. 1 统计学习

**统计学习的方法：**

- 监督学习
- 非监督学习
- 半监督学习
- 强化学习



## 1.2 监督学习

**预测任务：**

- 回归问题 ： 连续变量
- 分类问题 ： 有限个离散变量
- 标注问题 ： 变量序列



## 1.3 统计学习三要素

**方法 = 模型 + 策略 + 算法**

### 模型

**条件概率分布 或 决策函数**

### 策略

**选取最优模型：**

- 损失函数 ：度量模型一次预测的好坏
- 风险函数 ： 度量平均意义下的模型预测的好坏

**损失函数：**

- 0-1 损失函数 ： $L(Y, f(X)) = (1 ,Y not f(X) | 0 , Y is f(X))$ *注： 分类问题*
- 平方损失函数： $L(Y, f(X)) = (Y - f(X) )^2$
- 绝对损失函数： $L(Y, f(X)) = |Y - f(X) |$
- 对数损失函数： $L(Y, P(Y|X)) =  - log P(Y|X) $

*损失函数值越小，模型越好*

对于给定的一个训练数据集，模型f(X)关于其的平均损失称为经验风险：$R_{emp}(f) = \frac{\sum L(y_i , f(x_i))}{N}$



**经验风险最小化与结构风险最小化**

1.  **经验风险最小化** ： $min R_{erm}(f) = min \frac{\sum L(y_i , f(x_i))}{N}$ 

 要求要有足够大的样本容量； 当样品容量很小时，容易产生”过拟合“现象；

2. **结构风险最小化** ： 为了防止过拟合，等价于正则化； 结构风险在经验风险的基础之上加上表示模型复杂度的正则化项或罚项； $R_{srm}(f) = \frac{\sum L(y_i , f(x_i))}{N} + \alpha J(f)$ *模型f越复杂，复杂度J(f)越大*；因此：  $min R_{srm}(f) = min \frac{\sum L(y_i , f(x_i))}{N} + \alpha J(f)$



## 1.4 模型评估与模型选择

### 训练误差与测试误差

**统计学习的目的不仅仅是为了能够使学习到的模型对已知数据，更是为了能够对未知数据都有很好的预测能力**
