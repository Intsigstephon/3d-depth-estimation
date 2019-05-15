## Motivation
活体检测技术升级， 从动作活体到腾讯的极光守卫方案。

## Technique idea
整体方案中包含一个技术点： 从单张图像/整个视频中得到深度图像， 也即图像深度估计； 因此，针对这一课题，做了部分调研

## State of the art
近些年的文章， 基本都采用无监督的方案； 主要是因为深度图像需要特殊的硬件辅助， 难以获取； 因此只能另辟蹊径。 
双目图像容易获取， 因此可以充分利用。

# Analysis
所谓使用非监督学习来训练就是利用不知道ground truth的输入图片训练来得到深度信息。
既然没有深度的ground truth那肯定有来自于其他地方的约束，比如使用stereo image。
stereo image是来自两个相机（或者双目相机）在同一水平线上左右相距一定位置得到的两幅图片。
这种图片获取的代价要比深度的ground truth 低一些。 
这些方法利用了深度信息和场景之间的一些物理规律来约束，得到了很不错的结果. 
以下为该思路下的三种方法，可以说是一脉相承：

Unsupervised CNN for Single View Depth Estimation: Geometry to the Rescue（2016 ECCV)
Unsupervised Monocular Depth Estimation with Left-Right Consistency (2017 CVPR)
Semi-Supervised Deep Learning for Monocular Depth Map Prediction （2017 CVPR）