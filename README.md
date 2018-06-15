### 2018.6.15.Fri.
demo过程中发现，发送语音和图片，ProgressBar不消失。

# ChatDemo

##主界面选择实现方式：

![image](https://github.com/Maxi-Mao/ChatDemo/blob/master/ChatIMG/main.jpg)

##文字表情示例图片：

![image](https://github.com/Maxi-Mao/ChatDemo/blob/master/ChatIMG/img1.png)

##图片发送示例图片：

![image](https://github.com/Maxi-Mao/ChatDemo/blob/master/ChatIMG/img2.png)

##语音发送示例动图：

![image](https://github.com/Maxi-Mao/ChatDemo/blob/master/ChatIMG/voice.gif)

##注：RecyclerView和ListView实现方式不同，些许功能不同，按需使用。

（按二者缓存方式的特性，建议类似聊天这种局部更新频繁的界面使用RecyclerView。）

 （RecyclerView现已完善，如有bug通知我再修复）
##16/11/7更新：

* 优化界面流畅度，主要优化GifTextView控件，和RecyclerView界面的流畅度，主要解决滑动时图片和文字表情的闪烁问题。

##16/10/15更新：

* 添加消息数据库，用于保存聊天记录。 数据库用的是GreenDao。数据分页加载。

因为是个Demo，所以ListView和RecyclerView用的同一个表，大家只需看实现方式即可。

##16/10/10更新：

* 添加ListView的实现方式：PullToRefreshListView

PullToRefreshRecyclerView为RecyclerView的实现方式，若想切换ListView则需对ChatActivity和PullToRefreshLayout等做修改和一些属性修改。

ListView适配器:ChatListViewAdapter

RecyclerView适配器:ChatRecyclerAdapter

##16/9/30更新：

* 界面由ListView改为RecyclerView

* 增加添加item动画

* 修复界面随键盘弹起问题，类似微信。

* 优化界面，提升用户体验

##介绍：
* 该项目是一个聊天界面，封装了包括文字、表情、图片和语音信息。
* 支持静态表情，gif表情，文字表情混排。图文混排实现参考：[Android聊天实现图文混编（包括gif显示）](http://blog.csdn.net/omrapollo/article/details/50586902)
* 支持图片发送，裁剪图片形状，支持图片点击进入大图观看，支持放大缩小等。
* 根据图片大小等比例缩放，并压缩显示。
* 支持语音发送，接收语音未读状态显示，语音录制为amr格式保存文件，语音发送仿微信。
* 语音播放工具可以参考另一个项目：[android语音播放工具（自带缓存）](http://blog.csdn.net/omrapollo/article/details/78085730)
* 若想录制mp3格式参考：[Android录制mp3格式](http://blog.csdn.net/omrapollo/article/details/50470659)
* 没有录音权限则提示用户。实现方式参考：[Android录音权限被禁解决方案](http://blog.csdn.net/omrapollo/article/details/51150280)
* 语音、图片支持三种状态：发送中、发送失败和发送成功（发送失败显示感叹号）。
* 支持下拉加载更多，下拉加载更多用了ViewDragHelper，实现方式参考：[Android下拉刷新](http://blog.csdn.net/omrapollo/article/details/49867345)
* 支持时间显示，默认大于一分钟显示一次，具体规则参见ChatAdapter类。可根据需求修改。

##详细说明

ListView:

![image](https://github.com/Maxi-Mao/ChatDemo/blob/master/ChatIMG/uml1.png)

RecyclerView:

![image](https://github.com/Maxi-Mao/ChatDemo/blob/master/ChatIMG/uml2.png)

###主要：
* ChatActivity:聊天界面
* ChatListViewAdapter:ListView聊天界面适配器
* ChatRecyclerAdapter:RecyclerView聊天界面适配器
* ChatBean:聊天数据对象

###其他
* ImageViewActivity:大图观看界面
* AudioRecordButton：自定义录音控件
* BubbleImageView：自定义图片裁剪控件
* MediaManager：语音播放控件
* GifTextView：自定义图文混排控件
* pulltorefresh包：自定义下拉加载更多控件（仅支持下拉加载更多）
* SlideInOutBottomItemAnimator:RecyclerView添加item动画（上滑）

图片加载使用Glide。（这个很好 2018.6.15.)

为了优化性能，滑动的过程中gif为静态显示。

文字发送按钮为键盘中的回车。

##后记：

该项目也是将之前做过的一些东西汇合了一下，时间比较短，大家就看一下具体的实现方式吧，可能有点乱，有时间的话我整理一下。

## License

    Copyright 2016 maojiqing

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.