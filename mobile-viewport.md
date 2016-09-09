# 一、viewport基础

	+、 布局viewport默认的宽度为980px(ios),安卓不一定,可以用document.body.clientWidth获取到;
	+、 手机浏览器默认为我们做了两件事情：
		1、把页面渲染在一个980px(IOS)的viewport
		2、通过缩放看到整个viewport的全貌
	+、 viewport实际上是为了页面排版正确，再缩放，会显示正常
	+、 viewport分为visual viewport和layout viewport
			visual viewport (window.innerWidth可获得)通过缩放来将layout viewport渲染出来的页面展示在手机，visual viewport是无法得到的，是一个虚拟的角色
			layout viewport 负责把页面渲染在底层

	Q?	为什么不使用默认的（注意是默认的，可以在不加meta标签的时候，去控制台可以用document.body.clientWidth获取到）980px的布局viewport配合缩放展示页面进行开发？
		1、宽度不可控制，不同设备的默认的viewport不一样
		2、页面通过缩小显示的话，交互不友好
		3、缩放后链接有可能不能点击
		4、有缩放，缩放后又有滚动
		5、font-size为40px才等同于pc的12px，不规范

# 二、viewport  meta标签

	由上可知，使用默认viewport开发，不规范，故引入meta标签去改造！！！
	meta里面的content="width=320"，可以改变viewport的宽度
	而用content="width=device-width"可以根据设备调整layout viewport的宽度等于设备宽度
	initial-scale自带width=device-width, initial-scale=1时，layout viewport = visual viewport;

	移动Web最佳viewport设置 ： layout viewport = 设备宽度 = visual viewport;
