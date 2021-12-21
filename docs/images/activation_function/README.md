# 激活函数

## softmax激活函数，常用于分类网络
```text
Out[i, j] = \frac{\\exp(X[i, j])}{\sum_j(exp(X[i, j])}
```
![](softmax.png)
* i表示batch_size中的索引，

## PyTorch定义的激活函数
* [常见激活函数](https://pytorch.org/docs/stable/nn.html#loss-functions)
