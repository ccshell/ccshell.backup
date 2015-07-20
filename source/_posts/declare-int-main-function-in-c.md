title: c++ int main 写法
date: 2015-07-20 09:22:01
tags:
- c++

---
今天看c++ primer 第四版，看到“main 函数的返回值必须是int型”。对此很有怀疑，不是可以用void main？于是查询网络找到了这样一篇文章。
”void main()“?

根据这篇文章，查询了C++之 父 Bjarne Stroustrup的主页faq

http://www.stroustrup.com/bs_faq2.html#void-main

http://www.stroustrup.com/bstechfaq.htm  （中文版本，我可以写"void main()"吗）

 

因此c99（c89可以接受main( ))只支持两种：

	int main( void ){ return 0; }
和

	int main( int argc, char *argv[] ){ return 0; }
c++98（以及c++0x）标准也只支持两种：

	int main(  ){ return 0; }
和

	int main( int argc, char *argv[] ){ return 0; }
其中c99和c++98规定main函数中没有return 语句，编译器需要提供一个return 0

其他形式的main，都是各自编译器自己扩展或为了向后兼容保留了以前的实现。为了代码有良好的风格和可移植，还是按标准书写代码。