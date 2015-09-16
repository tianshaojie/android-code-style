# Android-Code-Style

## 约定

* **Activity.onCreate()，Fragment.onActivityCreated()，作为程序入口，不用写入太多代码，尽量保持只调用initXXX()方法，简单明了展示调用过程。如：initData()，initView()。**
* **单个方法体不要过长**
* **代码任何地方不要拼错单词**
* **杜绝整个类代码格式化**
* 调用方法保持“临近原则”，被调用的方法，放在调用方法下方
* 统一调整IDE的Tab缩进为4个空格
* 空行的使用，拒绝拖沓无分割，关联代码段放一块并与后面代码分割
* 用好TODO标记
	* 记录想法，记录功能点，开发过程中可以利用TODO记录一下临时想法或为了不打扰思路留下待完善的说明
	* 删除无用TODO，开发工具自动生成的TODO，或则已经完善的TODO，一定要删除。
* 处理“魔数”等看不懂的神秘数字
	* 代码中不要出现数字，特别是一些标识不同类型的数字。
	* 所有意义数字全部抽取到Constant公共类中，避免散布在各位类中。

	
## 命名

### 1. 布局文件中的id命名

**规则：使用驼峰命名，前缀+逻辑名称，类变量名和布局文件id名称保持一致，不需要下划线分割**

**控件前缀规则：**

* TextView/EditText: text
* Button/RadioButton/ImageButton: btn
* ImageView: img
* RelativeLayout/LinearLayout/FrameLayout: layout，
* ListView: listView
* WebView: webView
* CheckBox: chBox


* 如：TextView @+id/textTitle
* 如：EditView @+id/textName
* 如：Button @+id/btnSearch


### 2. 布局文件命名

**规则：** 使用**前缀_逻辑名称**命名，单词全部小写，单词间以 下划线 分割。

**前缀规则：**

* Activity对应的布局使用activity_
* Fragment对应的布局使用fragment_

* 如：PublishActivity: activity_publish.xml


### 3. 资源文件命名

**规则：** 使用 **前缀_用途** 命名，单词全部小写，单词间以 下划线 分割。

* drawable：
	* btn_back_selector.xml		控件前缀命名
	* common_circle_gray.xml	通用资源多处使用common_
	* chat_image_selector.xml	功能相关业务使用加用途前缀
	
* drawable_hdpi：
	* btn_back_normal.9.png		控件前缀名称
	* btn_back_press.9.png		控件前缀名称
	* icon_login_lock.png		icon_+用途
	
* values/color：
	* pull_refresh_attrs.xml	引入的第三方资源，携带资源简拼的前缀

### 4. 类和接口命名 

**规则：** 使用驼峰规则，首字母必须大写，使用名词或名词词组。要求简单易懂，富于描述，不允许出现无意义或错误单词。

* 如：class BookMarkAdd 正确  
* 如：class AddBookReadPlan 错误！ 应为 class BookReadPlanAdd 

### 5. 方法的命名

**规则：** 使用驼峰规则，首字母必须小写，使用动词。要求简单易懂，富于描述，不允许出现无意义或错误单词。

* 如：public void run(); 
* 如：public String getBookName(); 

### 6. 变量命名

**规则：** 使用驼峰规则，首字母必须小写，使用名词或名词词组。要求简单易懂，富于描述，不允许出现无意义或错误单词。

* 成员变量命名，不要在私有变量前添加m字样
* 常量命名，全部大写，单词间用下划线隔开



## 其他

* 空行：空行将逻辑相关代码段隔开，简洁清楚，提高可读性
	* 成员变量之间，根据业务形成分组加空行
	* 方法之间加空行
* 控制语句
	* 减少条件嵌套，不要超过3层
	* if判断使用“卫语句”，减少层级	
	`
	if(obj != null) {
		doSomething();
	}	
	`	
	修改为：	
	`
	if(obj == null) {
		return;
	}
	doSomething();	`
	* if语句必须用{}包括起来,即便是只有一句
* 方法
	* 拆分臃肿方法，每个方法只作一件事
	* 做同一个逻辑的方法，尽量靠近放到一块，方便查看
	* 不要使用 try catch 处理业务逻辑
	* 使用JSON工具类，不要手动解析和拼装数据
* Activity继承BaseFragmentActivity或SwipeBackActivity，可以使用ButterKnife注解代替findViewById。


## IDE

* Android Studio (越早使用越好)
* Android SDK 4.4W （API 20 统一开发版本）
* JDK 1.8（统一开发版本）


## Libraries

** Base **

* fastjson-android-1.2.4.jar
* okhttp-2.2.0.jar
* okio-1.2.0.jar
* picasso-2.5.0.jar
* butterknife:7.0.1
* ormlite-android:4.48

** UI **

* PullToRefresh
* QuickAdapter
* PagerSlidingTabStrip
* SystemBarTint		状态栏以及导航栏设置背景颜色
* SwipeBackLayout 	左滑返回
* PullToZoomView	可以下拉缩放HeaderView
* AutoLoopViewPager 轮播图
* PhotoView
* ViewPageIndicator

## View project on GitHub

* [https://github.com/tianshaojie/android-code-style](https://github.com/tianshaojie/android-code-style)


