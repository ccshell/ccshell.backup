title: 学习Markdown
date: 2015-06-15 19:02:16
tags:
- Markdown

---

Setext形式的第一级标题
============

	语法：文字下行输入=
	============

Setext形式的第二级标题
-----------

	语法：文字下行输入减号
	------------


# Atx形式的第一级标题

	语法：行开头输入#后接空格或tab
	# Atx形式的第一级标题

## Atx形式的第二级标题

	语法：行开头输入##后接空格或tab
	## Atx形式的第二级标题

### Atx形式的第三级标题

	语法：行开头输入###后接空格或tab
	### Atx形式的第三级标题

> 这是一个块引用
> 
> 这是前一个块引用的第二段
> 
> # 这是第一级标题形式的块引用

	语法：>开头后接空格或tab
	> 这是一个块引用
	> 
	> 这是前一个块引用的第二段
	> 
	> # 这是第一级标题形式的块引用

*这是一个强调*

	语法：斜体强调，用*号括起来，不能有空格
	*这是一个强调*

_这是另一个强调_

	语法：斜体强调，用下划线括起来，不能有空格
	_这是另一个强调_

**这是一个强调**

	语法：加粗强调，用**号括起来，不能有空格
	**这是一个强调**

__这是另一个强调__

	语法：加粗强调，用双下划线号括起来，不能有空格
	__这是另一个强调__

* 一种无序列表，注意要有一个空格
* 它的第二段
* 它的第三段

		语法：*号开头加一个空格或tab
		* 一种无序列表，注意要有一个空格
		* 它的第二段
		* 它的第三段

+ 另一种无序列表
+ 它的第二段
+ 它的第三段

		语法：+号开头加一个空格或tab
		+ 另一种无序列表
		+ 它的第二段
		+ 它的第三段

- 还是另一种无序列表
- 它的第二段

		语法：-号开头加一个空格或tab
		- 还是另一种无序列表
		- 它的第二段

1. 有序的列表
2. 第二段
3. 第三段

		语法：数字加英文句点开头加一个空格或tab
		1. 有序的列表
		2. 第二段
		3. 第三段

这是一个链接行内[测试](http://ccshell.com/ "我是标题")

	这是一个链接行内[测试](http://ccshell.com/ "我是标题")

这是一个链接参考[测试][cc]

[cc]: http://ccshell.com/ "ccshell"

	这是一个链接参考[测试][cc] cc是名称，可以是数字或字符串，不区分大小写
	[cc]: http://ccshell.com/ "ccshell"

显示一个图片行内![github](https://assets-cdn.github.com/images/modules/dashboard/bootcamp/octocat_collabocats.png "我是图片标题")

	显示一个图片行内
	![github](https://assets-cdn.github.com/images/modules/dashboard/bootcamp/octocat_collabocats.png "我是图片标题")

显示一个图片参考![github][pic_path]

[PIC_PATH]: https://assets-cdn.github.com/images/modules/dashboard/bootcamp/octocat_collabocats.png "我是图片标题"

	显示一个图片参考
	![github][pic_path]
	[PIC_PATH]: https://assets-cdn.github.com/images/modules/dashboard/bootcamp/octocat_collabocats.png "我是图片标题"

输入行内代码`<blink>` `&mdash`

	输入行内代码`<blink>` `&mdash` 用反引号括起来

输入整块代码，用4个空格或一个tab缩进后接内容。在列表后面需要8个空格或两个tab缩进

插入html代码

<table border="1"><tr><td>单元格</td></tr></table>

	插入html代码，可以直接输入html标签
	<table border="1">
	<tr>
		<td>单元格</td>
	</tr>
	</table>

