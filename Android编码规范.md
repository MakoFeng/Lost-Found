#Android 编码规范


[TOC]



----------

##说明
团队协作项目，为了保持大家的代码一致性，进行一些代码格式的规范，方便阅读和后期维护



##文档变更记录表



|修订人|涉及条目|修改内容|修改时间|
|------|--------|--------|--------|
|冯浩|||2014-12-23|


##标示符命名

- 类（classes）：名词，采用大驼峰命名法，尽量避免缩写，除非该缩写是众所周知的，  比如HTML,URL，如果类名称中包含单词缩写，则单词缩写的每个字母均应大写。
|类|描述|例如|
|------|--------|--------|
|activity 类|Activity为后缀标识|欢迎页面类WelcomeActivity|
|Adapter类|Adapte 为后缀标识|详情适配器DetailAdapter|
|公共方法类|Tools或Manager为后缀标识|线程池管理类：ThreadPoolManager日志工具类：LogTools|
|Service类| 以Service为后缀标识|时间服务TimeService|
|BroadcastReceive类|以Broadcast为后缀标识|时间通知TimeBroadcast|
|基础类|以Base开头|BaseActivity,BaseFragment|

- 方法（methods）：动词或动名词，采用小驼峰命名法例如:onCreate(),run()
|方法|说明|
|---|---|
|initXX()|初始化相关方法,使用init为前缀标识，如初始化布局initView()|
|isXX()|checkXX()方法返回值为boolean型的请使用is或check为前缀标识|
|getXX()|返回某个值的方法，使用get为前缀标识|
|processXX()|对数据进行处理的方法，尽量使用process为前缀标识|
|showXX()|弹出提示框和提示信息，使用display为前缀标识|

- 常量（Constants）全部大写,采用下划线命名法.例如：MIN_WIDTH


- layout中id命名
		命名模式为：view缩写_模块名称_view的逻辑名称
下面为常见缩写
|名称|缩写|
|---|---|
|LinearLayout|ll|
|RelativeLayout|rl|
|TextView|tv|
|ImageView|iv|
|ImageButton|ib|
|Button|btn|


- activity中的view变量命名
		命名模式为：逻辑名称+view缩写
		建议：如果layout文件很复杂，建议将layout分成多个模块，每个模块定义一个moduleViewHolder，其成员变量包含所属view

- 资源文件（图片drawable文件夹下）：全部小写，采用下划线命名法，加前缀区分
		命名模式：activity名称_逻辑名称
如果有多种形态如按钮等除外如btn_xx.xml（selector）
|名称|功能|
|---|---|
|btn_xx|按钮图片使用btn_整体效果（selector）|
|btn_xx_normal|按钮图片使用btn_正常情况效果|
|btn_xx_press|按钮图片使用btn_点击时候效果|
|def_search_cell|默认图片使用def_功能_说明|
|ic_more_help|图标图片使用icon_功能_说明|
命名后缀：
|后缀|说明|
|---|---|
|normal|图片的状态，代表普通状态|
|press|图片的状态，代表按下状态|
|select|图片的状态，代表其所占的view被选中|
|unselect|图片的状态，代表其所占的view没有被选中|

- 资源布局文件（XML文件（layout布局文件））
全部小写，采用下划线命名法

1. ContentView命名, Activity默认布局
        例如：activity_main.xml、activity_more.xml
2. Dialog命名：dialog_描述.xml
		例如：dialog_more.xml
3. PopupWindow命名：pop_描述.xml
		例如：pop_more.xml
4. ListView的Item命名lv_描述_item.xml
		例如：lv_more_item.xml
5. 包含项：include_模块.xml
		例如：include_more.xml
6. 动画文件（anim文件夹下）

	前面为动画的类型，后面为方向
|动画命名例子|规范写法|
|---|---|
|fade_in|淡入|
|fade_out|淡出|
|push_down_in|从下方推入|
|push_down_out|从下方推出|
|push_left|推像左方|

##注释
- 类注释
		每个类完成后应该有作者姓名和联系方式的注释，对自己的代码负责
```
/**
 * 作者: fenghao
 * 时间: 14-12-23 13：21
 * 描述: 测试用的
 * 联系方式: s.e.fh@streamer-era.com
 */
public class Test {
        ...
}
```

- 方法注释
		每一个成员方法（包括自定义成员方法、覆盖方法、属性方法）的方法头都必须做方法头注释
```
/*
 * 方法名：
 * 功    能：
 * 参    数：
 * 返回值：无
 */
```
- 快注释
```
	private class MessageObserver extends ContentObserver {
		public MessageObserver() {
			super(mainHandler);
		}

		public void onChange(boolean selfChange) {
			Message msg = new Message();
			msg.arg1 = 0;
			mHandler.sendMessage(msg); // 向Handler发送消息,更新UI
		}
	}
```

- 资源文件注释
```
    <!--红色  -->
    <color name="red">#FFC93437</color>
    <!--黄色  -->
    <color name="yellow">#FFF7D23E</color>
```



