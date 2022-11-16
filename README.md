# TV-webview
电视app应用，全屏展示网页，内嵌x5浏览器，动态设置网址。

#### 项目初衷
公司或企业电视上经常需要显示一些网址，如系统监控图表、企业经营大屏等。
这些图表常为网页做的，
1. 直接在电视的浏览器里面输入很不方便。 
2. 浏览器里不易全屏，显示效果不好。
3. 电视默认浏览器对html的新特性支持不够好。 

出于以上原因，我们要做一个安卓app，安装在电视上展示企业图表。 

#### 功能介绍 
1. app内嵌x5内核浏览器，支持很多新特性，可播放视频,websocket等。 
2. 可动态设置 app访问的网址、userAgent。
3. 集成jsBridge 和TTS语音合成服务, 可调用speakVoice 来播放声音
4. 为方便遥控器操作， 双击返回键 时可选择设置参数。
5. 集成NanoHTTPD web服务，方便在网页中设置参数。
6. 支持安卓电视、平板、手机。

#### 案例说明
一个弹幕网页，需要实时的接收多人发来的信息，弹幕形式显示在网页中，并把文字转为语音播放出来。 
	- ![image](https://github.com/nocb/TV-webview/blob/main/doc/danmu.png?raw=true)
	实时接收消息，可以用goeasy 的服务，
	网页接收到消息后，调用MyJavaScriptInterface 中的speakVoice 方法，发出语音。
	比如：顾客刷卡进入场馆后，电视屏幕上立刻显示顾客年卡信息，并语音“欢迎 韩先生入场”。 
	再比如：医院的排队叫号屏幕， 需要通知患者就医，医生可点击下一位，电视屏上自动语音通知，并显示相关信息。
	
#### 系统组件
1. X5WebView   https://x5.tencent.com/
2. nanohttpd安卓端http服务 https://github.com/NanoHttpd/nanohttpd
3. volley  网络请求服务  

#### 使用说明
app默认打开是 https://www.baidu.com ，设置成你需要的网址。
双击返回键，进入设置服务， 在浏览器中输入 网址，设置url ，提交后重新开启应用 。 
- ![image](https://github.com/nocb/TV-webview/blob/main/doc/11.png?raw=true)
- ![image](https://github.com/nocb/TV-webview/blob/main/doc/22.png?raw=true)
- ![image](https://github.com/nocb/TV-webview/blob/main/doc/setting.png?raw=true)

#### 问题
1. x5 内核加载不成功 
可以先加载 https://debugtbs.qq.com/   然后调试， 可手动“安装线上内核”   
具体可参考： X5内核加载问题自查手册.pdf 


