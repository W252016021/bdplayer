
**百度播放器**   [![](https://www.jitpack.io/v/W252016021/bdplayer.svg)](https://www.jitpack.io/#W252016021/bdplayer)
-
**基于百度视频sdk封装的播放器类库**
```java
全功能版支持全媒体格式
支持滑动快进和音量声音滑动调节
支持倍速播放<0.8x-2.0x>
支持锁屏播放
支持横竖屏切换
支持裁剪方式切换
```
##### 目前所知问题:
```java
.WMV文件无法快进
```
##### 引用方式1:

```java
allprojects {
 repositories {
   ...
      maven { url 'https://www.jitpack.io' }
   }
 }
```

```java
 dependencies {
	        implementation 'com.github.W252016021:bdplayer:v1.2'
	}
```
##### 引用方式2：
```java
如果导入过慢直接通过下方地址下载*bdplayer.aar*文件导入项目即可
```
###### 下载地址: [bdplayer.aar](https://www.lanzous.com/b521906/"bdplayer.aar")
##### 播放方式：

```java
// VideoInfo.clearBdHestory(this);  //清除记忆播放记录
VideoInfo info = new VideoInfo();
info.setAK("**************************");//你在百度申请到的access key,无效ak可能导致无法播放
info.setUrl("http://192.168.1.103/crzdy.mp4");
info.setTitle("毒液BD中英双字");
info.setOpenHestoryPlay(true);//是否开启记忆播放
info.setDecodeModel(info.DECODE_SW);//设置解码模式，可以设置为 DECODE_AUTO(优先硬解，其次软解) 或者 DECODE_SW(软解)，默认为DECODE_AUTO;
info.setScaleModel(info.VIDEO_SCALING_MODE_SCALE_TO_FIT);
// VIDEO_SCALING_MODE_SCALE_TO_FIT 填充，遵守宽高比，有黑边
// VIDEO_SCALING_MODE_SCALE_TO_FIT_WITH_CROPPING 裁剪，遵守宽高比，无黑边，但视频边缘可能被裁剪
// VIDEO_SCALING_MODE_SCALE_TO_MATCH_PARENT 铺满，不遵守宽高比，直接铺满显示区域
info.setLogEnabled(true);//开启日志输出
startActivity(new Intent(this, VideoPlayerActivity.class).putExtra("VideoInfo", info));
```
##### 百度access key申请地址：
[百度access key申请](https://console.bce.baidu.com/iam/#/iam/accesslist "百度access key申请")

##### 防混淆设置
将以下语句加入到您的proguard混淆配置文件中，

```java
-libraryjars libs/bdplayer.jar
-keep class com.baidu.cloud.media.**{ *;}
```
[![演示图片](https://raw.githubusercontent.com/W252016021/bdplayer/master/%E6%BC%94%E7%A4%BA%E5%9B%BE%E7%89%87.png "演示图片")](https://raw.githubusercontent.com/W252016021/bdplayer/master/%E6%BC%94%E7%A4%BA%E5%9B%BE%E7%89%87.png "演示图片")
```java
###### by QQ252016021            date:2018.12.13
```
