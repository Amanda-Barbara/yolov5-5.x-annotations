# autoanchor.py代码解析

## anchor锚框
* 锚框通过与目标框做iou来判断选择哪一个锚框来计算预测框，进而通过锚框来得到预测框
* 单目标不需要锚框，在多目标检测的情况下需要锚框，选择锚框中与目标框的iou值最大的那一个来计算预测框的信息，
* 不同尺度下的网格单元都有三个锚框，然后选择一个与目标框的iou最大的来计算预测框的信息，进而计算目标框与预测框的损失
* 特征图能够和原图位置对应起来
* 正负样本通常由 gt 和先验框 anchor 匹配生成，参与计算的是 anchor 的和 gt（只有尺寸，没有类别），
  而计算 loss 则是其对应的 predict 和 gt（包含类别信息）。这句话就点明了 3 种框的关系，可以看出 anchor 是桥梁
![](../docs/images/anchor/anchor_box.png)

* 黄色的锚框是蓝色的预测框与红色的目标框之间联系的桥梁，被目标框通过与锚框计算iou而选中的锚框通过公式计算出预测框的位置信息，进而计算出目标框与预测框之间的loss
![](../docs/images/anchor/anchor_box计算机制.png)
  
![](../docs/images/anchor/anchor_box计算机制2.png)

![](../docs/images/anchor/anchor_box对应机制.png)

![](../docs/images/trainval/yolov3训练过程.png)

![](../docs/images/trainval/yolov3测试过程.png)

## check_anchors计算流程

![](../docs/images/anchor/check_anchors.jpg)

## 参考链接
* 1 [anchor概念以及不同算法下的正样本匹配机制](https://murphypei.github.io/blog/2020/10/anchor-loss)





