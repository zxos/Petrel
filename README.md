
## 项目介绍

海燕（petrel）是360推出的首家免费短视频开源项目，涵盖了iOS、Android等平台。为开发者提供短视频拍摄、剪辑等全套解决方案。

剪辑SDK定位以市场为导向,助推短视频行业发展，为开发者提供编辑、特效、预览播放、合成全流程解决方案，开发者可以根据自己的创意创建App，实现各种特色功能。

## 系统版本及编译环境

**支持的系统：**

* iOS 8.0及以上
* Android 4.4及以上

**Android 编译环境：**

* NDK r10e 及以上
* Android Studio 2.1.3 及以上
* Gradle 2.14.1 及以上

## 输入/输出规范

**输入规范：**

* 视频格式：MP4、MOV、WMV、M2V、MPG
* 音频格式：MP3、FLAC、AAC、M4A
* 图片格式：JPG、PNG、HEIC
* 视频编码：H264、H265、WMV、MPEG4
* 音频编码：MP3、AAC、PCM、FLAC

**输出规范：**

* 视频格式：MP4
* 视频编码：H264
* 音频编码：AAC

**第三方库：**

* ffmpege 3.4 及以上

## 产品特点

**支持多轨道、多段编辑**

* 支持同时导入不同格式的视频、图片，进行多段混剪
* 支持多轨道，能够满足画中画、分屏、配音等多种玩法

**支持多种输入、输出样式**

支持多种格式、多种分辨率的输入素材，素材既可以是本地的也可以是云端url地址，同时开发者可以根据需求自定义输出分辨率。

**所见即所得**

通过预览播放器可以在制作过程中实时预览制作效果，大大提高了制作体验，节省了制作成本和时间

**丰富的基础编辑功能**

剪辑SDK包含丰富的基础编辑功能，开发者可以根据自己的需求灵活组合使用。

**支持自定义特效**

特效完全插件化，开发者还可以根据需要扩展自定义特效。

## 核心功能列表及说明


| 功能 | 说明 |
| --- | --- |
| 多段素材拼接、文件剪切 | 将多段视频素材拼接一个文件，并且支持剪切头部尾部冗余的视频，或者文件片段 |
| 画面裁剪、旋转、缩放、水平/垂直镜像 | 对视频画面进行裁剪，旋转角度，扩大缩小，镜像等操作，达到最佳视觉体验 |
| 缩略图 | 实时获取文件缩略图，精确到帧画面，方便剪辑预览 |
| 音视频分离 | 分离音视频，获取单独的音频或者视频与其他素材进行叠加 |
| 画中画 | 叠加不同的视频素材，实现画中画的效果，例如分屏、9宫格画面 |
| 转场 | 相邻文件衔接处添加转场效果，起到平滑过渡的作用，为客户提供20余种效果进行选择。 |
| 倍速 | 无级慢速、快速调节，支持1/8-8b倍速 |
| 调节音量、声音添加缓入缓出效果 | 针对音频文件调节音量，声音支持缓入缓出循循渐进的效果，波浪状的音轨。 |
| 变声 | 调节音调，实现不同的声音效果，例如男生变女生。 |
| 添加字幕、贴纸、水印 | 添加字幕、贴纸、水印丰富视频内容 |
| 添加滤镜 | 添加不同滤镜效果，快速替换风格，目前提供17种滤镜效果，同时支持自定义 |
| 实时背景音乐 | 添加背景音乐与原音进行混合 |
| 马赛克 | 针对原视频打马赛克，例如遮盖品牌及广告logo |


## 模块结构

剪辑SDK主要分为几个模块，分别为：时间线、特效、预览播放器、合成器。

* 时间线（Timeline）:

时间线是所有剪辑事件按照时间先后顺序排列的集合，也是所有剪辑事件在时间上的体现。时间线的长短和最终合成输出的文件时间一一对应，时间线时长即代表最终合成输出文件的时长。

时间线上可以添加音/视频轨道(Track)，轨道是文件素材（TrackClip）的载体，也就是文件列表。视频轨道上可以添加视频、图片文件；音频轨道上能添加音频、视频文件，音频轨道上添加视频文件时只会处理音频部分。同一轨道上的文件间不能重叠，否则后添加的文件无法添加成功。

* 特效(Effect)：

特效是特效的载体，可以针对素材片段、轨道或者时间线添加、获取、删除，特效分为音、视频特效。

* 预览播放器（Player）：

预览播放器和传统播放器相比，具备实时预览效果，所有添加的特效都可以通过预览播放器实时渲染。预览过程中，特效并没有真正添加进素材文件内。

* 合成器（Producer）：

合成器会读取素材文件，并按特效指令处理素材文件，最终按照配置合成新的媒体文件。

**项目结构图**

![](doc/Resource/框架图.png)

## 使用流程

实现视频编辑的一般步骤：
1.	 创建时间线
2. 添加轨道
3. 添加文件片段
4. 添加特效指令
5. 添加实时预览
6. 合成媒体文件
其中，4、5顺序可颠倒，实时预览、合成器均可单独使用。

![](doc/Resource/流程图.png)

## 与我们联系

欢迎您与我们联系，QQ群：857572993
![](doc/Resource/QQ.jpg)

## License
Petrel is [Apache v2.0 licensed](./LICENSE).

