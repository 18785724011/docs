# 前端图片处理 - 高斯模糊

## 前言
[高斯模糊](https://baike.baidu.com/item/%E9%AB%98%E6%96%AF%E6%A8%A1%E7%B3%8A/10885810?fr=aladdin)在图片处理中是比较常见的一种处理，其视觉效果就像是经过一个半透明屏幕在观察图像。这篇文章会基于[webgl](https://baike.baidu.com/item/WebGL/592485?fr=aladdin)展示一种通用的算法实现，以及针对大图的优化。

高斯模糊使用[正态分布](https://baike.baidu.com/item/%E6%AD%A3%E6%80%81%E5%88%86%E5%B8%83)来计算当前像素周围和自身的权重，并将这些权重和对应的rgb值相乘，加总再除以总权重。

## 正态分布

首先介绍下状态分布，
