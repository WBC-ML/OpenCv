# OpenCv
学习OpenCv的笔记以及代码

< 第一章.显示图像

  - namedWindow函数创建指定名称的窗口，一般不用
  - imshow函数显示图像，直接imshow(窗口名称，图)创建窗口顺带显示图像
  - waitkey函数等待按键，相当于switch case
  - destroyWindow函数销毁窗口，destroyAllWindows()关闭所有窗口
  - imwrite函数保存图像，例如可以复制图像到指定的路径下

< 第二章.图像处理基础

  - 二值图像 白色像素为1 黑色像素为0
  - 灰度图像 数值区间[0,255]，数值255表示纯白，数值0表示纯黑，其余数值在纯白和纯黑之间过渡
  - 彩色图像 分为RGB三个通道，分别代表红绿蓝三种颜色，（0,0,0）代表纯黑，（255,255,255）代表纯白
