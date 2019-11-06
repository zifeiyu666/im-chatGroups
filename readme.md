## 解决了什么问题？
1. 即时通信聊天组/群聊中不同人数头像显示问题。
2. 聊天组最近一次聊天内容长度超出的显示处理。
3. 聊天组标题很长的时候显示省略号，并且聊天组宽度是自适应的。

## 使用的技术和技巧
1. 头像显示
	1. 利用flex布局实现了不同尺寸头像的显示效果
	2. justify-content: center; align-items:center; align-content: center;三个属性联合使用实现了头像的水平处置居中
	3. flex-wrap: wrap-reverse; 实现了换行的时候从下往上排
2. 聊天组标题名称和时间的显示格式
	1. 聊天组标题和时间分别居左居右，利用justify-content: space-between实现
	2. 聊天组标题超宽显示省略号会把时间挤到换行
	```
		.title-text{
			overflow: hidden;
			text-overflow: ellipsis;
			white-space: nowrap;
		}
		.time{
			white-space: nowrap; // 这里为了防止时间被挤到变形
		}
	```