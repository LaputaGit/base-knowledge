# Touch基础事件

	+、touchstart:手指触摸屏幕触发（已经有手指在屏幕上不会触发）
	+、touchmove:手指在屏幕滑动，连续触发
	+、touchend:手指离开屏幕时触发
	+、touchcancel:系统取消touch时候触发（不常用）

	**除常见的事件属性外，触摸事件包含专有的触摸属性**
		+、touches:跟踪触摸操作的touch对象数组
		+、targetTouches:特定事件目标的touch对象数组
		+、changeTouches:上次触摸改变的touch对象数组

	**每个touch对象包含属性**
	+、clientX:触摸目标在视口中的x坐标。
	+、clientY:触摸目标在视口中的y坐标。
	+、identifier:标识触摸的唯一ID.
	+、pageX:触摸目标在页面中的x坐标（包含滚动）。
	+、pageY:触摸目标在页面中的y坐标（包含滚动）。
	+、screenX:触摸目标在屏幕中的x坐标。
	+、screenY:触摸目标在屏幕中的y坐标。
	+、target:触摸的DOM节点目标。

	**一个bug：Android只会触发一次touchstart,一次touchmove,touchend不触发
		4.0、4.1、4.4、5.0有这个bug, 4.2没有这个bug
	**
	+、解决方案：
		在touchmove中加入：event.preventDefault()，可以修复bug。
		但要注意event.preventDefault()会导致默认行为不发生，如scroll,导致
		页面不滚动！