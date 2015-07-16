title: 一行shell实现在当前目录创建A到Z的目录
date: 2015-07-13 09:10:13
tags:
- shell

---

	for var in `seq 65 90`; do var=$(echo "ibase=10; obase=8; ${var}"|bc);printf "\\${var}"|xargs mkdir; done

命令讲解

	seq 65 90 生成65到90的序列。65对应A的ascii的A

	echo "ibase=10; obase=8; ${var}"|bc 将十进制值转换成八进制

	$(...) 一种命令替换方法

	printf "\\${var}" 将八进制的值转换成字符