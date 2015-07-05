# Android-Code-Style


## IDE

* IntelliJ IDEA
* Android SDK 4.4W （API 20）
* JDK 1.8


## Jars

** Base **

* fastjson-android-1.2.4.jar
* okhttp-2.2.0.jar
* okio-1.2.0.jar
* picasso-2.5.0.jar
* androidannotations-api-3.2.jar

** UI **

* PullToRefresh
* QuickAdapter
* PagerSlidingTabStrip


## 命名


###  1. 类和接口命名 

**规则：** 使用 名词或名词词组 命名。类名必须使用驼峰规则，即首字母必须大写，如果为词组，则每个单词的首字母也必须要大写。要求类名简单，不允许出现无意义的单词（如 class XXXActivity）。 

* 如：class BookMarkAdd 正确  
* 如：class AddBookReadPlan 错误！ 应为 class BookReadPlanAdd 

### 2. 方法的命名

**规则：** 方法名是一个动词，使用驼峰规则，第一个单词的首字母小写，其后单词的首字母大写。
**注意：** 减少单词简拼，要做到见词识意，坚决抵制单词拼错。

* 如：public void run(); 
* 如：public String getBookName(); 

### 3. 变量命名

**规则：** 变使用驼峰规则，但是首字母必须小写，变量名尽可能的使用名词或名词词组。同样要求简单易懂，富于描述，不允许出现无意义的单词。

* 成员变量命名，不要在私有变量前添加m字样
* 常量命名，全部大写，单词间用下划线隔开


### 4. 布局文件命名

**规则：** Activity对应的布局，使用 **模块名(包名)_类名称**命名。全部单词小写，单词间以下划线分割，并且使用名词或名词词组。类名称单词拆开后使用下划线连接。

* 如：PublishActivity: circle_publish.xml


### 5. 布局文件中的id命名

~~**规则：** 使用 **前缀_逻辑名称** 命名。使用驼峰规则，单词间以下划线分割，并且使用名词或名词词组。~~  `注：引入入androidannotations后，全部统一使用驼峰命名`

**规则：** 使用 **前缀+逻辑名称** 命名。全部单词小写，单词间以下划线分割，并且使用名词或名词词组。

**控件前缀规则：**

```
* TextView/EditText: ~~ text ~~ 请使用实际意义的名称，前缀多余，如name, title, passowrd
* Button/RadioButton/ImageButton: btn
* ImageView: ~~ img ~~ 请使用实际意义的名称，前缀多余，如logo，productImg
* RelativeLayout/LinearLayout: layout
* ListView：listView
* WebView: webView
```

* 如：TextView @+id/name
* 如：Button @+id/btnSearch


### 6. 资源文件命名

**规则：** 使用 **模块名_用途** 来命名。layout中所使用的所有资源（如drawable,style等）命名必须以全部单词小写，单词间以下划线分割，并且尽可能的使用名词或名词组，如果为公共资源，如分割线等，则直接用用途来命名  

* 如：circle_search_icon_selector.xml 
* 如：某分割线，line.png  或 separator.png

## 约定

1. 缩进：统一调整IDE的Tab缩进为4空格
2. 空行：空行将逻辑相关代码段隔开，简洁清楚，提高可读性
	* 每个成员变量之间不需要空行，根据业务形成分组，然后加空行
	* 两个方法之间支架一行空行
	* 如：定义的intent变量为一组，下面加空行
	* 如：控件变量为一组，下面加空行
3. 用好TODO
	* 记录想法，记录功能点，开发过程中可以利用TODO记录一下临时想法或为了不打扰思路留下待完善的说明
	* 删除无用TODO，开发工具自动生成的TODO，或则已经完善的TODO，一定要删除。
4. 处理“魔数”等看不懂的神秘数字
	* 代码中不要出现数字，特别是一些标识不同类型的数字。
	* 所有意义数字全部抽取到Constant公共类中，避免散布在各位类中。
5. 控制语句
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
6. 方法
	* 拆分臃肿方法，每个方法只作一件事
	* 做同一个逻辑的方法，尽量靠近放到一块，方便查看
	* 不要使用 try catch 处理业务逻辑
	* 使用JSON工具类，不要手动解析和拼装数据
7. 杜绝整个类代码格式化


## View project on GitHub

* [https://github.com/tianshaojie/android-code-style](https://github.com/tianshaojie/android-code-style)


