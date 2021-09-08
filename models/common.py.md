# common.py代码解析
## Focus结构
* 对输入图像的每一通道做切片操作，变成4个原输入大小一半的4个切片，3个通道切片后加在一起即是12个切片
* 该模块的设计主要是减少原始信息的丢失，减少计算量加快模型推理速度

## 深度可分离卷积
* 深度可分离卷积将一般的卷积过程分为了`depthwise convolution`（逐深度卷积）和`pointwise convolution`（逐点卷积），
  在损失一点精度的情况下，计算量大幅下降，速度更快，模型更小
```text
c1           : 输入通道数
c2           : 输出通道数
卷积核大小    : k*k
普通卷积的参数量 : c1*k*k*c2
深度可分离卷积的参数量 : c1*k*k + c1*1*1*c2
```
![](../docs/images/base_tutorial/depthwise_separable_convolution.png)
  
  
## 分组卷积
```text
c1           : 输入通道数
c2           : 输出通道数
分组数        : g
卷积核大小    : k*k
普通卷积的参数量 : c1*k*k*c2
分组卷积的参数量 : (c1/g)*k*k*(c2/g)*g
```
* `(c1/g)*k*k*(c2/g)`表示的是一个普通卷积的参数量，即分组卷积中的每一个小组的卷积参数量

![](../docs/images/base_tutorial/groupconv.png)
```text
分组卷积的分组数如果和输入的通道数相同，则此时的分组卷积即为深度可分离卷积
```
## 参考链接
* 1 [Focus结构](https://zhuanlan.zhihu.com/p/172121380)
* 2 [Focus结构](https://mp.weixin.qq.com/s/yO13BjSNG1cEDAxqR-SkHw)
* 3 [深度可分离卷积](https://www.cnblogs.com/sddai/p/14549475.html)
* 4 [分组卷积](https://blog.csdn.net/breeze_blows/article/details/98068025)
* 5 [common.py代码解析](https://blog.csdn.net/qq_38253797/article/details/119684388)
* 6 [same卷积](https://blog.csdn.net/u012370185/article/details/95238828)


