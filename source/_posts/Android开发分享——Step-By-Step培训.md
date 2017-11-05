title: Android开发分享——Step By Step培训
date: 2015-10-28 17:17:25
tags:
---
### Android简介
* Android发展历程
	Android系统仅仅推出两年就超过了已经霸占市场逾十年的诺基亚Symbian,目前已经成为全球应用最广泛的手机操作系统
	* 2003年10月，Andy Rubin等人一起创办Android公司
	* 2005年8月，Google收购Android,并让Andy Rubin继续负责Andorid项目
	* 2007年11月，Google宣布组建开放手机联盟(Open Handset Alliance)，34家终端和运营企业加入，共同开发名为安卓(Android）的开放源代码的移动系统。
		Google、中国移动、T-Mobile、三星、高通、德州仪器等领军企业通过开放手机联盟携手开发Android。
		开放手机联盟旨在开发多种技术，大幅削减移动设备和服务的开发和推广成本。
	* 2008年推出Android系统的第一个版本，Google，T-mobile、HTC联合促成了世界上第一款基于开源Android手机T-mobile G1的诞生。
		![T-Mobile G1](http://7xnve9.com1.z0.glb.clouddn.com/T-Mobile%20%20G1_1.jpg)
		![T-Mobile G1](http://7xnve9.com1.z0.glb.clouddn.com/T-Mobile%20%20G1_2.jpg)
	* 2009年推出Android 1.5，提供了非常豪华的用户界面和蓝牙连接支持，吸引了大量开发者
	* ...
* Android推出的版本

版本号|名称|API Level
---|---|---
1.0 | N/A | 1
1.1 | N/A | 2
1.5 | Cupcake(纸杯蛋糕) | 3,NDK 1
1.6 | Donut(甜甜圈) | 4,NDK 2
2.0|Eclair(松饼)|5
2.0.1|Eclair|6
2.1|Eclair|7,NDK 3
2.2.x|Froyo(冻酸奶)|8,NDK 4
2.3-2.3.2|Gingerbread(姜饼)|9,NDK 5
2.3.3-2.3.7|Gingerbread|10
3.0|Honeycomb(蜂巢)|11
3.1|Honeycomb|12,NDK 6
3.2.x|Honeycomb|13
4.0.1-4.0.2|Ice Cream Sandwich(冰淇淋三明治)|14,NDK 7
4.0.3-4.0.4|Ice Cream Sandwich|15,NDK 8
4.1.x|Jelly Bean(果冻豆)|16
4.2.x|Jelly Bean|17
4.3.x|Jelly Bean|18
4.4-4.4.4|KitKat(奇巧巧克力)|19
4.4W|KitKat|20
5.0|Lollipop(棒棒糖)|21
5.1|Lollipop|22
6.0|Marshmallow(棉花糖)|23
* 移动市场占有率
	* 友盟统计
		![友盟统计](http://7xnve9.com1.z0.glb.clouddn.com/友盟统计.png)
	* Android Studio
		![Studio数据](http://7xnve9.com1.z0.glb.clouddn.com/各版本市场占有率.png)
* Android与Java
	* Android应用程序是用Java语言写成的，使用JDK的javac(或等效工具，例如ECJ)来编译。
		这个过程产生标准的Java字节码（.class文件）,这些文件再转化成Android的.dex文件，
		从使用的角度来看，它就是一种不同格式的Java class文件。
	* 使用Dalvik VM替代JVM,相较于 Java 虚拟机，Dalvik是专门为移动设备定制的。
		它针对手机内存、CPU性能有限等情况做了优化处理。
	* Android使用了一部分javase标准API，Android使用了一个相当大的JavaSE APIs子集。
		甚至可以将Android改名为Java GE（Java Google Edition）
		如果你懂得Java编程(深入到高级的，底层的细节)，你也就懂得Android编程，你只需要学一些新的API和框架概念，他们是对等的系统。
* Android平台架构及特性
	经典平台架构图
    ![平台架构图](http://7xnve9.com1.z0.glb.clouddn.com/Android平台架构.JPG)
	* 1.Linux内核层
		Android系统是基于Linux 2.6内核的，这一层为Android设备的各种硬件提供了底层的驱动，如显示驱动、音频驱动、照相机驱动、蓝牙驱动、Wi-Fi 驱动、电源管理等。
	* 2.系统运行库层
		* C/C++库来为Android提供主要的特性支持
			* SQLite库提供数据库支持
			* OpenGL|ES库提供3D支持
			* Webkit提供浏览器内核支持
			* ...
		* Android Runtime
			* Core Libraries
				提供核心库，能够允许开发者使用Java语言来编写Android应用程序
			* Dalvik VM
				让每一个Android应用程序都能运行在独立的进程当中，并且拥有一个自己的Dalvik虚拟机实例
	* 3.应用框架层
		提供了构建应用程序时可能用到的各种API
	* 4.应用层
		所有安装在手机上的应用程序

### 开发环境搭建
* 开发IDE及环境搭建
	* Eclipse
		* JDK
		* Eclipse
		* ADT
		* Android SDK
	* ADT-Bundle
		* JDK
		* Android SDK
	* Android Studio
		* JDK
		* Android SDK
		* Android Studio
* HelloWorld及项目目录结构分析
	* Eclipse项目目录
		![Eclipse项目目录](http://7xnve9.com1.z0.glb.clouddn.com/Eclipse目录.png)
	* Android Studio项目目录
		![Studio项目目录](http://7xnve9.com1.z0.glb.clouddn.com/AS项目目录.png)
	* Log打印输出
		Log.i(tag,msg);

### Android基础
* AndroidManifest.xml
	* uses-permission
	* Application
	* Activity
		```xml
		<?xml version="1.0" encoding="utf-8"?>
		<!--设置命名空间，项目包名-->
		<manifest xmlns:android="http://schemas.android.com/apk/res/android"
			package="com.ecode.basicdemo" >
			<!-- 应用权限-->
			<uses-permission android:name="android.permission.INTERNET"/>
			<!-- 应用设置-->
			<!-- allowBackup="true" 容许任何一个能够打开USB 调试开关的人从Android手机中复制应用数据到外设-->
			<!-- icon 设置应用图标-->
			<!-- label 设置应用标签，即应用图标下显示的名称-->
			<!-- theme 应用主题-->
			<application
				android:allowBackup="true"
				android:icon="@mipmap/ic_launcher"
				android:label="@string/app_name"
				android:theme="@style/AppTheme" >
				<!-- activity 名称设置为：包名+Acivity相对路径-->
				<activity android:name=".MainActivity" >
					<!-- 意图过滤器，MAIN和LAUNCHER设置表示该Activity是应用的入口-->
					<intent-filter>
						<action android:name="android.intent.action.MAIN" />

						<category android:name="android.intent.category.LAUNCHER" />
					</intent-filter>
				</activity>
			</application>
		</manifest>
		```
* Activity
	* 初始化Activity
		经典Activity生命周期调用图
        ![Activity生命周期](http://7xnve9.com1.z0.glb.clouddn.com/Activity生命周期.png)
		* onCreate
		* onStart
		* onResume
		* onPause
		* onStop
		* onDestory
		* onRestart
	* 设置布局文件
		`setContentView(R.layout.main_activity);`
	* AndroidManifest.xml中注册
	* 启动与结束
		* startActivity
			* Intent显示启动
			* IntentFilter隐式启动
		* startActivityForResult
		* finish();
	* onClick事件处理
	* Bundle数据传递
	* 主题设置及横竖屏
* 用户界面UI
	* 常用的系统控件
		* TextView、EditText、Button、ImageView
		* Toast、AlterDialog
		* CheckBox、RadioGroup、RadioButton
		* AlertDialog、ProgressDialog
		* ListView、GridView
	* 五大布局
		* LinearLayout线性布局
			```xml
			<LinearLayout
				android:layout_width="match_parent"
				android:layout_height="match_parent"
				android:orientation="vertical">

				<TextView
					android:layout_width="wrap_content"
					android:layout_height="wrap_content"
					android:text="Hello World!"/>

				<TextView
					android:layout_width="wrap_content"
					android:layout_height="wrap_content"
					android:text="Hello World!"/>

				<TextView
					android:layout_width="wrap_content"
					android:layout_height="wrap_content"
					android:text="Hello World!"/>
			</LinearLayout>
			```
		* RelativeLayout相对布局
			```xml
			<RelativeLayout
				android:layout_width="match_parent"
				android:layout_height="match_parent">
				<TextView
					android:id="@+id/t1"
					android:layout_width="wrap_content"
					android:layout_height="wrap_content"
					android:text="T1 Hello World!"/>
				<TextView
					android:id="@+id/t2"
					android:layout_below="@id/t1"
					android:layout_width="wrap_content"
					android:layout_height="wrap_content"
					android:text="T2 Hello World!"/>
				<TextView
					android:id="@+id/t3"
					android:layout_toRightOf="@id/t1"
					android:layout_width="wrap_content"
					android:layout_height="wrap_content"
					android:text="T3 Hello World!"/>
			</RelativeLayout>
            ```
		* TableLayout表格布局
			```xml
			<TableLayout
				android:layout_width="match_parent"
				android:layout_height="match_parent">
				<TableRow>
					<TextView
						android:layout_width="wrap_content"
						android:layout_height="wrap_content"
						android:text="T1 Hello World!"/>
					<TextView
						android:layout_width="wrap_content"
						android:layout_height="wrap_content"
						android:text="T2 Hello World!"/>
				</TableRow>
				<TableRow>
					<TextView
						android:layout_width="wrap_content"
						android:layout_height="wrap_content"
						android:text="T1 Hello World!"/>
					<TextView
						android:layout_width="wrap_content"
						android:layout_height="wrap_content"
						android:text="T2 Hello World!"/>
				</TableRow>
			</TableLayout>
            ```
		* AbsoluteLayout绝对布局
			```xml
			<AbsoluteLayout
				android:layout_width="match_parent"
				android:layout_height="match_parent"
				android:orientation="vertical">
				<Button
					android:layout_width="wrap_content"
					android:layout_height="wrap_content"
					android:layout_x="0px"
					android:layout_y="0px"
					android:text="按钮1"/>
				<Button
					android:layout_width="wrap_content"
					android:layout_height="wrap_content"
					android:layout_x="20px"
					android:layout_y="20px"
					android:text="按钮2"/>
				<Button
					android:layout_width="wrap_content"
					android:layout_height="wrap_content"
					android:layout_x="40px"
					android:layout_y="40px"
					android:text="按钮3"/>
				<Button
					android:layout_width="wrap_content"
					android:layout_height="wrap_content"
					android:layout_x="60px"
					android:layout_y="60px"
					android:text="按钮4"/>
			</AbsoluteLayout>
            ```
		* FrameLayout帧布局
			所有放在布局里的控件，都按照层次堆叠在屏幕的左上角
            ```xml
			 <FrameLayout
					android:layout_width="fill_parent"
					android:layout_height="fill_parent">
					<TextView
						android:layout_width="fill_parent"
						android:layout_height="wrap_content"
						android:textSize="50sp"
						android:textColor="#000000"
						android:text="第一层"/>
					<TextView
						android:layout_width="fill_parent"
						android:layout_height="wrap_content"
						android:textSize="40sp"
						android:textColor="#ffff00"
						android:text="第二层"/>
					<TextView
						android:layout_width="fill_parent"
						android:layout_height="wrap_content"
						android:textSize="20sp"
						android:textColor="#00ffff"
						android:text="第三层"/>
			 </FrameLayout>
             ```

* 数据存储
	* Shareperference
		会在shared_prefs目录下生成xml
        ```java
		SharedPreferences sp=getSharedPreferences("settings",MODE_PRIVATE);
        SharedPreferences.Editor editor=sp.edit();
        editor.putInt("a",10);
        editor.commit();
		int a=sp.getInt("a",0);
        ```
	* 文件存储
		* 手机内存
			files目录下生成文件
			* 写文件
				```java
				FileOutputStream fos=openFileOutput("f.txt", MODE_PRIVATE);
				fos.write("aaa".getBytes());
				fos.close();
                ```
			* 读文件
				```java
				FileInputStream inStream=this.openFileInput("f.txt");
				ByteArrayOutputStream stream=new ByteArrayOutputStream();
				byte[] buffer=new byte[1024];
				int length=-1;
				while((length=inStream.read(buffer))!=-1)   {
					stream.write(buffer,0,length);
				}
				stream.close();
				inStream.close();
				Toast.makeText(MainActivity.this,stream.toString(), Toast.LENGTH_LONG).show();
                ```
		* SD卡存储
			* SD卡权限设置
                ```xml
                <!-- 在SDCard中创建与删除文件权限 -->
                <uses-permission android:name="android.permission.MOUNT_UNMOUNT_FILESYSTEMS"/>
                <!-- 往SDCard写入数据权限 -->
                <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>
                ```
            * 获取SD卡路径
                ```java
                if (Environment.getExternalStorageState().equals(Environment.MEDIA_MOUNTED)){
                    File dir=Environment.getExternalStorageDirectory();
                    for (File fileName : dir.listFiles()){
                        Log.e("fileName", fileName.getName()+"------");
                    }
                }
                ```
	* SQLite数据库
	* ContentProvider
	* 网络存储
* Service
* BraodcastReciever
	* 无序广播
	* 有序广播
* 线程与handler消息机制
* AsyncTask
* HttpURLConnection和HTTPClient
* 多媒体MP3与视频播放
* Android动画
	* FrameAnimation帧动画
	* TweenAnimation补间动画
	* PropertyAnimation属性动画
	