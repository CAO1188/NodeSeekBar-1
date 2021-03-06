# NodeSeekBar
节点托动条

这是一个有节点的SeekBar，其节点平均分布在SeekBar上。
其实现原理是自定义View，然后复写onDraw在合适地方画圆。
现在可以设置NodeSeekBar的方向，圆的大小、颜色，线段颜色等，当然也能设置节点的数量。

使用方法：

1、在布局文件中添加NodeSeekBar
```xml
<com.mouse.cookie.nodeseekbar.NodeSeekBar
        android:id="@+id/nsb_mainactivity"
        android:layout_width="wrap_content"
        android:layout_height="400dp"
        app:nodeNumber="6"
        app:progress="2"
        app:cycleRadius="20"
        app:orientation="vertical"
        app:cycleBackgroundColorBefore="#bbbbbb"
        app:cycleBackgroundColorAfter="#00ffff"
        android:layout_alignParentTop="true"
        android:layout_centerHorizontal="true"/>
```
设置节点数`nodeNumber`=int，当前进度`progress`=int，节点圆半径`cycleRadius`=int; <br>
节点圆两种颜色`cycleBackgroundColorBefore`=color、`cycleBackgroundColorAfter`=color; <br>
方向`orientation`=(vertical、horizontal)。 <br>

2、在java代码中设置进度变化事件监听器
```java
mNodeSeekBar.setOnProgressChangedListener(new NodeSeekBar.OnProgressChangedListener() {
            @Override
            public void onProgressChanged(int i) {
                Log.i("Tag_MainActivity", "进度为：" + i);
            }
        });
```
3、获取当前进度
```java
mNodeSeekBar.getProgress();
```
效果：<br>
![image](https://github.com/cookiemouse/NodeSeekBar/blob/master/image/image_1.png)
![image](https://github.com/cookiemouse/NodeSeekBar/blob/master/image/image_2.png)

4、更新
2016.04.01
增加可在节点处添加文字的功能

使用方法
```java
mNodeSeekBar.setString(List<String>);
```
竖型NodeSeekBar是以从下到上的顺序添加文字，横型NodeSeekBar是以从左到右的顺序添加文字。
