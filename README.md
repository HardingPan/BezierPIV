# BezierPIV

## 环境配置
python version:3.11  
```
<!-- 本项目主要基于pytorch机器学习框架 -->
conda install pytorch torchvision torchaudio pytorch-cuda=11.8 -c pytorch -c nvidia
<!-- 本项目的数据可视化通过plt实现 -->
conda install matplotlib

```

## 算法介绍
本项目使用的是三阶Bezier曲线，曲线方程为：
$$\mathbb{B}(t)=p_0{(1-t)}^3+3p_1t{(1-t)}^2+3p_2(1-t)t^2+p_3t^3$$
代码表示为
```python
p0 * np.power((1 - t), 3) + 3 * p1 * t * np.power((1 - t), 2) + 3 * p2 * (1 - t) * np.power(t, 2) + p3 * np.power(t, 3)
```
### Bezier平滑算法
分清平滑与拟合：平滑后的曲线，一定经过原始的数据点；而拟合曲线，则不一定要经过原始数据点。

一般而言，需要平滑的数据分为两种：时间序列的单值数据和时间序列的二维数据。 对于前者，并非一定要用贝塞尔算法，仅用样条插值就可以轻松实现平滑；而对于后者，不管是```numpy```还是```scipy```提供的那些插值算法，就都不适用了。

基于三阶贝塞尔曲线，实现时间序列的单值数据和时间序列的二维数据的平滑算法，可满足大多数的平滑需求。
## 文件说明
### bezier.py
用于存放模型内bezier相关代码
refer to: *https://www.aiuai.cn/aifarm1570.html*


