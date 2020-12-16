# OpenCv
学习OpenCv的笔记以及代码

#### 第一章.显示图像

  - namedWindow函数创建指定名称的窗口，一般不用
  - imshow函数显示图像，直接imshow(窗口名称，图)创建窗口顺带显示图像
  - waitkey函数等待按键，相当于switch case
  - destroyWindow函数销毁窗口，destroyAllWindows()关闭所有窗口
  - imwrite函数保存图像，例如可以复制图像到指定的路径下

#### 第二章.图像处理基础
> 图像的基本表示方法

  - 二值图像 白色像素为1 黑色像素为0
  - 灰度图像 数值区间[0,255]，数值255表示纯白，数值0表示纯黑，其余数值在纯白和纯黑之间过渡
  - 彩色图像 分为RGB三个通道，分别代表红绿蓝三种颜色，（0,0,0）代表纯黑，（255,255,255）代表纯白
  - 一般情况下，通道顺序是RGB，但是在OpenCV中是BGR
> 像素处理

  - 图像可以理解为一个矩阵，在OpenCV for Python中，图像就是Numpy库中的一个数组
  - Numpy.zeros()函数生成全为零的数组
  ```
  for i in range(1000):
    img[0,i] = 255#纯黑的图片
    img[i,0] = 255
    img[i,i] = 255
    img[i,999-i] = 255#左上和左边都是一条白线，也有一条交叉的白线
    
  ```
  - 彩色图像读入OpenCV时依次读取BGR通道的像素值，并存储在ndarray的列中，以三维数组的形式存储
  - img[0,0,0]访问图像第0列第0行第0通道的像素值
  - img[0,0]访问第0行第0列的BGR值，即BGR通道的值之和
  ```
import numpy as np
import cv2

blue = np.zeros((300,300,3),dtype=np.uint8)#生成300X300，通道数为3的三通道二维数组
#print(np.shape(blue)) 结果为（300,300,3）
blue[:,:,0] = 255#将0通道即蓝色通道的值设为255，即纯蓝
# print("blue=\n",blue)
cv2.imshow("blue",blue)
green = np.zeros((300,300,3),dtype=np.uint8)
green[:,:,1] = 255
# print("green=\n",green)
cv2.imshow("green",green)
red = np.zeros((300,300,3),dtype=np.uint8)
red[:,:,2] = 255
print("red=\n",red)
cv2.imshow("red",red)
key = cv2.waitKey()
if key != -1:
    cv2.destroyAllWindows()
  ```
