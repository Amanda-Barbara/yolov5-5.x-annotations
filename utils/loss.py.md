# loss.py代码解析

## loss求解
* 框的预测值，以及目标框都要映射到特征层上，loss是在特征层上进行求解的，

## yolov5边框回归机制
* yolov5采用了跨邻域网格的正样本匹配策略，这样可以得到更多的正样本anchor，加速收敛

## ComputeLoss计算
* [BCEWithLogitsLoss](https://flyfish.blog.csdn.net/article/details/118909723)

## 浮点取模
* [浮点取模](https://flyfish.blog.csdn.net/article/details/119276814)

## 参考链接
* 1 [loss求解](https://mp.weixin.qq.com/s?__biz=MzU5NTg2MzIxMw==&mid=2247486712&idx=1&sn=f56a342fbba7b155f2dfdf84776ac17e&chksm=fe6a3f3ac91db62caefd100a712717fb0663b4066bdd64e2fdc7a80c526d7cbcf8d6f4aa6a94&scene=178&cur_album_id=1826437164776095749#rd)

