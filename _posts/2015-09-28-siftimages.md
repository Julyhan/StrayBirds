---
layout: post
title: siftimages
category: coding
comments: true
---

最近需要利用opencv写一个sift的代码，恰巧发现[github](https://github.com/sagunms/ComputerVisionProjects/blob/master/2%20-%20siftImages/siftImages/siftImages.cpp)上已经有一个写得很好的代码。于是从自己写变为修改，练自己注释和之前STL学的一些东西。

没想到这个过程中，却收获很大。两个多小时把写的部分见[此](https://github.com/Julyhan/Personnal/blob/master/vision/siftImages.cpp)。现把收获点总结如下：

### visual studio

* visual studio 的project properties配置

opencv每次配置都很麻烦，对于不变的环境，基本可以使用配置表一劳永逸。参考此篇[博客](http://blog.csdn.net/bendanban/article/details/28661763)。

* opencv debug vs release

切记，debug模式下，用debug的lib和dll，反之亦然，否则容易引起imread读不入图像等问题。今年暑假比赛的程序估计就和库文件的配置有点关系，不过当时全部使用C版接口，即图像指针读图了，汗。

* visual studio 接受argv输入

不多说，工具型问题，直接上[链接](http://blog.csdn.net/qq1987924/article/details/22781331)。

不想看链接，几步搞定：项目|属性|配置属性|调试 ==>>命令参数

### opencv

* 色彩空间转换```cvtColor```

```cvtColor(Mat src, Mat imgYUV, CV_BGR2YCrCb);```

* 分割图像通道```split``` 

```split(Mat imgYUV, vector<Mat> imgYUVset);```

* 合并图像通道```merge``` 

```merge( vector<Mat> imgYUVset, Mat img_yyy);```

* 图形操作

```line(Mat img, Point2f begin_point, Point2f  end_point, Scalar color);```
```circle(Mat img, Point key_points[i].pt, float key_points[i].size * .5, Scalar color);```

* 复制指定区域图像

```img_resize.copyTo(img_merge(Rect(0, 0, img_resize.cols, img_resize.rows)));```

* 显示图像
```
namedWindow("Single Image", CV_WINDOW_AUTOSIZE);
imshow("Single Image", img_merge);
waitKey();
```


