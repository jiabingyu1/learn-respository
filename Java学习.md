# Java基础

## 一、常用dos命令

1.切换盘符：

​	盘符名 + : + Enter	例：C:\Users\13156>E:	变为：	E:\>

2.检索当前盘符的文件目录：

​	dir	例：E:\>dir

3.进入指定文件夹：

​	cd + 空格 + 文件夹名	例：E:\>cd 游戏	变为：	E:\游戏>

4.进入多级文件夹：

​	cd + 空格 + 文件夹名\文件夹名\...

5.退到上一级目录：

​	cd.. 或 cd + 空格 + ..

6.退到根目录：

​	cd\ 或 cd + \

7.清屏命令行：

​	cls

8.退出命令行窗口：

​	exit

9.创建新文件夹：

​	mkdir + 文件夹名

10.创建多级文件夹：

​	mkdir + 文件夹名\文件夹名

11.删除文件夹：

​	rd + 文件夹名	注意：删除的文件夹必须为空，且删除为直接删除，不会放在回收站

12.删除文件：

​	del + 文件名.后缀名	注意：不走回收站

13.批量删除文件：

​	del + *.后缀名	删除所有后缀为该后缀名的文件



## 二、Java知识准备

### 1.JVM和跨平台

JVM指Java虚拟机，是Java运行程序的假想计算机，主要用来运行Java程序

跨平台指Java代码可以在不同的操作系统上运行（一次编写，到处运行）

### 2.注释

// 	单行注释

/*	*/ 	多行注释

/**	*/ 	文档注释

文档注释作用：文档注释中的内容可以根据javadoc命令快速生成一个文档（API文档），别人拿到这个文档，就能快速对类中实现的功能进行快速了解。

javadoc命令实现：javadoc -d 要生成的文件夹名字 -author -version 文档注释所在的文件名.java

### 3.关键字

Java提前定义好的、具有特殊含义的小写单词，例如public、class、static等。

### 4.字符编码问题

1.编码：保存数据的过程就是编码的过程

2.解码：读数据的过程就是解码的过程

3.注意：

​	a.编码和解码遵守的编码规范必须是一样的

​	b.常见的两个编码规范：GBK（专用于中文，也叫ANSI，一个中文汉字占用2个字节）、UTF-8（一个中文汉字占3个字节）

​	c.dos命令窗口默认编码为GBK

### 5.源文件名和类名

类名必须要和Java文件名一致吗？

​	不一定，但如果不一致，则需要将类名前面的public删除。一个Java文件中只能有一个class带public。

​	因此建议不要在一个文件中写多个class，一个Java文件中就写一个public class即可。

​	main方法必须写在带public的类中

### 6.引用数据类型

类、数组、接口、枚举、注释等。

### 7.转义字符

\n 换行字符

\t 制表符，即tab

输入网址或是磁盘索引时要用双斜杠 \\\ 用以区别转义字符。

### 8.驼峰命名

命名类时，首字母和后续单词首字母全部大写；命名变量和方法时，首字母小写，后续单词首字母全部大写。



## 三、IDEA使用

### 1.目录结构说明

![image-20241226024935699](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241226024935699.png)

因此先创建project，在project下面创建module，在module下创建package

### 2.project的操作

new project -> 创建空项目empty project

<img src="C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241226025253030.png" alt="image-20241226025253030" style="zoom: 80%;" />

<img src="C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241226025451920.png" alt="image-20241226025451920" style="zoom:80%;" />

### 3.module的操作

如果src是灰色的，需要改变一下目录的属性。![image-20241226032259585](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241226032259585.png)

### 4.package的操作

![image-20241226032415628](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241226032415628.png)

package取名规范：

1.公司域名倒着写：

​	例：尚硅谷 域名：www.atguigu.com 故包名为：com.atguigu

### 5.简写操作

main + 回车 定义main方法

sout + 回车 定义输出方法

### 6.快捷键

1.Alt+Enter：导入包，自动修正代码

2.ctrl+Y：删除光标所在行

3.ctrl+D：复制粘贴光标当前行

4.ctrl+Alt+L：整理代码，格式化

5.ctrl+/：光标当前行注释

6.ctrl+shift+/：所选代码注释

7.Alt+shift+上下箭头：移动当前行



## 四、Java基本语法

### 1.Scanner键盘录入

1.概述：是Java定义好的一个类

2.作用：将数据通过键盘录入的形式放到代码中参与运行

3.位置：java.util

4.使用：

​	a.导包（明确使用哪个包下的哪个类）：import java.util.Scanner

​	b.创建对象	Scanner 变量名 = new Scanner(System.in)

​	c.调用方法，实现键盘录入	录入整数：变量名.nextInt()	录入字符串String型：变量名.next()

5.变量名.next()：录入字符串，遇到空格和回车就结束输入

   变量名.nextLine()：录入字符串，遇到回车就结束输入

### 2.Random随机数

1.概述：Java自带的一个类

2.作用：可以在指定的范围内随机一个整数

3.位置：java.util

4.使用：

​	a.导包：import java.util.Random

​	b.创建对象	Random 变量名 = new Random()

​	c.调用方法，生成随机数	在int的取值范围内随机生成一个整数：变量名.nextInt()

​							 在0~(bound-1)范围内随机：变量名.nextInt(int bound)

​							 在1~10之间随机一个数：变量名.nextInt(10)+1

### 3.数组

1.特点：既可以存储基本类型的数据，也能存储引用类型的数据。

2.定义：

​	a.动态初始化：在定义数组的时候，没有给具体的数据，只指定了长度。

​		数据类型[] 数组名 = new 数据类型[长度]	或	数据类型 数组名[] = new 数据类型[长度]

​	b.静态初始化：在定义数组的时候，直接给出数据。

​		数据类型[] 数组名 = new 数据类型[]{元素1，元素2...}	或	数据类型 数组名[] = new 数据类型[]{元素1，元素2...}

​	c.简化的静态初始化：数据类型[] 数组名 = {元素1，元素2...}

3.操作：获取数组长度	数组名.length	注意：length不是方法，而是属性，因此后面不带括号

4.异常：

​	a.数组索引越界异常 ArrayIndexOutOfBoundsException

​		原因：操作的索引超出了数组范围

​	b.空指针异常 NullPinterException

​		原因：当一个数组对象为Null时调用此对象的其他属性或成员。

### 4.方法

#### 4.1 基本概念

通用格式：修饰符 返回值类型 方法名(参数){return 结果}

形参实参：

​	a.形参：在定义方法的时候形式上定义的参数，此参数还没有值。

​	b.实参：在调用方法的时候对参数赋予的具体值。

四种方法：

a.无参无返回值方法

​	定义：public static void 方法名(){}	调用：直接使用 方法名()

b.有参无返回值方法

​	定义：public static void 方法名(数据类型 变量名){}	调用：方法名(具体值)

c.无参有返回值方法

​	定义：public static 返回值类型 方法名(){return 返回值}

d.有参有返回值方法

​	定义：public static 返回值类型 方法名(数据类型 变量名){return 返回值}

#### 4.2 重载

方法的重载：

1.概述：方法名相同，参数列表不同的方法

2.什么叫参数列表不同？

​	a.参数个数不同

​	b.参数类型不同

​	c.参数类型顺序不同

3.判断两个方法是否为重载：

​	a.和参数名无关

​	b.和返回值无关

<img src="C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241227022525620.png" alt="image-20241227022525620" style="zoom: 50%;" />



## 五、Java进阶

### 1.面向对象

面向过程：自己的事情自己干，代表语言为C语言	例：自己手洗衣服。

面向对象：自己的事情别人帮忙去干，代表语言为Java语言	例：用洗衣机洗衣服，我只需要点按钮，不需要了解内部原理。

注意：若类中的方法带有static关键字，则调用时可以直接使用类名，不用创建对象实例；若不带，则需要先创建对象实例，然后再调用方法。例：Arrays.toString()，toString方法中带有static关键字，所以直接类名加方法；而Scanner sc = new Scanner(System.in)；sc.nextInt()，则是需要创建类名Scanner的对象实例sc，再用实例调用方法。

#### 1.1 类和对象

1.测试类：带main方法的类，主要是运行代码的

2.实体类：是一类事物的抽象表示形式。

​	组成部分：a.属性（成员变量）：这一类事物在什么位置：类中方法外	作用范围：当前类	默认值：整数0，小数0.0，字符'\u0000'，布尔false，引用null

​			   b.行为（成员方法）：这一类事物都能干什么

3.对象：一类事物的具体体现。

#### 1.2 匿名对象

![image-20241227194414644](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241227194414644.png)

1.所谓的匿名对象，就是指没有等号左边的部分，只有等号右边的部分（对象）

2.使用

​	new 对象().成员	例：

<img src="C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241227194655823.png" alt="image-20241227194655823" style="zoom:67%;" />

3.注意：

​	a.如果只想单纯调用一个方法，让方法执行，可以考虑使用匿名对象

​	b.如果涉及到赋值，则不能用匿名对象

![image-20241227195413644](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241227195413644.png)

#### 1.3 成员变量和局部变量

1.定义位置不同	成员变量定义在类中方法外

​				  局部变量定义在方法内部

2.初始化值不同	成员变量有默认值，所以不用手动赋值，可以直接使用

​				  局部变量没有默认值，需要先手动赋值再使用

3.作用范围	成员变量作用于整个类

​			  局部变量只作用于自己所在的方法

4.内存位置不同	成员变量在堆中，跟着对象走

​				  局部变量在栈中，跟着方法走

5.生命周期不同	成员变量随着对象的创建而产生，随着对象的消失而消失

​				  局部变量随着方法的调用而产生，随着方法的执行完毕而消失

### 2.封装

将一个物品封装起来，外界不能直接使用，提高了物品的安全性。

#### 2.1 封装的介绍以及使用

![image-20241228174637132](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241228174637132.png)

#### 2.2 private的使用

被private修饰的成员只能在自己的类中使用，在别的类中使用不了。

注意：将代码放到一个方法中，也是封装的体现。

​	   一个成员被private修饰也是封装的体现，只不过private最具代表性。

#### 2.3 get/set方法的使用

由于使用private关键字之后外界无法再使用private定义的成员变量，因此提供一套接口get和set去实现数据的赋值。set方法为属性赋值，get方法获取属性值。

#### 2.4 this关键字在set方法中的使用

1.如果方法中的成员变量和局部变量重名时，遵循就近原则，先访问局部变量。因此，使用的this代表的是当前的对象，可以区分重名的成员变量和局部变量，this.引用的一定是成员变量。

2.this具体代表哪个对象？

​	看看是哪个对象实体调用的包含this的方法，this代指的就是这个对象实例。例如下图3，person.speak()，调用的speak方法中含有this关键字，调用该方法的对象实体是person，则this代指person。

1.不重名时：

![image-20241228221913066](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241228221913066.png)

输出为：	张三 and 李四

2.重名时：

![image-20241228222009963](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241228222009963.png)

输出为：	李四 and 李四

3.使用this关键字避免此类问题：

![image-20241228222245510](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241228222245510.png)

输出为：	张三 and 李四

#### 2.5 构造方法

1.概述：方法名和类名一致，并且能初始化对象的方法

2.分类：

​	a.无参构造：没有参数

​	b.无参构造：有参数，参数是为指定的属性赋值

3.特点：

​	a.方法名和类名一致

​	b.没有返回值

4.格式：

​	a.无参构造	public 类名(){}	new对象使用	每个类中都默认会有一个无参构造，jvm系统提供。

​	b.有参构造	public 类名(形参){}

#### 2.6 JavaBean

1.JavaBean是Java语言编写类的一种标准规范，符合JavaBean的类要求：

​	a.类必须是具体的（非抽象abstract）和公共的，即public class命名的类。

​	b.具有无参构造和有参构造。

​	c.成员变量私有化，并提供用来操作成员变量的set和get方法。

![image-20241229011034290](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241229011034290.png)

2.编写JavaBean的快捷键：Alt+Insert

​	constructor：构造方法	getter and setter：赋值与提取值

![image-20241229011604851](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241229011604851.png)

3.JavaBean怎么来的？

​	JavaBean都是和数据库的表相关联，类名对应数据库表名，属性名对应列名，对象对应表中每一行数据的总和，属性值对应表中单元格中的数据。

### 3.static关键字

#### 3.1 介绍

1.概述：static是一个静态关键字，可以修饰成员变量，格式：static 数据类型 变量名，也可以修饰一个方法，格式：修饰符 static 返回值类型 方法名(形参){}，

![image-20241229013757330](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241229013757330.png)

修改多个对象实体中的同一个值时使用static关键字，这样就可以直接在代码头部通过改变变量内容实现。（类似于const全局变量，一改全改）

2.调用静态成员（即带static关键字）：类名直接调用，不用new对象实体。

3.静态成员特点：属于类成员，不属于对象成员。

​			      静态成员会随着类的加载而加载。

​			      静态成员优先于对象存在于内存中。（因为类创建成功意味着静态成员的创建成功）

​			      凡是根据静态成员所在的类创建出来的对象，都可以共享这个静态成员。

#### 3.2 使用

![image-20241229015421198](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241229015421198.png)

输出：![image-20241229015437810](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241229015437810.png)

#### 3.3 访问特点

1.在静态方法中能直接访问非静态成员吗？

​	不能。要想调用的话，需要new对象然后再调用。

2.在非静态方法中能直接访问静态成员吗？

​	可以。如果在同一个类中可以直接调用访问。如果在不同类中，则需要 类名.方法() 调用。

3.在静态方法中能直接访问静态成员吗？

​	可以。如果在同一个类中可以直接调用访问。如果在不同类中，则需要 类名.方法() 调用。

4.在非静态方法中能直接访问非静态成员吗？

​	可以。如果在同一个类中可以直接调用访问。如果在不同类中，则需要先定义对象实体，然后再调用，即 new 对象.方法() 。

总的来说：先出生的不能访问后出生的。static随着类出生，对象实体随着对象的声明出生。

#### 3.4 实际开发问题

![image-20241229020930214](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241229020930214.png)

### 4.可变参数

需求：定义一个方法，实现n个整数相加；

分析：方法参数位置，只明确了参数的类型，但是不明确参数个数，此时就可以定义成可变参数。

1.定义格式：数据类型...(三个点)变量名

<img src="C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241229023525215.png" alt="image-20241229023525215" style="zoom: 67%;" />

2.注意：a.可变参数的本质是一个数组。

​	      b.参数位置不能连续写多个可变参数，而且当可变参数和其他普通参数一起使用时，可变参数需要放到参数列表最后。

### 5.对象数组

1.需求：定义一个长度为3的数组，存储3个Person对象，遍历数组，将三个Person对象中的属性值获取出来。

2.语法：定义一个存储Person型的数组，需要	Person[] arr = new Person[3];创建大小为3的Person类型数组

![image-20241229145049308](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241229145049308.png)

3.注意申请对象数组时并没有创建对象，只是开辟了一块连续内存空间，此时需要再将每一个数组位置申请为对象实体。

![image-20241229151952349](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241229151952349.png)

### 6.方法参数

1.基本数据类型做参数传递：只在方法中改变值，实际main函数的值不会变（形参和实参问题）。

2.引用数据类型做参数传递：引用类型传递的是地址，因此形参实参都会改变。（类似c语言传递数组进函数）

3.命令行参数：![image-20241229204836786](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241229204836786.png)

​	通过命令行给args数组传参：

![image-20241229212345122](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241229212345122.png)

​	用IDEA给args数组传参：

![image-20241229212538498](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241229212538498.png)

![image-20241229212520448](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241229212520448.png)

​	作用：测试功能是否正常实现。例如：如果方法method()需要形参，那么在main函数里使用方法之后，通过args[0]\args[1]传入形参。

<img src="C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241229214637250.png" alt="image-20241229214637250" style="zoom:80%;" />

### 7.权限修饰符

![image-20250102230456866](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102230456866.png)

![image-20250102230825011](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102230825011.png)

# Java高级

## 一、继承

### 1.继承的介绍

1.父类怎么形成的？

​	我们定义了多个类，发现这些类中有很多重复性的代码，因此定义一个父类，将相同代码抽取出来放到父类中，其他的类直接继承这个父类，就可以直接使用父类中的内容了。

2.怎么去继承？

​	使用关键字extends，格式：子类 extends 父类

3.注意：

​	a.子类可以继承父类中的私有和非私有成员，但是不能直接使用父类的私有成员。（有三种方法解决这个问题）

​	b.构造方法不能继承。

### 2.继承的基本使用

1.定义一个父类，在其中定义重复性代码。

2.定义一个子类继承父类（关键字extends）。

3.创建子类对象，直接使用父类中非私有成员。

### 3.继承的成员特点

#### 3.1 成员变量

1.子类和父类中的成员变量不重名：

![image-20241231023707712](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241231023707712.png)

​	父类不能直接调用子类中特有的成员。

2.子类和父类中的成员变量重名：

​	先找自己内部的成员，如果没有，且当前类是子类，则再找父类；如果没有，且当前类是父类，则报错。

#### 3.2 成员方法

1.子类和父类中的成员方法不重名：

​	父类不能直接调用子类特有的方法。

2.子类和父类中的成员变量重名：

​	先找自己内部的方法，如果没有，且当前类是子类，则再找父类；如果没有，且当前类是父类，则报错。

### 4.方法的重写

1.概述：子类中有一个和父类方法以及参数列表相同的方法。

2.前提：只有继承中才能存在重写。

3.访问顺序：看new的是谁，就先调用谁中的方法，如果new的是子类，则先调用的是子类中的方法，当子类中不存在该方法时，再找父类中的该方法。

4.检测是否为重写方法：在该方法上写@Override，若报错，则证明不是重写。

5.注意：

​	a.子类重写父类方法后，权限必须保证大于或等于父类权限（权限指的是访问权限）。

​		权限修饰符顺序：public --> protected --> 默认 --> private

​	b.子类方法重写父类方法，方法名和参数列表要和父类完全一致。

​	c.私有方法不能被重写，构造方法不能被重写，静态方法不能被重写。

​	d.子类重写父类方法之后，返回值类型应该是父类方法返回值类型的子类类型。

​	d例：

![image-20241231025923973](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241231025923973.png)

​	其中，左边是父类，右边是子类。子类重写父类方法之后，返回值类型为Zi，其为父类方法返回值Fu的子类	类型。

![image-20241231030051692](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241231030051692.png)

​	其中，左边是父类，右边是子类。子类重写父类方法之后，返回值类型为Fu，其不是父类方法返回值Zi的子类类型。

6.方法重写的使用场景：

​	功能升级改造，子类需要对父类中已经实现好的功能进行重新改造。 

### 5.继承中的关键字

​	注意，在创建对象时，如果创建的是子类对象，则会先进行父类创建。即，new子类时，在调用子类构造方法之前，先调用了父类的无参构造方法。原因：每个构造方法的第一行，默认有一个super()，这是虚拟机JVM自动提供的，super()代表的是父类的无参构造。

#### 5.1 super关键字

1.概述：代表的是父类引用

2.作用：可以调用父类中的成员

3.使用：

​	a.调用父类构造方法 --> 在子类中的构造中写super()，即调用父类无参构造 或super(实参)，即调用父类有参构造。

​	b.调用父类成员变量 --> super.成员变量名

​	c.调用父类成员方法 --> super.成员方法名(参数)

#### 5.2 this关键字

1.概述：代表的是当前对象。（哪个对象调用this所在的方法就表示哪个对象）

2.作用：

​	a.区分重名的成员变量和局部变量。

​	b.调用当前对象中的成员。

3.使用：

​	a.调用当前对象的构造方法：this()：调用当前对象的无参构造。	this(参数)：调用当前对象的有参构造。

​	b.调用当前对象的成员变量：this.成员变量名

​	c.调用当前对象的成员方法：this.成员方法名()

4.注意：

​	不管是super还是this，只要在构造方法中使用，都必须在第一行，因此二者不能同时存在。

### 6.继承的特点

1.继承只能单继承，不能多继承。即子类只能有一个父类。

2.继承支持多层继承。

3.一个父类可以有多个子类。

4.构造方法不能继承，也不能重写。私有方法可以继承，但不能使用，也不能重写。静态方法可以继承，但不能被重写。

### 7.私有属性的使用

父类的私有成员可以继承，但不能使用，也不能重写。虽然父类中的成员私有，但是可以通过提供get、set方法，设置子类从父类中继承的私有成员，并通过get方法访问。



## 二、抽象

<img src="C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241231234745804.png" alt="image-20241231234745804" style="zoom:67%;" />

<img src="C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20241231234820692.png" alt="image-20241231234820692" style="zoom:67%;" />

1.抽象类怎么来的？

​	抽取共性方法放到父类中，发现方法无法确定具体实现，因为每个子类对该方法的具体实现细节不同，故定义为抽象方法。抽象方法所在的类一定是抽象类。

2.实现方式：关键字abstract

3.定义抽象方法格式：	修饰符 abstract 返回值类型 方法名(参数);

4.抽象类：	public abstract class 类名{}

5.注意：

​	a.抽象方法所在的类一定是抽象类。

​	b.抽象类中不一定非要有抽象方法。

​	c.子类继承抽象父类时，需要重写父类中所有的抽象方法，否则会报错，除非该子类也是抽象类。即抽象方法最终都是要实现的。

​	d.抽象类不能创建对象实体，因此只能通过创建非抽象的子类对象调用重写方法。

​	e.虽然抽象类不能new对象但其仍有构造方法,该方法是为了在子类创建对象时初始化父类中的属性而使用的

6.可以将抽象类视为一类事物的标准，要求只要是属于这一类的，就必须要拥有抽象类中的方法，必须实现该方法（通过重写的方式）



## 三、接口

### 1.作用

​	接口是一个引用数据类型，是一种标准和规则。

### 2.接口关键字

​	interface接口	public interface 接口名{}

​	implements实现类	implements 接口名{}

### 3.接口中可定义成员

​	a.jdk7以及之前：

​		抽象方法：public abstract	即使不写默认也有

​		成员变量：public static final 数据类型 变量名 = 值	即时不写默认也有

​		注：被final修饰的变量不能二次赋值（类似const），所以我们一般将final变量视为常量。

​	b.jdk8：

​		默认方法：public default 返回值类型 方法名(形参){}，可以在内部写具体方法，因此可重写也可不重写。

​		静态方法：public static 返回值类型 方法名(形参){}

​	c.jdk9开始：

​		私有方法：private的方法

### 4.使用

![image-20250101185814418](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250101185814418.png)

### 5.方法的具体实现

​	1.抽象方法

![image-20250101223033570](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250101223033570.png)

![image-20250101223052198](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250101223052198.png)

![image-20250101223236714](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250101223236714.png)

​	输出：鼠标打开

​		鼠标关闭

​	2.默认方法（可在接口中具体实现，因此不需要接口实现类）

![image-20250102002556319](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102002556319.png)

![image-20250102002610823](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102002610823.png)

![image-20250102002622598](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102002622598.png)

​	输出：我是重写的默认方法。

​	3.静态方法（可在接口中具体实现，因此不需要接口实现类。同时也不需要创建对象，可以使用接口名直接调用）

![image-20250102003148626](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102003148626.png)

![image-20250102003159345](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102003159345.png)

​	4.默认方法和静态方法的作用：由于使用抽象方法的接口必须要在相关的实现类中将所有的抽象方法全部实现，因此在使用接口定义某个不常用的小功能时，与该接口相关联的接口实现类全部报错。故使用默认方法和静态方法，使其在接口类中就能定义，可以直接用来使用。

### 6.成员变量

​	public static final 数据类型 变量名 = 值	即时不写默认也有

​	final代表最终的，被它修饰的变量不能二次赋值，因此必须要手动赋值常量，且不写public static final默认也有。接口的成员变量使用接口名直接调用即可，不需要创建对象实体。

![image-20250102011722809](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102011722809.png)

![image-20250102011735618](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102011735618.png)

![image-20250102011745876](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102011745876.png)

### 7.多接口

当实现类有多个接口时，若两个接口中某两个方法完全一样（名称，参数顺序，返回值全部相同），则需要在实现类中重写一次，即使是已经实现的默认方法和静态方法也一样。

![image-20250102013735009](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102013735009.png)![image-20250102013753891](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102013753891.png)![image-20250102013821043](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102013821043.png)![image-20250102013840392](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102013840392.png)

输出：我是重写的实现方法

### 8.方法中传递

1.接口类型作为方法参数传递：传参数时需要传递的是接口的实现类的对象实体。

![image-20250103023917994](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250103023917994.png)

2.接口作为返回值传递：实际返回的是实现类对象，但还是要用接口接收，即USB usb = method01();

![image-20250103024156571](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250103024156571.png)



## 四、接口与抽象类异同

### 1.相同点

1.两者都是抽象类，都不能创建对象实体，即都不能new。

2.interface实现类及abstrct class的子类都必须要实现已经声明的抽象方法。即带有abstract关键字的方法必须全部实现。

### 2.不同点

1.接口需要实现，要用implements；而抽象类需要继承，要用extends。

2.一个类可以实现多个接口，但一个类只能继承一个抽象类。

3.接口强调特定功能的实现，而抽象类强调所属关系。抽象类一般作为父类使用，可以有成员变量，构造方法，成员方法，抽象方法等；接口大多数情况下成员单一，一般使用接口调用方法，被视为是功能的大集合。

4.接口中只要不是default和static方法，每个接口实现类中都要全部实现这个接口中的所有方法；而抽象类中只需要在最后所有abstract方法均被实现即可，不需要每个子类都要实现所有的抽象方法。

### 3.interface应用场景

1.类与类之前需要特定的接口进行协调，而不在乎其如何实现。

2.作为能够实现特定功能的标识存在，也可以是什么接口方法都没有的纯粹标识。

3.需要将一组类视为单一的类，而调用者只通过接口来与这组类发生联系。

4.需要实现特定的多项功能，而这些功能之间可能完全没有任何联系。

### 4.abstract class应用场景

在既需要统一的接口，又需要实例变量或缺省的方法的情况下，就可以使用它。最常见的有：

1.定义了一组接口，但又不想强迫每个实现类都必须实现所有的接口。可以用abstract class定义一组方法体，甚至可以是空方法体，然后由子类选择自己所感兴趣的方法来覆盖。

2.某些场合下，只靠纯粹的接口不能满足类与类之间的协调，还必需类中表示状态的变量来区别不同的关系。abstract的中介作用可以很好地满足这一点。

3.规范了一组相互协调的方法，其中一些方法是共同的，与状态无关的，可以共享的，无需子类分别实现；而另一些方法却需要各个子类根据自己特定的状态来实现特定的功能。



## 五、多态

### 1.介绍

1.前提：

​	a.必须有子父类继承或者接口实现关系

​	b.必须有方法的重写，没有重写，多态就没有意义

​	c.创建对象实体和之前不同，格式：父类 对象名 = new 子类();

2.注意：

​	多态下不能调用子类特有功能。



![image-20250102041441708](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102041441708.png)

### 2.基本使用

![image-20250102041053165](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102041053165.png)

![image-20250102041108481](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102041108481.png)

![image-20250102041115306](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102041115306.png)

### 3.成员访问特点

1.多态成员变量：编译运行看左边。

![image-20250102042117162](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102042117162.png)

![image-20250102042133988](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102042133988.png)

![image-20250102042144615](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102042144615.png)

​	输出：10

​	tag是Fu中的值，只能取到父中的值

2.多态成员方法：编译看左边，运行看右边。

![image-20250102042335926](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102042335926.png)

![image-20250102042414063](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102042414063.png)

![image-20250102042429513](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102042429513.png)

​	输出：我是子类方法

​	tag的门面类型是Fu,但实际类型是Zi,所以调用的是重写后的方法。

### 4.多态的好处（为什么学多态）

1.问题描述：

​	如果使用原始方式new对象（等号左右两边一样），既能调用重写的成员，还能调用继承的成员，还能调用自己特有的成员。但是多态方式new对象只能调用重写的，而且不能直接调用子类特有的成员，那么为什么要使用多态呢？

​	答：当子类作为参数传递时，例如public void eat(Dog dog){}，此时另一个类Cat也想用这个方法，但是参数只支持Dog类，因此Cat要想使用该方法，还需要public void eat(Cat cat){}，非常麻烦，因此将参数设置为父类，即public void eat(Animal animal){}，这样两个类就都可以使用该方法了。

​	另外，当public void eat(Animal animal){}时，如果传入dog，则有Animal animal = dog = new Dog();如果传入cat，则有Animal animal = cat = new Cat();因此，可以直接定义为：Animal animal = new Dog();	或	Animal animal = new Cat();（方法参数中大类能接收小类，例如double既能接收int型又能接收float型）

​	即：如果形参传递父类类型，调用此方法，父类类型可以接收任意子类对象，传递哪个子类对象，就指向哪个子类对象，就调用那个子类对象重写的方法。

2.多态方式和原始方式new对象的优缺点：

原始方式：

​	a优点：既能调用重写的成员，还能调用父类非私有的成员，还能调用自己私有的成员。

​	b缺点：扩展性差。

多态方式：

​	a优点：扩展性强。

​	b缺点：不能直接调用子类特有的成员。

### 5.多态的转型

#### 5.1 向上转型

父类引用指向子类对象。例：double a = 1;//1是int型

#### 5.2 向下转型

1.将大类型强制转为小类型。

2.表现方式：

​	父类类型 对象名 = new 子类对象()  -->  向上转型  -->  double b = 1

​	子类类型 对象名2 = (子类类型)对象名1  -->  向下转型  -->  int i = (int)b

3.想要调用子类特有功能，我们就需要向下转型。

![image-20250102172415259](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102172415259.png)

#### 5.3 转型出现的问题

类型转换异常：

![image-20250102185135025](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102185135025.png)

​	调用方法的参数为dog对象实体时，可以执行；但如果为cat对象实体时，在Dog dog = (Dog) animal语句中会强制把Cat型变量animal转换为Dog型变量，两种数据类型完全不同，既不是父子关系，也没有继承关系，因此导致类型转换异常。

解决：在向下转型之前先判断类型。关键字：instanceof	判断结果为布尔型。

使用：	对象名  instanceof  类型	判断的时关键字前面的对象是否符合关键字后面的类型。

![image-20250102185609810](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250102185609810.png)



## 六、final关键字

### 1.final修饰类

1.格式：public final class 类名{}

2.特点：被final修饰的类不能继承。

​	例：若public final class Animal{}	则public class Dog extends Animal{}报错

### 2.final修饰方法

1.格式：修饰符 final 返回值类型 方法名(形参){}

2.特点：被final修饰的方法不能被重写。

3.注意：final和abstract不能同时使用，因为abstract要求重写，而final又不能重写。

### 3.final修饰局部变量

1.格式：final 数据类型 变量名 = 值

2.特点：被final修饰的局部变量不能被二次赋值，即被视为常量。

### 4.final修饰对象

2.格式：final 数据类型 对象名 = new 数据类型();

2.特点：被final修饰的对象，地址值不能改变，但是对象中的属性值可以改变。可以理解为：改变地址才是二次赋值，而改变内部属性值不算二次赋值。

### 5.final修饰成员变量

1.格式：final 数据类型 变量名 = 值

2.特点：需要手动赋值且不能二次赋值



## 七、内部类

### 1.介绍

1.什么时候使用内部类？

​	当一个事物的内部，还有一个部分需要完整的结构去描述，而这个内部的完整结构又只为外部事物提供服务，那么整个内部的完整结构最好使用内部类。

​	比如人类都有心脏，人类本身需要属性、行为去描述，人类内部的心脏也需要心脏特殊的属性和行为去描述，此时心脏就可以定义成内部类，即人类中的一个心脏类。

2.在Java中允许一个类的定义位于另外一个类内部，前者称之为内部类，后者称之为外部类。

即：`class A{`

​		`class B{`

​		`}`

​	`}`

3.分类：成员内部类（静态、非静态）、局部内部类、匿名内部类

### 2.成员内部类

#### 2.1 静态成员内部类

1.格式：直接在定义内部类的时候加上static关键字。

​	public class A {

​		static class B {

​		}	

​	}

2.注意：

​	a.内部类可以定义属性、方法、构造方法等。

​	b.静态内部类可以被final或者abstract修饰。且被final修饰后，不能被继承；被abstract修饰后，不能创建对象实体。

​	c.静态内部类不能调用外部的非静态成员。

​	d.内部类还可以被四种权限修饰符修饰。

3.调用静态内部类成员：

​	外部类.内部类 对象名 = new 外部类.内部类();

<img src="C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250103020641215.png" alt="image-20250103020641215" style="zoom:67%;" />

#### 2.2 非静态成员内部类

1.格式：

​	public class A {

​		class B {

​		}	

​	}

2.注意：

​	a.内部类可以定义属性、方法、构造方法等。

​	b.非静态内部类可以被final或者abstract修饰。且被final修饰后，不能被继承；被abstract修饰后，不能创建对象实体。

​	c.非静态内部类不能调用外部的非静态成员。

​	d.内部类还可以被四种权限修饰符修饰。

3.调用非静态内部类成员：

​	外部类.内部类 对象名 = new 外部类().new 内部类();

#### 2.3 类名重名问题

外部类的成员变量和内部类的成员变量以及内部类的局部变量重名时怎么区分？

​	使用关键字	this	和	类名.this

![image-20250103021853642](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250103021853642.png)

![image-20250103021909562](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250103021909562.png)

​	输出：

​		王五

​		李四

​		张三

### 3.局部内部类

#### 3.1 基本操作

可以定义在方法中、代码块中、构造方法中。注意：局部内部类中的方法需要间接访问。

![image-20250103022831196](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250103022831196.png)

![image-20250103022915662](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250103022915662.png)

​	输出：heart beat!!

#### 3.2 实际操作

在启动类中创建方法实现接口，不需要额外定义接口实现类。

![image-20250104024135108](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250104024135108.png)

### 4.匿名内部类

#### 4.1 基本操作

匿名内部类可以理解为没有显式声明出类名的内部类。

1.问题描述：我们如果想实现接口，简单使用一次抽象方法，我们就需要创建一个实现类去实现这个接口，重写抽象方法，还要创建对象实体，过于麻烦。因此，如果只是单纯的使用一次接口方法，该怎么样才能更简单去实现？

使用匿名内部类，即使用一种格式就可以代表了实现类对象实体或子类对象实体。

格式：

法一、

​	new 接口/抽象类() {	//点之前的语句代表定义了一个对象实体，只不过是匿名的形式

​		重写方法

​	}.重写的方法();

法二、

​	类名.对象名 = new 接口/抽象类() {	//同上，只不过这种方式写出了对象名

​		重写方法

​	}

对象名.重写的方法();

2.什么时候使用匿名内部类？

当简单的只调用一次接口中的方法时，我们可以使用匿名内部类直接重写方法，而不用先实现接口实现类，再创建对象实体去麻烦的实现。

#### 4.2 复杂用法

1.匿名内部类当参数传递

![image-20250104054523123](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250104054523123.png)

​	蓝色部分即匿名内部类，也可以被视为一个对象实体，因此才能被形参为USB类的方法所调用。

2.匿名内部类当返回值返回

![image-20250104055008115](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250104055008115.png)

​	总结：复杂用法和基础方法大致相同，只不过把匿名内部类放到了另一个方法中，如果不重新定义其他方法，那么复杂用法就转化为了基础用法的一般格式。

​	蓝色部分即匿名内部类，也可以被视为一个对象实体，由于返回值为USB类型，因此main方法中定义了一个对象实体去接收，接收后的对象实体就可以使用匿名内部类的方法了。



## 八、异常

### 1.介绍

1.概述：代码出现了不正常的现象；在Java中，异常都是一个一个的类，即Throwable类下的Exception类内部的子类。![image-20250104180719004](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250104180719004.png)

### 2.创建异常对象

创建异常对象只是为了后面学习如何处理异常，其他的暂时没有啥意义。

1.关键字：throw

2.格式：throw new 异常

![image-20250104214227556](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250104214227556.png)

​	输出：我要执行了

![image-20250104214308180](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250104214308180.png)

​	出现异常：NullPointerException

### 3.异常处理方式

#### 3.1 throws

1.格式：在方法参数和方法体之间位置上写

throw 异常

2.意义：处理异常	将异常向上抛

![image-20250104214856915](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250104214856915.png)

![image-20250104215212872](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250104215212872.png)

add方法中先出现异常，在方法定义后面加上throws Exception，异常就会向上抛给main方法；在main方法定义后面加上throws Exception，异常就会向上抛给虚拟机JVM，JVM检测到异常后，向用户输出异常处理程序错误信息，并终止程序执行。

3.当出现多个异常时，格式：throws 异常1,异常2...

![image-20250104215535302](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250104215535302.png)

​	如果throws的多个异常之间有字父类继承关系，我们可以直接throws父类异常。

![image-20250104215757775](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250104215757775.png)

​	由于IOException是FileNotFoundException的父类，因此可以仅抛出父类异常。

​	如果不知道多个异常之间是否有子父类继承关系，也可以直接throws Exception

#### 3.2 try-catch

1.格式：

​	try {

​		可能出现异常的代码

​	}catch(异常 该异常对象的对象名) {

​		处理异常的代码	//一般会将异常信息保存到日志文件中

​	}

2.意义：处理异常	在catch中直接处理

![image-20250104220651014](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250104220651014.png)

![image-20250104220745568](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250104220745568.png)

​	对比throws方式，try-catch后续仍然能够继续执行，而throws则是直接终止程序。

3.当出现多个异常时，格式：

​	try {

​		可能出现异常的代码

​	}catch(异常1 该异常对象的对象名) {

​		处理异常的代码	//一般会将异常信息保存到日志文件中

​	}catch(异常2 该异常对象的对象名) {

​		处理异常的代码	//一般会将异常信息保存到日志文件中

​	}catch(异常3 该异常对象的对象名) {

​		处理异常的代码	//一般会将异常信息保存到日志文件中

​	}catch(异常n 该异常对象的对象名) {

​		处理异常的代码	//一般会将异常信息保存到日志文件中

​	}... ...



​	如果try-catch的多个异常之间有字父类继承关系，我们可以直接catch父类异常。

​	如果不知道多个异常之间是否有子父类继承关系，也可以直接catch Exception

### 4.finally关键字

1.概述：代表的是不管是否触发了异常，都会执行的代码块。

特殊情况：如果之前执行了System.exit(0)，表示终止当前正在执行的Java虚拟机，则finally关键字的代码块就不会执行。

2.格式：

​	try {

​		可能出现异常的代码

​	}catch(异常 该异常对象的对象名) {

​		处理异常的代码	//一般会将异常信息保存到日志文件中

​	}finally{

​		不管是否有异常，都会执行的代码块

​	}

![image-20250104231008907](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250104231008907.png)

​	调用method，sout时遇到空指针异常，被catch捕获；捕获后返回1，由于是return，故停止该方法继续运行；此时jvm虚拟机检测到finally关键字，因此暂缓方法的停止，首先执行了finally关键字中的代码后，再返回1交给result接收，最后输出result。

3.使用场景：

​	a.关闭资源

​	b.对象如果没有用了，则GC(垃圾回收器)会回收堆内存中的垃圾,释放内存。但是有些对象GC无法回收，比如连接对象Connection、I/O流对象、Socket对象等，这需要我们自己手动回收、手动关闭，此时关闭动作就可以放在finally中表示必须执行。

​	因此，将来不能回收的对象new完之后，后续操作不管是否操作成功，是否有异常，我们都需要手动关闭，此时我们可以将关闭资源的代码放到finally中。

### 5.继承情况下的异常

问题：

​	1.如果父类中的方法抛出异常，那么子类重写之后的方法是否也需要抛出异常？	子类可以不需要抛出异常

​	2.如果父类中的方法没有抛出异常，那么子类重写之后的方法是否能抛出异常？	子类不能抛出异常

### 6.两种处理的使用时机

#### 6.1 try_catch

处理异常之后，还想让后续的代码正常运行，则使用try_catch

#### 6.2 throws

如果方法之间是递进关系（即调用），可以先throws，但是最终仍需要使用try_catch进行统一的异常处理。

### 7.自定义异常

1.需求：键盘录入一个用户名实现登录功能，如果登录失败则抛出异常LoginUserException

​	LoginUserException并不是Exception的子类，因此需要自己定义。

![image-20250105023548688](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250105023548688.png)

![image-20250105023601550](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250105023601550.png)

​	输出：

![image-20250105023616786](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250105023616786.png)

2.如果继承Exception，就是编译时期异常；如果继承RuntimeException，就是运行时异常。

### 8.打印异常信息

Throwable类中的方法：

​	String toString()：输出的是异常类型(LoginUserException)和设置的异常信息(自定义信息)

![image-20250105024152640](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250105024152640.png)

​	String getMessage()：输出的只有异常信息

![image-20250105024253607](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250105024253607.png)

​	void PrintStackTrace()：打印最完全的异常信息，包括异常类型、异常信息以及出现的行数和方法等

![image-20250105024337930](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250105024337930.png)



## 九、Object类

1.概述：所有类的跟类（父类），所有的类都会直接或间接的继承Object类，也包括自己定义的类。

### 1.toString方法

功能：返回对象的字符串表示。格式：包名+类名+@+地址的十六进制

![image-20250105025522716](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250105025522716.png)

### 2.equals方法

功能：比较两个对象的地址值是否相等。格式：返回true表示相等，false表示不相等。

### 3.clone方法

功能：复制一个属性值一样的新对象。

使用：需要被克隆的对象实现Cloneable，并重写clone方法。



## 十、String

### 1.介绍

1.概述：String类代表字符串

2.特点：

​	a.Java程序中的所有字符串字面值（如“abc”）都作为此类的对象实例实现，即凡是带双引号的都是String的对象。

​	b.字符串是个常量，它们的值在创建之后不能被更改。

​		String s = “Hello”;

​		s += “world”;即产生了一个新对象

![image-20250106005812165](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250106005812165.png)

​	c.String对象是不可变的，所以可以共享。

​		String s1 = “abc”;

​		String s2 = “abc”;

![image-20250106005953735](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250106005953735.png)

### 2.实现原理

1.jdk8的时候，String底层是一个被final修饰的char数组；jdk9开始到之后，底层就变成了一个被final修饰的byte数组。原因：占用内存空间的优化，一个char类型占2个字节，一个byte类型占一个字节。

2.由于String底层是数组，而且被final修饰，所以数组地址值无法更改，导致String也无法改变。

### 3.创建

1.String()：利用String的无参构造创建String对象。

2.String(String original)：根据字符串创建String对象。

3.String(char[] value)：根据char数组创建String对象。

4.String(byte[] bytes)：通过使用平台的默认字符集解码指定的byte数组，构造一个新的String

5.简化形式：String 变量名 = “”

注意：

![image-20250106171010401](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250106171010401.png)

### 4.常用方法

#### 4.1 判断方法

boolean equals(String s)	比较字符串内容

boolean equalsIgnoreCase(String s)	比较字符串内容，忽略大小写

#### 4.2 获取方法

int length()：获取字符串长度

String concat(String s)：字符串拼接，返回新串

char charAt(int index)：根据索引获取对应的字符

int indexOf(String s)：获取指定字符串在大字符串中第一次出现的索引位置

String subString(int beginIndex)：截取字符串，从指定索引开始截取到最后，返回新串

String subString(int beginIndex, int endIndex)：截取字符串，从beginIndex开始到endIndex结束，含头不含尾，且返回新串

#### 4.3 转换方法

char[] toCharArray()：将字符串转换成char数组

byte[] getBytes()：将字符串转换成byte数组

String replace(CharSequence c1, CharSequence c2)：替换字符c1为c2

byte[] getBytes(String charsetName)：按照指定的编码将字符串转成Byte数组，参数为编码格式，如GBK或UTF-8等

#### 4.4 分割方法

String[] split(String regex)：按照指定的规则分割字符串，其中regex是正则表达式

![image-20250107020331956](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250107020331956.png)

![image-20250107020348425](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250107020348425.png)

如果间隔的regex指 . （点），则需要转义字符，变为”\\\\.“

#### 4.5 其他方法

boolean contains(String s)：判断字符串中是否包含字串s

boolean endswith(String s)：判断字符串是否以字串s结尾

boolean startswith(String s)：判断字符串是否以字串s为开头

String toLowerCase()：将字符串内所有字母转成小写

String toUpperCase()：将字符串内所有字母转成大写

String trim()：去掉字符串两端的空格



## 十一、StringBuilder

### 1.介绍

1.概述：是一个可变的字符序列，此类提供了一个与StringBuffer兼容的一套API（即StringBuilder与StringBuffer功能一样、作用一样、使用方式一样，只有对象不一样），但StringBuilder不保证线程同步（线程不安全，效率高）。

2.作用：主要是字符串的拼接。

3.问题：String也能拼接，为什么一定要用StringBulider拼接字符串？

​	String拼接字符串时，每拼接一次都会产生新的String对象，即在内存中开辟新的空间，如果拼接的次数多了，会占用内存，效率比较低；

​	StringBulider底层自带一个缓冲区（没有被final修饰的byte数组），拼接字符串后都会在此缓冲区中保存，在拼接的过程中不会随意产生新的对象，节省内存。

4.StringBuilder特点：

​	a.底层自带缓冲区，此缓冲区是没有被final修饰的数组，默认长度为16

​	b.如果超出数组长度，数组会自动扩容，即创建一个新长度的新数组，将老数组的元素复制到新数组中，然后将新数组的首部地址重新赋值给老数组

​	c.默认每次扩容老数组的2倍+2，如果一次性添加的数据超出了该长度，比如又有36个元素，超出了第一次扩容的34，就按照实际数据个数为准，就是以36扩容

### 2.常用方法

StringBuilder append(任意类型数据)：字符串拼接，返回的是StringBuilder自己

StringBuilder reverse()：字符串反转，返回的是StringBuilder自己

String toString()：将StringBuilder转成String



## 十二、数学相关类

### 1.Math类

1.概述：数学工具类

2.作用：主要用于数学运算

3.特点：构造方法私有了，且方法都是静态的

4.使用：类名直接调用，即Math.方法名

5.常用方法：

​	static int abs(int a)：求参数的绝对值

​	static double ceil(double a)：向上取整

​	static double floor(double a)：向下取整

​	static long round(double a)：四舍五入

​	static int max(int a, int b)：求两个数之间的较大值

​	static int min(int a, int b)：求两个数之间的较小值

### 2.BigInteger类

1.问题描述：我们操作数据，将来的数据有可能非常大，大到比long还大，这种数据我们一般称为”对象“，用即BigInteger类声明出的对象。

2.作用：处理超大整数

3.构造：

​	BigInteger(String val)	参数的格式必须是数字形式，但仍是String类型

4.常用方法：

​	BigInteger add(BigInteger val)	加法

​	BigInteger subtract(BigInteger val)	减法

​	BigInteger multiply(BigInteger val)	乘法

​	BigInteger divide(BigInteger val)	除法

​	int intValue()	将BigInteger转换成int

​	long longValue()	将BigInteger转换成long

### 3.BigDecimal类

1.问题描述：使用float或者double做运算时会出现精度丢失问题，因此如果是涉及到高精确度的项目，就不能使用float或double类型直接运算。

2.作用：主要是解决float和double直接运算出现的精度丢失问题。

3.构造方法：

​	BigDecimal(String val)：参数的格式必须是数字形式，但仍是String类型；虽然构造方法中的参数可以是double类型，但是不建议使用。要想传递double型，可以使用valueOf方法。

4.常用方法：

​	static BigDecimal valueOf(double val)：此方法在初始化小数时可以传输double型数据

​	BigDecimal add(BigDecimal val)	加法

​	BigDecimal subtract(BigDecimal val)	减法

​	BigDecimal multiply(BigDecimal val)	乘法

​	BigDecimal divide(BigDecimal val)	除法（如果除不尽，会出现运算异常）

​	BigDecimal divide(BigDecimal divisor, int scale, int roundingMode)：

​		divisor：除数

​		scale：保留多少位小数

​		roundingMode：取舍方式：

​			static int ROUND_UP：向上加1

​			static int ROUND_DOWN：直接舍去

​			static int ROUND_HALF_UP：四舍五入

## 十三、日期相关类

### 1.Date类

1.概述：表示特定瞬间，精确到毫秒

2.构造方法：

​	Date()：获取当前系统时间

​	Date(long time)：获取指定时间，传递毫秒值（从时间原点开始计算）

3.常用方法：

​	void setTime(long time)：设置时间，传递毫秒值（从时间原点开始计算）

​	long getTime()：获取时间，返回毫秒值

### 2.Calendar类

1.概述：Calendar是一个抽象类，使用Calendar类中的方法进行对象的创建与获取。

2.Calendar中的方法：

​	static Calendar getInstance()，即Calendar calendar = Calendar.getInstance()，等号右边是Calendar的一个子类，因此该方法也体现了多态，将子类转型成父类Calendar

3.常用方法

![image-20250108002425799](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250108002425799.png)

![image-20250108010950513](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250108010950513.png)



### 3.SimpleDateFormat日期格式化类

1.概述：将日期格式化

2.构造：SimpleDateFormat(String pattern)

​	pattern代表的是我们自己指定的日期格式（字母不能改变，连接符可以改变）

​	![image-20250108011354596](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250108011354596.png)

​	例如：yyyy-MM-dd HH:mm:ss

3.常用方法：

​	String format(Date date)：将Date对象按照指定的格式转成String

​	Date parse(String source)：将符合日期格式的字符串转成Date对象

![image-20250108015430088](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250108015430088.png)

​	输出：

![image-20250108015454715](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250108015454715.png)

### 4.jdk8新日期类

#### 4.1 LocalDate本地日期

##### 4.1.1 获取LocalDate对象

1.概述：LocalDate是一个不可变的日期时间对象，表示日期，通常被视为年月日

2.获取：

​	static LocalDate now()	创建LocalDate对象

​	static LocalDate of(int year, int month, int dayOfMonth)	创建LocalDate对象，设置年月日

![image-20250108031853717](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250108031853717.png)

结果：

![image-20250108032006448](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250108032006448.png)

##### 4.1.2 LocalDateTime对象

1.LocalDateTime概述：LocalDateTime是一个不可变的日期时间对象，代表日期时间，通常被视为年-月-日-时-分-秒

2.获取：

​	static LocalDateTime now()：创建LocalDateTime对象

​	static LocalDateTime of(int year, Month month, int dayOfMonth, int hour, int minute, int second)：创建LocalDateTime对象，设置年月日时分秒

##### 4.1.3 获取日期字段的方法

int getYear()：获取年份

int getMonthValue()：获取月份

int getDayOfMonth()：获取月中的第几天

##### 4.1.4 设置日期字段的方法

LocalDate withYear(int year)：设置年份

LocalDate withMonth(int month)：设置月份

LocalDate withDayOfMonth(int day)：设置天数

##### 4.1.5 日期字段偏移

方法名plus开头，向后偏移；方法名minus开头，向前偏移

#### 4.2 Period和Duration类

##### 4.2.1 Period计算日期之间的偏差

## 十四、工具类

### 1.System系统相关类

1.概述：系统相关类，是一个工具类

2.特点：

​	a.构造私有，不能利用构造方法new对象

​	b.方法都是静态的

3.使用：

​	类名直接调用

![image-20250109222959563](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250109222959563.png)

### 2.Arrays数组工具类

1.概述：数组工具类

2.特点：

​	a.构造私有

​	b.方法静态

​	c.类名直接调用

![image-20250109223410412](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250109223410412.png)

注意：使用bindarySearch的前提是升序

## 十五、包装类

### 1.基本介绍

1.概述：包装类就是基本类型对应的类，我们需要将基本类型转换成包装类，从而让基本数据类型拥有类的特性，即可以使用包装类中的方法去操作数据。

2.内容：

![image-20250109230230578](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250109230230578.png)

### 2.Integer

1.概述：Integer是int的包装类

2.构造方法（不推荐使用）：

​	Integer(int value)

​	Integer(String s)	s必须是数字形式

3.常用方法：

​	1.装箱：将基本类型转成对应的包装类

​		static Integer valueOf(int i)

​		static Integer valueOf(String s)

​	2.拆箱：将包装类转成对应的基本类型

​		int intValue()

4.拆箱和装箱很多时候都是自动完成的，例：Integer i = 10（自动装箱）

### 3.String

1.基本类型转成String

​	方式1：“+”拼接

​	方式2：String中的静态方法

​		static String valueOf(int i)

![image-20250110164540834](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250110164540834.png)

2.String转成基本类型

![image-20250110164952722](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250110164952722.png)



## 十六、多线程基础

### 1.基础知识

进程：在内存中执行的应用程序

线程：是进程中最小的执行单元

线程作用：负责当前进程中程序的运行，一个进程中至少有一个线程，一个进程也可以有多个线程，这样的应用程序就可以称为多线程程序。

![image-20250108033714443](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250108033714443.png)

使用场景：软件中的耗时操作（拷贝大文件、加载大容量资源、聊天软件、服务器等）

一个线程可以干一件事，采用多线程，我们就可以同时做多件事，提高了CPU利用率。

注意：Java是抢占式调度

主线程：CPU和内存之间为main方法开辟的通道，专门为main方法服务，这个通道叫做“主线程”。

### 2.Thread创建多线程（基础）

#### 2.1 extends Thread

步骤：。

​	1.定义一个类，继承Thread

​	2.重写run方法，在run方法中设置线程任务，即此线程具体执行的代码

​	3.创建自定义线程类的对象

​	4.调用Thread中的start方法，开启线程，jvm自动调用run方法

![image-20250108044418514](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250108044418514.png)

![image-20250108044428101](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250108044428101.png)

​	运行结果：

![image-20250108044446643](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250108044446643.png)

​	注意：每次运行的结果顺序都不一样，因为每次自定义线程和主线程抢占主动权的顺序不一样。

#### 2.2 Runnable接口

1.创建一个类，用来实现Runnable接口

2.重写run方法，设置线程任务

3.利用Thread内的构造方法Thread(Runnable target)，其中，参数是接口实现类的对象实体，创建Thread对象，将自定义的类当作参数传递到Thread构造中。这一步的目的是让我们自己定义的类成为一个真正的线程类对象。

4.调用Thread中的start方法，开启线程，虚拟机jvm自动调用run方法。

![image-20250109013355786](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250109013355786.png)

![image-20250109013412066](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250109013412066.png)

​	运行结果：

![image-20250109013432607](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250109013432607.png)

#### 2.3 两种多线程方式的区别

1.extends_Thread：继承只支持单继承，有继承的局限性

2.实现Runnable接口：没有继承的局限性，例如MyThread extends Fu implements Runnable

3.继承时创建线程对象可以使用自己定义的子类，因为该子类继承了父类Thread；实现接口时则必须采用Thread类的构造方法，同时把自己定义的接口实现类作为构造方法的参数进行传递。

#### 2.4 匿名内部类创建多线程

严格意义上来说，匿名内部类方式属于第二种创建方式，因为匿名内部类创建形式是建立在实现Runnable接口的基础之上。

1.匿名内部类回顾：

​	new 接口/抽象类(){

​		重写方法；

​	}.重写的方法();

或

​	接口名/类名 对象名 = new 接口/抽象类(){

​		重写方法

​	}

​	对象名.重写的方法();

2.实现线程的代码编写：

![image-20250109014836937](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250109014836937.png)

### 3.Thread类中的方法

void start()：开启线程，jvm自动调用run方法

void run()：设置线程任务（即该线程该执行的代码），这个run方法是Thread重写的接口Runnable中的run方法

String getName()：获取线程名字

void setName(String name)：给线程设置名字

static Thread currentThread()：获取正在执行的线程对象（方法在哪个线程中使用，获取到的就是那个线程的对象）

static void sleep(long millis)：线程睡眠，超时后会自动醒来，继续执行

注意：run方法中的异常不能抛出，因为父类没有抛异常，所以只能try-catch

### 4.Thread其他方法

void setPriority(int newPriority)：设置线程优先级，优先级越高，抢到CPU使用权的几率就越大，但并不是每次都能先抢到。

int getPriority()：获取线程优先级

void setDaemon(boolean on)：设置为守护线程，当非守护线程执行完毕，守护线程就要结束，但是守护线程并不是立刻结束。当非守护线程结束之后，系统会告知守护线程，在告知的过程中，守护线程仍继续执行。

static void yield()：礼让线程，让当前线程让出CPU使用权；让两个线程的执行尽可能的平衡一点

void join()：插入线程

### 5.线程安全问题

什么时候发生？

​	当多个线程访问同一个资源时，导致数据出现问题

#### 5.1 同步代码块

1.格式：

​	synchronized(任意对象){

​		线程可能出现不安全的代码

​	}

2.任意对象：也就是锁对象

3.执行特点：一个线程拿到锁之后就会进入同步代码块中执行，在此期间其他线程拿不到锁，也就进不去同步代码块，因此需要在同步代码块外面排队等待，需要等待正在执行的线程执行完毕出了同步代码块（即出了synchronized大括号），等待的线程才能抢到锁，才能进入到同步代码块中执行。

![image-20250109214556927](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250109214556927.png)

![image-20250109214606400](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250109214606400.png)

​	结果：不再出现访问同一个资源的情况

#### 5.2 同步方法

##### 5.2.1 普通同步方法--非静态

1.格式：

​	修饰符 synchronized 返回值类型 方法名(参数){

​		方法体

​		return 结果

​	}

2.实现：

![image-20250109214958380](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250109214958380.png)

3.如果将该方法改造为同步代码块方式，则默认锁为this（即关键字synchronized中的参数改为this）

![image-20250109215311182](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250109215311182.png)

##### 5.2.2 静态同步方法

1.格式：

​	修饰符 static synchronized 返回值类型 方法名(参数){

​		方法体

​		return 结果

​	}

2.默认锁是class对象，区别于非静态同步的默认锁this

3.实现：

![image-20250109220016961](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250109220016961.png)

![image-20250109215849061](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250109215849061.png)

#### 5.3 Lock锁

1.概述：Lock是一个接口，因此new对象时需要调用一个已经实现好的接口实现类。（类似于Runnable接口和Thread的关系）

2.实现类：ReentrantLock

3.方法：

​	lock()：获取锁

​	unlock()：释放锁

![image-20250113021823488](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250113021823488.png)

​	优化：每个线程，无论票数是否成功申请，最后都需要释放锁，因此可以采用finally关键字，把必须执行的unlock方法放到关键字finally中。如下图所示：

![image-20250113023812322](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250113023812322.png)

#### 5.4 Lock与synchronized

synchronized：不管是同步代码块还是同步方法，都需要在结束一对{}之后，才能释放锁对象。

Lock：是通过调用两个方法去控制需要被同步的代码，使用更加灵活。

### 6.死锁

![image-20250110193017310](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250110193017310.png)

![image-20250110193027296](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250110193027296.png)

![image-20250110193043150](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250110193043150.png)

![image-20250110193055706](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250110193055706.png)

​	出现死锁的原因是锁嵌套，因此以后编写代码时应该尽量避免锁嵌套。

### 7.线程生命周期

1.线程状态介绍

![image-20250110193243819](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250110193243819.png)

2.线程状态图

![image-20250110205000953](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250110205000953.png)

![image-20250110205022132](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250110205022132.png)



## 十七、多线程高级

### 1.等待唤醒案例

![image-20250111180717972](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250111180717972.png)

1.案例分析：（一个生产者一个消费者交替执行）

![image-20250112184055686](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250112184055686.png)

2.具体实现：

第一种方式（同步代码块）：

![image-20250112212954025](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250112212954025.png)

![image-20250112213022020](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250112213022020.png)

![image-20250112213043203](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250112213043203.png)

![image-20250112213056019](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250112213056019.png)

​	注意：锁对象也可以在测试类中定义，通过改写两个类的构造方法将锁对象传入生产者和消费者两个对象中，此时两个对象的锁在内存中的地址相同，也就是同一把锁。

第二种方式（同步方法）：

![image-20250113000836295](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250113000836295.png)

![image-20250113000849304](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250113000849304.png)

![image-20250113000903762](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250113000903762.png)

![image-20250113000916340](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250113000916340.png)

​	注意：和上一种方式的差别就是同步方法和同步代码块的区别，也就是synchronized关键字的位置是在方法内还是在方法声明中。另外，这种方式修改了锁的实现，让其在测试类中实现锁的定义，生产者和消费者使用自身的构造方法进行同一个锁的调用。（为了方便截图，BaoZiPu.class中的无参构造删除了，实际开发中要加上无参构造，因为测试类需要使用BaoZiPu类的无参构造进行锁的声明，即BaoZiPu的对象实体充当一个锁）

### 2.多等待多唤醒案例

1.案例分析：

​	如果出现多生产者多消费者，若仍要保持生产一个消费一个的顺序，应该：

​	1.将Thread.notify()方法改为Thread.notifyAll()，因为如果仍是之前的唤醒方法的话，假设当前执行生产者线程，调用唤醒方法，除了当前的线程，其余几个线程任选一个唤醒，但无法保证任选出来的那个线程是消费者线程，有可能再次唤醒了生产者线程进行执行，所以将所有线程全部唤醒，让消费者也有机会抢占CPU。但仍有一个问题，即全部线程都被唤醒时，仍有可能使生产者占有CPU，此时应该用第2步。

​	2.将生产者和消费者线程都加上else，如果不加，假设当前线程为生产者，唤醒所有线程后，仍然是生产者抢占了CPU，此时出了if括号后，仍然向下执行。当else加上后，就不会执行后续的语句，而是重新进行if or else的判断，就会将同为生产者的线程阻塞，直到消费者成功抢占CPU，转而执行消费者线程。（或者不加else，而是将if改为while，本质是一样的，都是让新唤醒的进程再进行一次判断）

2.具体实现（只需更改测试类以及BaoZiPu类中的getCount方法和setCount方法）：

![image-20250113015528926](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250113015528926.png)

![image-20250113015542235](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250113015542235.png)

或（更改if）

![image-20250113020241131](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250113020241131.png)

### 3.Thread创建多线程（高级）

#### 3.1 Callable接口

1.概述：Callable <V>是一个接口，类似于Runnable

2.方法：

​	V call()：设置线程任务，返回V，类似于run方法

3.call方法和run方法的异同：

​	相同点：都是设置线程任务的

​	不同点：

​		1.run方法没有返回值，call方法有返回值

​		2.run方法不能throws抛出异常，call方法可以throws抛出异常

4.call方法中的<V>是什么？

​	a.<V>叫做泛型，用于指定我们操作什么类型的数据，且括号<>中只能写引用数据类型，如果括号中的内容为空，则默认为Object类型数据。

​	b.实现Callable接口时，指定泛型是什么类型，重写的call方法返回值就是什么类型。

5.获取call方法返回值：使用FutureTask类

​	a.FutureTask <V> 是接口Future <V>的实现类

​	b.FutureTask <V>中的方法：

​		构造方法：FutureTask(Callable<V> callable)：创建一个FutureTask对象，它将在运行时执行	给定的Callable

​		V get()：获取call方法中的返回值

![image-20250113040034580](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250113040034580.png)

![image-20250113040050607](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250113040050607.png)

#### 3.2 线程池

1.问题：在之前多线程创建的学习中，每当有一个线程，就需要创建一个相应的线程对象去执行，用完之后还要销毁。如果线程任务非常多，那就需要频繁的创建和销毁线程对象，这样做会耗费大量的内存资源。所以，为了解决此问题，应当想办法让线程对象循环利用，使用的时候直接拿，用完之后再还回去。

![image-20250113041312406](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250113041312406.png)

2.使用：

​	1.创建线程池对象：工具类Executors

​	2.获取线程池对象：工具类Executors中的一个静态方法：

​		static ExecutorService newFixedThreadPool(int nThreads)

​		a.参数：指定线程池中最多创建的线程对象条数

​		b.返回值ExecutorService是线程池，用来管理线程对象

​	3.执行线程任务：ExecutorService中的一个方法：

​		Future<?> submit(Runnable task)：提交一个Runnable任务用于执行

​		Future<T> submit(Callable<T> task)：提交一个Callable任务用于执行

​	4.submit方法的返回值Future：用于接收run方法或是call方法的返回值，但是run方法没有返回值，所以可以不用Future接收，call方法则必须需要用Future接收。Future中有一个方法：V get()	用于获取call方法中的返回值

​	5.关闭线程池：ExecutorService中的一个方法：

​		void shutdown()：启动有序关闭，其中，之前提交的任务仍会申请空闲的线程对象去执行，但是不会接收新提交的任务。 

3.具体实现：

​	Runnable：

![image-20250113044904237](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250113044904237.png)

![image-20250113044922679](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250113044922679.png)

​	Callable：

![image-20250113044954151](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250113044954151.png)

![image-20250113045022680](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250113045022680.png)

​	注意：采用Callable形式时，必须要有一个Future对象接收线程执行结果，若想拿到此结果，则应该调用get方法获得。

### 4.定时器Timer

1.概述：定时器

2.构造方法：Timer()

3.方法：

​	void schedule(TimeTask task, Date firstTime, long period)

​	task：抽象类，是Runnable接口的实现类

​	firstTime：从什么时间开始执行

​	period：每隔多长时间执行一次，参数的单位是毫秒

4.具体实现：

![image-20250113051432819](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250113051432819.png)

## 十八、List集合基础

### 1.单列集合框架

1.集合的背景介绍

​	之前我们学了保存数据的有：变量、数组等，但是数组是定长的，当添加或删除一个数据时，想要改变数组长度就只能定义新的数组。所以，出现了一个长度可变的容器，也就是集合。

2.集合的特点

​	a.只能存储引用数据类型的数据

​	b.长度可变

​	c.集合中含有大量的方法方便我们操作

3.分类：

​	单列集合：一个元素只有一个组成部分，例如list.add("张三")

​	双列集合：一个集合由两部分构成，即key和value，例如map.put(1,"李四")

4.单列集合继承与接口

![image-20250113140320166](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250113140320166.png)

​	注意：

​		a.元素有序是指按照存储顺序排列，即存入的序列为abc，则array[0]=a,array[1]=b,array[2]=c

​		b.LinkedList本质上无索引，但是java为其提供了很多根据索引操作元素的方法

### 2.Collection接口

1.概述：是单列集合的顶级接口

2.使用：

​	a.创建：Collection<E> 对象名 = new 实现类对象<E>()

​		例：`Collection<String> collection = new ArrayList<String>();`

​	b.<E>是指泛型，决定了集合中能存储什么类型的数据，可以统一元素类型。泛型中只能写引用数据类型，如果不写则默认Object类型，此时任何引用类型数据都能够存储。

​	c.泛型细节：在创建对象时，等号前的泛型必须写，等号后的泛型可以不写，即：

​		Collection<E> 对象名 = new 实现类对象()

3.常用方法：	![image-20250113141139456](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250113141139456.png)

### 3.迭代器

#### 3.1 迭代器基本使用

1.概述：Iterator

2.主要作用：遍历集合

3.获取：Collection中的一个方法：Iterator<E> iterator()

4.Iterator中的方法：

​	boolean hasNext()：判断集合中是否存在下一个元素

​	E next()：获取下一个元素

![image-20250113143407339](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250113143407339.png)

​	结果：

![image-20250113143451656](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250113143451656.png)

​	注意：next()方法在获取的时候不要连续使用多次，否则会报错。

#### 3.2 迭代器迭代过程

int cursor;	//下一个元素索引位置

int lastRet = -1;	//上一个元素索引位置

指针从-1开始

![image-20250114001456442](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250114001456442.png)





#### 3.3 迭代器底层原理

1.获取Iterator的时候怎么获取的：

​	Iterator iterator = list.iterator()

​	我们知道Iterator是一个接口，等号右边一定是它的实现类对象

​	问题：Iterator接收的到底是哪个实现类对象呢？答：ArrayList中的内部类Itr对象（Itr只针对ArrayList的迭代器）

![image-20250114012535470](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250114012535470.png)

​	注意：只有ArrayList使用迭代器的时候Iterator接口才会指向Itr，其他的接口使用迭代器时Iterator接口指向的就不是Itr了，例如HashSet使用迭代器：

![image-20250114013110865](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250114013110865.png)

#### 3.4 并发修改异常

需求：定义一个集合，存储（唐僧、孙悟空、猪八戒、沙僧），遍历集合，如果遍历到猪八戒，则向集合中添加白龙马。

​	错误代码：

![image-20250114013754478](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250114013754478.png)

​	结果：并发修改异常

![image-20250114013815840](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250114013815840.png)

​	原因：起初预期操作次数等于实际操作次数，但是使用了add方法会使实际操作次数加一，而且不修改预期操作次数，之后next方法调用checkForComodification方法，预期操作次数和实际操作次数不一致，从而报错。

![image-20250114014314601](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250114014314601.png)

​	解决：AbstractList中存在一个方法：ListIterator<E> listIterator()，ListIterator类中存在一个add方法可以使实际和预期操作数同时改变。而ArrayList继承了AbstractList类，因此ListIterator<E> listIterator()方法也可以用到ArrayList类。即：使用ArrayList对象调用listIterator()方法返回一个ListIterator的对象，再用这个对象调用该类中的add方法，此时实际操作数和预期操作数都会改变。

正确代码：

![image-20250114021243219](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250114021243219.png)

​	结果：

![image-20250114021310231](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250114021310231.png)

​	结论：使用迭代器迭代集合的过程中，不要随意的更改集合长度，容易出现并发修改异常。（只更改不访问也行，因为异常实际上是在next方法中抛出的）

### 4.ArrayList集合

#### 4.1 List接口

1.概述：是Collection接口的子接口

2.常见的实现类：ArrayList、LinkList、Vector

#### 4.2 ArrayList

1.概述：ArrayList是List接口的实现类

2.特点：

​	a.元素有序，即按照存储顺序排序

​	b.元素可以重复

​	c.有索引，可以利用索引去操作数据

​	d.线程不安全

3.数据结构：数组

4.常用方法：

![image-20250114023519650](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250114023519650.png)

5.集合的遍历

![image-20250114024712910](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250114024712910.png)

![image-20250216024001007](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250216024001007.png)

#### 4.3 底层源码分析

1.ArrayList构造方法：

​	a.ArrayList()：构造一个初始值为十的空列表（无参构造）

​	b.ArrayList(int initialCapacity)：构造一个指定容量的空列表（有参构造）

2.ArrayList源码总结：

​	a.并不是使用new就会创建初始容量为10的空列表，而是第一次add的时候，才会创建初始容量为10的空列表。

​	b.ArrayList底层是数组，但为什么集合长度可变？

​		答：ArrayList底层会自动扩容，使用Arrays.copyOf。且自动扩容1.5倍。

3.注意：

​	`ArrayList<String> list = new ArrayList<String>();`现在我们想用集合时都是new，但在实际开发中并不能直接new，而是调用一个方法，查询出了很多数据，此方法返回一个集合，自动将查询出来的数据放到这个集合中，我们想在页面上展示数据，就只能遍历集合。

​	而且将来调用方法，返回的集合类型一般都是接口类型,因此：

​	List<泛型> list = 对象.查询方法()，直接使用父类类型List接收，这样就不需要管调用查询方法的对象是什么类型的集合了，统一使用父类List的方法进行遍历。

### 5.LinkedList集合

#### 5.1 介绍

1.概述：是List接口的实现类

2.特点：

​	a.元素有序

​	b.元素可重复

​	c.没有索引，但有操作索引的方法

​	d.线程不安全

3.数据结构：双向链表

4.方法：有大量直接操作首尾元素的方法

![image-20250114035625715](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250114035625715.png)

​	注意：LinkList[0]作为栈顶，可以调用pop和push方法。

#### 5.2 底层成员

1.LinkedList底层成员

​	transient int size = 0;	//元素个数

​	transient Node<E> first;	//第一个节点对象

​	transient Node<E> last;	//最后一个节点对象

2.Node代表的是节点对象

​	private static class Node<E> {

​		E item;	//节点上的元素

​		Node<E> next;	//记录下一个节点地址

​		Node<E> prev;	//记录上一个节点地址

​		Node(Node<E> prev, E element, Node<E> next) {

​			this.item = element;

​			this.next = next;

​			this.prev = prev;

​		}

​	}

3.LinkedList中的get方法：利用二分思想进行查找优化，避免查找时O(n)的时间复杂度。

![image-20250115021504637](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250115021504637.png)

其中，index代表的是集合中元素的索引。

### 6.增强for

1.基本使用

作用：遍历集合或数组

格式：

​	for(元素类型 变量名:要遍历的集合名或数组名) {

​		//其中，变量名就是代表的每一个元素，在循环体中直接使用变量名即可

​	}

快捷键：

​	集合名或数组名.for

![image-20250115021947906](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250115021947906.png)

输出：

​	张三

​	李四

​	王五

​	赵六

2.注意：

​	a.增强for遍历集合时，底层实现原理为迭代器

​	b.增强for遍历数组时，底层实现原理为普通for

​	所以，不管是用迭代器还是使用增强for，在集合遍历过程中都不要随意的修改集合长度，否则会出现并发修改异常。

### 7.Collection工具类

1.概述：集合工具类

2.特点：构造方法私有、方法都是静态的

3.使用：类名直接调用

4.常用方法：

![image-20250115042358075](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250115042358075.png)

5.方法分析：static<T> void sort(List<T> list, Comparator<? super T> c)

​	比较器Comparator：

​	int compare(T o1, To2) {

​		return o1-o2;	//升序

​		return o2-o1;	//降序

​	}

![image-20250115194833185](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250115194833185.png)

6.另一种方式：采用Comparable接口

​	方法：int compareTo(T o)	return this-o;//升序	return o-this;//降序

![image-20250115195755878](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250115195755878.png)

![image-20250115195808074](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250115195808074.png)

7.Arrays中的静态方法：static <T> List<T> asList(T...a)	作用：直接指定元素，转存到list集合中。

![image-20250115200044924](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250115200044924.png)

## 十九、泛型

### 1.介绍

1.泛型：<>

2.作用：统一数据类型，防止将来的数据转换异常。

3.注意：

​	a.泛型中的类型必须是引用类型

​	b.如果泛型为空，则默认类型为Object

4.为什么使用泛型？

​	1.从使用层面上来说：统一数据类型，防止将来的数据转换异常。

​	2.从定义层面上来说：定义带泛型的类、方法等，将来使用的时候给泛型确定什么类型，泛型就会变成什么类型，凡是涉及到泛型的都会变成确定的类型，代码更灵活。

### 2.泛型的定义

#### 2.1 含有泛型的类

1.定义：

​	public class 类名<E> {}

2.什么时候确定类型？

​	new对象的时候确定类型

3.实现：

![image-20250115232159448](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250115232159448.png)

![image-20250115232215397](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250115232215397.png)

#### 2.2 含有泛型的方法

1.格式：

​	修饰符 <E> 返回值类型 方法名(E e)

2.什么时候确定类型？调用的时候确定类型

3.实现：

![image-20250115235419713](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250115235419713.png)

![image-20250115235432400](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250115235432400.png)

#### 2.3 含有泛型的接口

1.格式：

​	public interface 接口名<E> {}

2.什么时候确定类型？

​	a.在实现类的时候还没有确定类型，在new实现类的时候确定类型

​	b.在实现类时直接确定类型，比如Scanner

3.实现：

​	a：

![image-20250116001013119](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250116001013119.png)

![image-20250116001100821](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250116001100821.png)

![image-20250116001114208](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250116001114208.png)

​	b：

![image-20250116001320921](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250116001320921.png)

#### 2.4 泛型通配符

1.泛型通配符<?>

![image-20250116001918069](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250116001918069.png)

​	运算结果：

![image-20250116001938958](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250116001938958.png)

#### 2.5 泛型的上限下限

![image-20250116002053579](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250116002053579.png)

![image-20250116002544194](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250116002544194.png)

## 二十、Set集合基础

### 1.介绍

1.Set接口并没有对Collection接口进行功能上的扩充，而且所有的Set集合底层都是依靠Map实现。

2.Set和Map是密切相关的，而且Map的遍历需要先变成单列集合，而且只能变成Set集合。

### 2.HashSet集合

1.概述：HashSet是Set接口的实现类

2.特点：

​	a.元素唯一

​	b.元素无序

​	c.无索引

​	d.线程不安全

3.数据结构：哈希表	jdk8之前，哈希表由数组和链表构成；jdk8之后，哈希表由数组、链表和红黑树构成。（加入红黑树目的：查询效率更好）

4.方法：和Collection一样

5.遍历：增强for或迭代器，不能普通for，因为没有索引

![image-20250116222247514](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250116222247514.png)

### 3.LinkedHashSet集合

1.概述：继承HashSet，即：LinkedHashSet extends HashSet

2.特点：

​	a.元素唯一

​	b.元素有序（按照存储顺序排序）

​	c.无索引

​	d.线程不安全

3.数据结构：哈希表和双向链表（保证了元素有序）

4.使用：和HashSet一样

### 4.哈希值

1.概述：是由计算机算出来的一个十进制数，可以看作是对象的地址值

2.获取对象的哈希值，使用的是Object中的方法

​	public native int hashCode()

![image-20250116223358120](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250116223358120.png)

结果：

![image-20250116223413033](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250116223413033.png)

3.注意：如果不重写hashCode方法，默认计算对象的哈希值（也就是地址）；如果重写了hashCode方法，那么计算的就是对象内容的哈希值了。

4.总结：

​	a哈希值不一样，内容肯定不一样

​	b哈希值一样，内容也有可能不一样

5.字符串哈希算法：

![image-20250116234955537](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250116234955537.png)

5.HashSet的存储去重复的过程

1.先计算元素的哈希值（重写hashCode方法），再比较内容（重写equals方法）

2.先比较哈希值，如果哈希值不一样，存入集合

3.如果哈希值一样，再比较内容

​	a.如果哈希值一样，内容不一样，存入集合

​	b.如果哈希值一样，内容也一样，去重复

6.总结：

​	a.如果HashSet存储自定义类型，如何去重复呢？

​		重写hashCode和equals方法，让HashSet比较属性的哈希值以及属性的内容。

​	b.如果不重写hashCode和equals方法，默认调用Object类中的hashCode和equals方法，不同的对象，哈希值肯定不一样，equals比较对象的地址值也不一样，所以此时即使对象的属性值一样，也不能去重复。



## 二十一、Map集合基础

### 1.双列集合框架

![image-20250117022519106](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250117022519106.png)

### 2.Map接口

1.概述：是双列集合的顶级接口

2.元素特点：元素都是由key(键)、value(值)组成。

### 3.HashMap集合

1.概述：HashMap是Map的实现类

2.特点：

​	a.key唯一，value可以重复，如果key重复了，则会发生value覆盖

​	b.无序

​	c无索引

​	d线程不安全

​	e可以存储null键和null值

3.数据结构：哈希表

4.方法：

​	![image-20250117023811016](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250117023811016.png)

​	注意：put方法返回的是被覆盖前的value数据

### 4.LinkedHashMap集合

1.概述LinkedHashMap extends HashMap，即LinkedHashMap是HashMap的子类。

2.特点：

​	a.key唯一，value可以重复，如果key重复了，则会发生value覆盖

​	b.有序

​	c无索引

​	d线程不安全

​	e可以存储null键和null值

3.数据结构：哈希表+双向链表

4.方法：同HashMap。使用时和HashMap一样，只需更改类名。

### 5.HashMap遍历

#### 5.1 方式一

获取key，根据key再获取value

方法：Set<K> keySet()	将Map中的key获取出来，转存到Set集合中。

![image-20250117040835600](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250117040835600.png)

#### 5.2 方式二

同时获取key和value

方法：Set<Map.Entry<K, V>> entrySet()	获取Map集合中的键值对，转存到Set集合中

![image-20250117043415266](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250117043415266.png)

![image-20250117043820492](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250117043820492.png)

### 6.Map中Key去重复

在类中重写Object类中的equals和hashCode方法

不重写时输出：

![image-20250117045132904](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250117045132904.png)

重写后输出：

![image-20250117045200670](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250117045200670.png)

代码（重写方法可用快捷键Alt+Insert）：

![image-20250117045324860](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250117045324860.png)

![image-20250117045229570](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250117045229570.png)

![image-20250117045400009](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250117045400009.png)

![image-20250117045415032](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250117045415032.png)



## 二十二、斗地主案例

![image-20250116201928390](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250116201928390.png)

![image-20250116201944058](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250116201944058.png)

### 1.单列集合

![image-20250116030004469](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250116030004469.png)

### 2.双列集合

![image-20250117165254343](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250117165254343.png)

![image-20250117204733226](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250117204733226.png)

注意：当HashMap中的key为整数类型时，排列有序

## 二十三、Map集合高级

### 1.哈希表存储过程

![image-20250117205847241](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250117205847241.png)

注意：刚开始是散列表的拉链法，当元素数据增加到一定量时，链表就会转化为红黑树，增加查询效率。

![image-20250117210103199](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250117210103199.png)

![image-20250117210113628](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250117210113628.png)

### 2.TreeSet集合

1.概述：TreeSet是Set的实现类

2.特点：

​	a.对元素进行排序

​	b.无索引

​	c.不能存null

​	d.线程不安全

​	e.元素唯一

3.数据结构：红黑树

4.构造方法：

​	TreeSet()	构造一个新的空的set，该set根据其元素的自然顺序进行排序（ASCII）

​	TreeSet(Comparator<? super E> comparator)	构造一个新的空TreeSet，它根据指定比较器进行排序

​	无参构造：

![image-20250117230501911](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250117230501911.png)![image-20250117230509523](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250117230509523.png)

​	有参构造：

![image-20250117231103891](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250117231103891.png)

![image-20250117231125796](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250117231125796.png)

![image-20250117231141691](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250117231141691.png)

### 3.TreeMap集合

1.概述：TreeMap是Map的实现类

2.特点：

​	a.对key进行排序

​	b.无索引

​	c.key唯一

​	d.线程不安全

​	e.不能存null

3.数据结构：红黑树

4.构造方法：

​	TreeMap()：使用键的自然顺序构造一个新的、空的树映射。（ASKII）

​	TreeMap(Comparator<? super E> comparator)：构造一个新的、空的树映射，该映射根据给定比较器进行排序。

​	无参构造：

![image-20250117231945255](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250117231945255.png)

​	有参构造：

![image-20250117232553106](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250117232553106.png)

![image-20250117232542772](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250117232542772.png)

### 4.HashTable集合

1.概述：HashTable是Map的实现类

2.特点：

​	a.key唯一，value可重复

​	b.无序

​	c.无索引

​	d.线程安全

​	e.不能存储null键和null值

3.数据结构：哈希表

4.HashMap和HashTable的异同：

​	相同：元素无序，key唯一，无索引

​	不同：HashMap线程不安全，HashTable线程安全。HashMap可以存储null键null值，HashTable不能。

### 5.Vector集合

1.概述：Vector是List接口的实现类

2.特点：

​	a.元素有序

​	b.有索引

​	c.元素可重复

​	d.线程安全

3.数据结构：数组

4.使用：

![image-20250117233405761](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250117233405761.png)

5.构造方法：

![image-20250117233453428](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250117233453428.png)

注意：

​	a.如果使用空参构造创建对象，数组初始容量为10，如果超出范围，自动扩容2倍

​	b.如果使用有参构造创建对象，数组初始容量为10，如果超出范围，自动扩容 老数组长度+容量增量

### 6.Properties集合

1.概述：也叫属性集，Properties继承Hashtable

2.特点：

​	a.key唯一，value可重复

​	b.无序

​	c.无索引

​	d.线程安全

​	e.不能存null键和null值

​	f.Properties的key和value类型为String

3.数据结构：哈希表

4.公有方法：与HashMap相同；

   特有方法：

![image-20250118000502002](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250118000502002.png)

### 7.集合嵌套

#### 7.1 List嵌套List

需求：创建2个List集合，每个集合中分别存储一些字符串，将2个集合存储到第3个List集合中。

![image-20250118010441047](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250118010441047.png)

#### 7.2 List嵌套Map

![image-20250118011122554](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250118011122554.png)

![image-20250118011133370](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250118011133370.png)

#### 7.3 Map嵌套Map

![image-20250118011957835](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250118011957835.png)



## 二十四、I/O流基础

### 1.File类

![image-20250118020824850](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250118020824850.png)

1.概述：文件和目录（文件夹）路径名的抽象表示。

2.简单理解：

​	我们在创建File对象的时候，需要传递一个路径，这个路径定位到哪个文件或文件夹上，File就代表哪个对象。例：File file = new File("E:\Idea\IO\1.jpg")

3.静态成员：

​	static String pathSeparator;//与系统有关的路径分隔符，为了方便，它被表示为一个字符串

​	static String separator;//与系统有关的默认名称分隔符，为了方便，它被表示为一个字符串

![image-20250118021557373](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250118021557373.png)

4.构造方法：

![image-20250118021724308](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250118021724308.png)

​	注意：创建File对象的时候，传递的路径可以是不存在的，但是传递不存在的路径没有意义。

### 2.File类常见方法

#### 2.1 获取方法

![image-20250118022343435](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250118022343435.png)

#### 2.2 创建方法

![image-20250118022750905](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250118022750905.png)

#### 2.3 删除方法

![image-20250118023022515](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250118023022515.png)

注意：

​	1.删除是直接删除，回收站中并不存在。

​	2.如果删除文件夹，则该文件夹必须要是空文件夹，而且也不走回收站。

#### 2.4 判断方法

![image-20250118023355793](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250118023355793.png)

#### 2.5 遍历方法

![image-20250118023521946](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250118023521946.png)

### 3.绝对路径和相对路径

1.绝对路径：从盘符开始写的路径，例：E:\\\ IEDA \\\ IO \\\ 1.txt

2.相对路径：不从盘符名开始写的路径。

3.针对IDEA中写相对路径：

​	a.口诀：参照路径可省略不写，剩下的就是在IDEA中的相对路径写法。在IDEA中的参照路径其实就是当前project的绝对路径。

​	b.比如：在module下面创建一个1.txt

​		先找1.txt的绝对路径：E:\\ IEDA \\ IO \\ module \\ 1.txt

​		再找参照路径：E:\\ IEDA \\ IO

​		参照路径可以省略：module \\ 1.txt

4.总结：在IDEA中写的相对路径，其实就是从模块名开始写

5.注意：如果直接写一个文件名 1.txt，它所在的位置默认是在当前project下。

### 4.I/O流

1.介绍：将一个设备上的数据传输到另外一个设备上，成为IO流技术。

2.为什么要学习IO流？

​	之前学习的集合和数组可以保存数据，但是这两个都是临时存储（代码运行完毕，集合和数组会从内存中消失，从而数据就不存在了），所以集合和数组达不到永久保存的目的，我们希望咱们的数据要永久保存起来，所以我们就可以将数据保存到硬盘上，之后我们就可以随时拿到硬盘上的数据。

3.IO流的流向（针对javaSE阶段的IO流）

![image-20250118212402464](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250118212402464.png)

​	输入流：将数据从硬盘上读到内存中，即Input

​	输出流：从内存出发，将数据写到硬盘上，即Output

​	要是从电脑和电脑之间做数据传输，就是相对的，即发数据一方是输出，接收数据一方是输入。

4.IO流的分类：

​	字节流：也叫万能流，因为任何数据都是以字节为基础的存储单元。

​		字节输出流：继承OutputStream抽象类

​		字节输入流：继承InputStream抽象类

​	字符流：专门操作文本文档

​		字符输出流：继承Writer抽象类

​		字节输入流：继承Reader抽象类

### 5.字节输出流

1.概述：字节输出流的顶级父类是OutputStream，这是一个抽象类，它含有其中一个子类，FileOutputStream，主要讨论FileOutputStream

2.作用：往硬盘上写数据

3.构造方法：

​	FileOutputStream(File file)：参数传递一个file对象

​	FileOutputStream(String name)：参数直接传递一个文件路径

4.特点：

​	a.构造方法传参，指定的文件如果不存在，输出流会自动创建

​	b.每执行一次相同参数的构造方法，默认都会创建一个新的文件，覆盖掉老文件

​	例子：执行一次构造方法创建一个文件1.txt，在文件中写入数据；之后再次执行一次相同的构造方法，文件会重新创建，内容为空。

5.常用方法：

![image-20250118213906633](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250118213906633.png)

​	注意：write方法按照ASKII编码传参，即fos.write(97)，即传入字符a；传字符串时，可以使用getBytes()方法，把字符串转成ASKII编码格式，返回byte串，然后调用write(byte)

6.字节流的续写：

​	由于每次创建字节流对象时都会覆盖上一个对象，导致每次传输时指定的文件初始状态一直为空，为了能续写上一次传输的文件，应该怎么做？	

​	应该使用FileOutputStream的另一种构造方法

​	FileOutputStream(String name, boolean append)

​		append如果为true，则实现续写功能；如果为false，则覆盖原文件。

### 6.字节输入流

1.概述：字节输入流的顶级父类是InputStream，这是一个抽象类，它含有其中一个子类，FileInputStream，主要讨论FileInputStream

2.作用：将数据从硬盘上读到内存中

3.构造方法：

​	FileInputStream(File file)：参数传递一个file对象

​	FileInputStream(String name)：参数直接传递一个文件路径

​	注意：不像输出流一样可以自动创建文件，传递的参数所表示的文件必须都实际存在

4.常用方法：

![image-20250118220731660](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250118220731660.png)

​	注意：

​		1.read方法一次只能读一个字节，因此同一段代码运行多次返回的值都不一样。例：1.txt中的内容为abc，第一次运行返回a，第二次运行返回b，第三次运行返回c。

​		2.另外：如果数据读完了，则返回 -1	即：第四次运行，数据已经读完，返回 -1

​		3.执行完close方法之后，流对象就不能再继续使用了，也就是不能再调用read方法了。

​		4.每个文件末尾都有一个不可见的结束标记符，read方法如果读取到了结束标记符，则返回 -1，证明该文件已经读完。

![image-20250118230706781](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250118230706781.png)

![image-20250118230749170](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250118230749170.png)

输出：

​	2

​	ab

​	======

​	2

​	cd

​	======

​	1

​	e

### 7.字符输入流

#### 7.1 字节流读取中文问题

问题：由于中文UTF-8编码是3个字节，GBK编码是2个字节，因此如果在遍历读取UTF-8编码中文文件，边读取边输出，且一次仅读取两字节，则会输出乱码。即：

​	如果按照字节读取，每次读取的字节没有构成一个汉字的字节数，就直接输出，则汉字无法显示。

解决：将文本文档中的内容按照字符操作。

#### 7.2 FileReader介绍

1.概述：字符输入流的顶级父类是Reader，这是一个抽象类，它含有其中一个子类，FileReader，主要讨论FileReader

2.作用：将文本文档中的内容读取到内存中

3.构造方法：

​	FileReader(File file)：参数传递一个file对象

​	FileReader(String path)：参数直接传递一个文件路径

4.常用方法：

![image-20250118233635191](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250118233635191.png)

### 8.字符输出流

1.概述：字符输出流的顶级父类是Writer，这是一个抽象类，它含有其中一个子类，FileWriter，主要讨论FileWriter

2.作用：将数据写入文件中

3.构造方法：

​	FileWriter(File file)：参数传递一个file对象

​	FileWriter(String fileName)：参数直接传递一个文件路径

​	FileWriter(String fileName, boolean append)：追加、续写

4.常用方法：

![image-20250119021632054](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250119021632054.png)

​	注意：FileWriter底层自带一个缓冲区，我们写的数据会先保存到缓冲区中，所以我们需要将缓冲区的数据刷新到文件中，即调用flush()方法刷新或close()方法关流。

5.flush()和close()区别：flush方法是将缓冲区的数据刷新到文件中，后续流对象还能继续使用；close方法则是先刷新后关闭，后续流对象不能继续使用。

### 9.I/O异常处理

JDK7及之前：

![image-20250119022616015](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250119022616015.png)

注意：使用流对象需要使用try_catch抛出异常；无论写数据是否执行成功，流对象都应该关闭，所以close方法应该放在finally关键字中；由于close方法也是FileWriter的方法，因此需要抛出异常，所以再写一个try_catch抛出close方法的异常；如果流对象不为null，证明文件创建成功，此时必须close；相反如果为null，则证明创建失败，不需要执行close语句。

JDK7之后：

1.格式：

​	try(IO对象) {

​		可能出现异常的代码

​	}catch(异常类型, 对象名){

​		处理异常

​	}

2.注意：以上格式处理IO异常会自动关流

![image-20250119023332022](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250119023332022.png)



## 二十五、I/O流高级

### 1.字节缓冲流

1.为什么要学字节缓冲流？

​	之前所学的FileOutputStream、FileInputStream、FileReader、FileWriter都叫做基本流，其中FileInputStream和FileInputStream的读写方法都是本地方法（方法声明上带有native），本地方法是和系统以及硬盘相关联的，也就是说这两个对象的读和写都是在硬盘之间进行读写的，效率不高；缓冲流中底层带一个长度为8192的数组，这个数组叫做缓冲区，此时的读和写都是在内存中完成的（也就是在缓冲区中完成的），极大缩短时间。

​	使用之前需要将基本流包装成缓冲流，也就是new缓冲流对象时要传入基本流，即：将基本流作为构造方法的参数进行传递。

2.字节缓冲流

​	a.BufferedOutputStream：字节缓冲输出流

​		构造方法：BufferedOutputStream(OutputStream out)

​		使用：和FileOutputStream一样

​	b.BufferedInputStream：字节缓冲输入流

​		构造方法：BufferedInputStream(InputStream in)

​		使用：和FileOutputStream一样

![image-20250120013717468](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250120013717468.png)

![image-20250120013732582](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250120013732582.png)

​	运行可知，使用缓冲流复制文件效率比基本流高得多。

3.使用缓冲流时为什么只需要关闭缓冲流，而不需要再关闭基本流？

​	缓冲流的close方法底层会自动关闭基本流。

4.缓冲流底层有数组，即缓冲区，这些数组（缓冲区）都是在内存之间进行读写，那么缓冲流读写的过程是什么？

![image-20250120014613466](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250120014613466.png)

​	输入流缓冲区和输出流缓冲区之间通过新建一个空间len进行传递。

​	过程：先依靠基本流将数据读出来，然后交给缓冲流；由于缓冲流的缓冲区大小是8192，所以每次读取8192个字节，放到缓冲区中；然后再将输入流缓冲区中的数据交给输出流缓冲区，然后再利用基本流将数据写入硬盘。在操作代码时，len的作用主要是：在两个缓冲区中传递数据。将输入流缓冲区的数据读取然后写到输出流缓冲区中，等待输出流缓冲区满了，再依靠基本流写到硬盘上。如果输入流缓冲区的数据读取不到，则重新从硬盘上读取8192个字节进入到输入流缓冲区中，继续利用len进行数据传递。

### 2.字符缓冲流

我们知道，字符流的基本流底层是有缓冲区的，所以在效率这一块效果不是特别明显，但是这并不代表不重要，因为我们应该主要学字符缓冲流的两个特有方法。

#### 2.1 字符缓冲输出流BufferedWriter

1.构造方法：BufferedWriter(Writer w)

2.常用方法：和FileWriter一样

3.特有方法：newLine() 换行

![image-20250120031011954](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250120031011954.png)

![image-20250120031030118](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250120031030118.png)

#### 2.2 字符缓冲输入流BufferedReader

1.构造方法：BufferedReader(Reader r)

2.常用方法：和FileReader一样

3.特有方法：String readLine()：一次读一行，如果读到结束标记，返回的是null

![image-20250120151849050](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250120151849050.png)

### 3.字符编码

​	计算机中存储的信息都是二进制数表示的，而我们在屏幕上看到的数字、英文、标点符号、汉字等字符是二进制数转换之后的结果。按照某种规则，将字符存储到计算机中，称为编码。反之，将存储在计算机中的二进制数按照某种规则解析显示出来，称为解码。比如说，按照A规则存储，同样按照A规则解析，那么就能显示正确的文本符号。反之，按照A规则存储，再按照B规则解析，就会导致乱码现象。

​	字符编码character Encoding：就是一套自然语言的字符与二进制数之间的对应规则。

#### 3.1 字符集

​	字符集也叫编码表。是一个系统支持的所有字符的集合，包括各国家文字、标点符号、图形符号、数字等。

![image-20250120163349385](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250120163349385.png)

#### 3.2 字符集分类

![image-20250120163455992](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250120163455992.png)

![image-20250120163901925](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250120163901925.png)

​	注意：UTF-8一个汉字占用3个字节，GBK一个汉字占用2个字节。

### 4. 转换流InputStreamReader

1.介绍：字节流读取中文在编码一致的情况下，也不能边读边看，因为如果字节读不准、读不全，输出的内容有可能出现乱码，所以学了字符流读取解决了边读边看的问题。但是，如果编码不一致，字符流读取文本文档中的内容也有可能出现乱码。

2.概述：是字节流通向字符流的桥梁，读数据

3.构造方法：InputStreamReader(InputStream in, String charsetName)

​	charsetName：指定编码格式，不区分大小写

4.作用：可以直接指定编码，按照指定的编码读取内容。

5.用法：基本用法和FileReader一样。

6.使用：

不指定编码，即使用FileReader时，

![image-20250120231509902](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250120231509902.png)

输出：![image-20250120231453631](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250120231453631.png)



指定编码，即使用InputStreamReader时，

![image-20250120231959748](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250120231959748.png)

输出：![image-20250120232014544](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250120232014544.png)

### 5.转换流OutputStreamWriter

1.概述：是字符流通向字节流的桥梁

2.构造方法：OutputStreamWriter(OutputStream out, String charsetName)

3.作用：按照指定的编码存数据

4.用法：基本用法和FileWriter一样

5.使用：

不指定编码，即使用FileWriter时，

![image-20250120233906175](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250120233906175.png)

输出：![image-20250120233842807](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250120233842807.png)



指定编码，即使用OutputStreamWriter时，

![image-20250120234445476](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250120234445476.png)

### 6.序列化流

#### 6.1 介绍

1.作用：读写对象

2.两个对象：

​	a.ObjectOutputStream：序列化流，写对象

​	b.ObjectInputStream：反序列化流，读对象

<img src="C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250120234909202.png" alt="image-20250120234909202" style="zoom:80%;" />

3.注意：

​	我们将对象序列化到文件中，打开文件时看不懂是正常现象。我们只需将这些看不懂的内容成功读取即可。

​	应用场景：玩游戏时会对游戏进度存档，那么退出的时候人物就是一个对象，人物的装备和属性就变成了成员变量存入文件中，当再次打开游戏时，直接从文件中将这些人物对象读回来，将对象的属性和装备进行还原。

#### 6.2 序列化流ObjectOutputStream

1.作用：写对象

2.构造方法：ObjectOutputStream(OutputStream out)

3.方法：writeObject(Object obj)：写对象

4.注意：想要将对象序列化到文件中，不能随意序列化，被序列化的对象需要实现Serializable接口

![image-20250121175421201](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250121175421201.png)

![image-20250124024359038](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250124024359038.png)

#### 6.3 反序列化流ObjectInputStream

1.作用：读对象

2.构造方法：ObjectInputStream(InputStream in)

3.方法：Object readObject()

![image-20250121180006799](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250121180006799.png)

结果：

![image-20250121180017818](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250121180017818.png)

#### 6.4 不序列化

关键字：transient	在成员变量中加上关键字即可保证该成员变量不被序列化。

​	例如Person类中，private transient Integer age;

#### 6.5 序列号冲突问题

问题描述：序列化之后，修改源码，修改完之后没有重新序列化，而是直接反序列化，则会出现序列号冲突问题：InvalidClassException异常。

![image-20250122023941523](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250122023941523.png)

解决：将序列号定死，后面不管怎么修改源码，序列号都不变。

​	在被序列化的对象中加上一个public static final long 的变量，并为其赋值。

![image-20250122024344816](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250122024344816.png)

将一个对象实现一个序列化接口，我们将来才能让这个对象变成二进制在网络上传输。

#### 6.6 循环反序列化问题

如果序列化多个对象，每个person对象都要手动进行一次反序列化，如下图所示。

![image-20250122024700983](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250122024700983.png)

这种方式过于麻烦，因此使用for循环进行反序列化。

![image-20250122024928497](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250122024928497.png)

注意：如果循环读取的次数如果和存储对象的个数不对应，就会出现EOFException异常。

​	解决：

​		a.创建一个集合，存储多个Person对象；

​		b.将对象存储到集合中，由序列化Person对象改为序列化集合对象，因此在反序列化时只需要将集合反序列化即可

​		c.集合可用list.size()返回Person对象个数，解决循环读取次数问题。	

### 7.打印流

#### 7.1 PrintStream基本使用

1.构造方法：PrintStream(String fileName)

2.常用方法：

​	println()：原样输出，自带换行效果

​	print()：原样输出，不带换行效果

![image-20250122033456818](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250122033456818.png)

3.改变流向

​	a.什么叫改变流向：

​		System.out.println()：本身是输出到控制台

​		改变流向：可以让输出语句从控制台上输出改变成向指定文件输出。

​	2.方法：System中的方法：

​		static void setOut(PrintStream out)：改变流向，让输出语句从控制台输出转移到指定文件中。

![image-20250122035700320](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250122035700320.png)

​	使用场景：可以将输出的内容以及详细信息放到日志文件中，永久保存。以后我们希望将输出的内容永久保存，但是输出语句会将结果输出到控制台上，控制台是临时显示，如果有新的程序运行，新程序的运行结果会覆盖之前的结果，这样无法达到永久保存，到时候我们想看看之前的运行结果信息就看不到了，所以我们需要将输出的结果保存到日志文件中就可以使用setOut改变流向。

#### 7.2 打印流完成续写

构造方法：PrintStream(OutputStream out)：可以依靠OutputStream的续写功能完成打印流续写。

![image-20250122041606891](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250122041606891.png)

### 8.Properties集合

回顾：

​	![image-20250122041824200](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250122041824200.png)

![image-20250122232513626](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250122232513626.png)

创建配置文件：

​	1.在模块下右键-->选择file，取名为xxxx.properties

​	2.在xxxx.properties文件中写配置数据

​		a.key和value都是key=value形式

​		b.key和value都是String形式，但是不要加双引号

​		c.每个键值对写完之后，需要换行再写下一对

​		d.键值对之间最好不要有空格（空格可以有，但是不建议写）

​		e.键值对中建议不要使用中文（中文可以有，但是中文直接读取会乱码，需要转换流转码）

![image-20250122232950580](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250122232950580.png)

![image-20250122233028054](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250122233028054.png)

输出：

​	![image-20250122233058928](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250122233058928.png)

### 9.CommonsIO工具类

1.介绍

​	IO技术开发中，代码量很大，而且代码的重复率较高。如果我们要遍历目录，拷贝目录就需要使用方法的递归调用，也增大了程序的复杂度。因此出现了IO流工具类CommonsIO，大大简化了IO开发。

2.添加第三方jar包

![image-20250122233854141](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250122233854141.png)

3.工具包的使用

1.IOUtils类

​	静态方法：IOUtils.copy(InputStream in, OutputStream out)：传递字节流，实现文件复制。

​	静态方法：IOUtils.closeQuietly(任意流对象)：悄悄的释放资源，自动处理close()方法抛出的异常。

![image-20250122235205839](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250122235205839.png)

![image-20250122235545967](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250122235545967.png)

2.FileUtils类

​	静态方法：FileUtils.copyDirectoryToDirectory(File src, File dest)：传递File类型的目录，进行整个目录的复制，自动进行递归遍历。

​		参数：

​		src：要复制的文件夹路径

​		dest：要将文件夹粘贴到哪里去

​	静态方法：writeStringToFile(File file, String str)：写字符串到文本文件中。

​	静态方法：String readFileToString(File file)：读取文本文件，返回字符串。

### 10.总结

![image-20250123001546498](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250123001546498.png)



## 二十六、网络编程

概述：

​	在网络通信协议下，不同计算机上运行的程序，进行数据传输。比如：通信、视频通话、网游、邮件等。

​	只要计算机之间通过网络进行数据传输，就有网络编程的存在。

### 1.软件架构

![image-20250123001743966](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250123001743966.png)

![image-20250123002010326](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250123002010326.png)

### 2.服务器概念

1.概述：安装了服务器软件的计算机

2.服务器软件：Tomcat等

![image-20250123030445893](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250123030445893.png)

### 3.通信三要素

1.IP地址

![image-20250123030624160](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250123030624160.png)

2.协议

![image-20250123030904559](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250123030904559.png)

3.端口号

![image-20250123031103323](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250123031103323.png)

### 4.UDP协议编程

1.DatagramSocket：好比寄快递找的快递公司

2.DatagramPacket：好比快递公司打包

#### 4.1 发送端步骤

1.创建DatagramSocket对象（快递公司）

​	a.空参：端口号从可用的端口号中随机一个使用

​	b.有参：自己指定

2.创建DatagramPacket对象，将数据进行打包

​	a.要发送的数据	byte[]

​	b.指定接收端的IP,InetAddress ip = InetAddress.getByName("127.0.0.1")

​	c.指定接收端的端口号

3.发送数据

4.释放资源

![image-20250124015035684](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250124015035684.png)

​	注意：发送端在没有接收端的情况下，不会报错，因为UDP协议是面向无连接的协议，不管有没有接收端都照发不误。

#### 4.2 接收端步骤

1.创建DatagramSocket对象，指定服务端的端口号

2.接收数据包

3.解析数据包

4.释放资源

![image-20250124020002791](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250124020002791.png)

运行结果：

![image-20250124020017337](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250124020017337.png)

### 5.TCP协议编程

![image-20250124021206458](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250124021206458.png)

#### 5.1 客户端步骤

1.创建Socket对象，指明服务端的ip以及端口号

2.调用Socket对象中的getOutputStream，向服务端发送请求

3.调用Socket对象中的getInputStream，读取服务端响应回来的数据

4.关流

![image-20250124022005176](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250124022005176.png)

#### 5.2 服务端步骤

1.创建ServerSocket对象，设置端口号

2.调用ServerSocket对象中的accept方法，等待客户端连接，返回Socket对象（服务端监听）

3.调用Socket对象中的getInputStream，读取客户端发送过来的数据

4.调用Socket对象中的getOutputStream，用于客户端响应数据

5.关闭资源

![image-20250124023126559](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250124023126559.png)

​	运行结果：

​	客户端：

![image-20250124023238944](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250124023238944.png)

​	服务端：

![image-20250124023257634](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250124023257634.png)

### 6.文件上传

![image-20250124030151995](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250124030151995.png)

#### 6.1 文件上传客户端以及服务端的实现

1.代码实现

客户端：

![image-20250124032548165](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250124032548165.png)

注意：代码有问题

服务端：

![image-20250124032612641](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250124032612641.png)

注意：代码有问题

问题：服务端一直卡在while循环中，无法向下继续执行。原因：客户端执行while循环的时候，如果文件读取完成，则下一次读取就会读到结束标识符，返回-1，从而退出while循环；但是客户端并没有给服务端传输结束标识符，导致服务端一直在等待客户端的文件传输，造成阻塞。

解决：socket.shutDownOutput()：可以理解为给对方一个结束标记

客户端（修改）：

![image-20250124033317271](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250124033317271.png)

2.客户端接收传递的图片时，会覆盖上一个同名的文件。

​	解决：将接收路径写活，即随机数取名，使用UUID工具类，UUID.randomUUID()会生成一个十六进制的随机数，再用toString方法将其转换成String类型。

服务端（修改）：

![image-20250124172827843](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250124172827843.png)

#### 6.2 文件上传服务端实现多线程

服务端：

![image-20250124174228334](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250124174228334.png)

最后需要对流对象的异常进行处理，过于麻烦，因此自定义一个工具类进行改进。

服务端（改进）

![image-20250124174747788](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250124174747788.png)

![image-20250124174818594](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250124174818594.png)



## 二十七、正则表达式

### 1.概念

1.概述：正则表达式是一个具有特殊规则的字符串

2.作用：校验，比如：校验手机号、身份证号、密码、用户名等。

3.String中有一个校验正则的方法：

​	boolean matches(String regex)：校验字符串是否符合指定的regex规则

4.比如：校验QQ号（不能以0开头，必须都是数字，必须是5-15位的）

例：

![image-20250125003523725](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250125003523725.png)

含义：第一位规定必须是1-9之间任意一个数，后面有4~14个任意0-9之间的数

### 2.基本使用

#### 2.1 字符类

java.util.regex.Pattern：正则表达式的编译表示形式。

​	正则表达式-字符类：[]表示一个区间，范围可以自己定义

​	语法示例：

​	1.[abc]：代表a或者b或者c字符中的任意一个。

​	2.[[^^abc]]：代表除了a、b、c以外的任意一个字符。

​	3.[a-z]：代表a-z的所有小写字符中的一个。

​	4.[A-Z]：代表A-Z的所有大写字符中的一个。

​	5.[0-9]：代表0-9之间的某一个数字字符。

​	6.[a-zA-Z0-9]：代表a-z或A-Z或0-9之间的任意一个字符。

​	7.[a-dm-p]：a-d或m-p之间的任意一个字符。

![image-20250125011512969](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250125011512969.png)

#### 2.2 逻辑运算符

![image-20250125025019873](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250125025019873.png)

![image-20250125024938928](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250125024938928.png)

#### 2.3 预定义字符

![image-20250125025044580](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250125025044580.png)

![image-20250126033644029](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250126033644029.png)

#### 2.4 数量词

![image-20250126033705637](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250126033705637.png)

![image-20250126033900591](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250126033900591.png)

#### 2.5 分组括号

(abc)：表示abc一起出现，即abc为一组

![image-20250126034123484](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250126034123484.png)

#### 2.6 String类相关

![image-20250126034232685](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250126034232685.png)

代码：

![image-20250126034356301](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250126034356301.png)

输出：

![image-20250126034331332](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250126034331332.png)



## 二十八、jdk新特性

### 1.Lambda表达式

#### 1.1 函数式编程思想

![image-20250127223902765](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250127223902765.png)

#### 1.2 表达式格式

1.定义格式：()->{}

2.解释：

​	()：代表重写方法的参数位置

​	->：代表的是将参数传递到方法体之中

​	{}：代表重写方法的方法体

![image-20250127224538937](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250127224538937.png)

​	可修改为：

![image-20250127224604110](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250127224604110.png)

#### 1.2 表达式使用前提

1.必须是函数式接口做方法传递

2.函数式接口：有且只有一个抽象方法的接口（例如Runnable接口中只有一个run方法，且为抽象方法），可以使用@FunctionalInterface注解去检测是否是函数式接口。

自己定义一个函数式接口USB，并且使用注解检测：

![image-20250127225454216](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250127225454216.png)

如果定义两个抽象方法，注释会报错：

![image-20250127225543774](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250127225543774.png)

#### 1.3 表达式省略规则

1.Lambda表达式怎么写？

​	a.观察是否是函数式接口做方法参数传递

​	b.如果是，考虑使用Lambda表达式

​	c.调用方法，以匿名内部类的形式传递实参

​	d.从new接口开始到重写方法的方法名结束，选中删除，别忘记删除一个右半大括号

​	e.在重写方法的参数后面，方法体的大括号前面，加上箭头 ->

![image-20250127230116990](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250127230116990.png)

![image-20250127230128958](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250127230128958.png)

2.省略规则：

​	a.重写方法的参数类型可以删除

​	b.如果重写方法只有一个参数，所在的小括号可以删除

​	c.如果方法体中只有一句话，那么所在的大括号以及语句后的分号可以删除

​	d.如果方法体中只有一句话并且带return，那么所在的大括号、语句后的分号、return都可以删除

​	改进：

![image-20250127234039293](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250127234039293.png)

例：

![image-20250127235043607](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250127235043607.png)

### 2.函数式接口

1.函数式接口：有且只有一个抽象方法的接口

2.检测：@FunctionalInterface

#### 2.1 Supplier

1.java.util.function.Supplier<T>接口，它意味着“供给”，即：我们想要什么就给什么

2.方法：T get()：我们想要什么，get方法就可以返回什么

3.需求：

​	使用Supplier接口作为方法的参数，用Lambda表达式求出int数组中的最大值

![image-20250128000652425](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250128000652425.png)

​	改进：

![image-20250128001017362](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250128001017362.png)

注意：其主要功能是忽视输入数据的格式，统一由supplier的泛型转为同一种格式。例：

![image-20250130220256393](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250130220256393.png)

输出：

![image-20250130220309073](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250130220309073.png)

#### 2.2 Consumer

![image-20250203200134114](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250203200134114.png)

1.java.util.function.Consumer<T>：消费型接口，也就是操作数据

2.方法：void accept(T t)：表示消费一个指定泛型的数据

注意：消费就是操作，至于怎么操作，就要看重写accept方法的方法体

![image-20250204162711356](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204162711356.png)

化简：

![image-20250204162840929](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204162840929.png)

![image-20250204164608817](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204164608817.png)

#### 2.3 Function

1.java.util.function.Function<T, R>：接口用来根据一个类型的数据得到另一个类型的数据

2.方法：R apply(T t)：根据类型T参数获取类型R的结果（类型转换）

例：将整数类型变为字符串类型

![image-20250204164252506](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204164252506.png)

化简：

![image-20250204164411057](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204164411057.png)

![image-20250204164532866](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204164532866.png)

#### 2.4 Predicate

1.java.util.function.Predicate<T>：判断型接口

2.方法：boolean test(T t)：用于判断的方法，返回值为boolean类型

例：判断字符串长度是否为7

![image-20250204165209507](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204165209507.png)

化简：

![image-20250204165327002](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204165327002.png)

### 3.Stream流

1.Stream流中的“流”不是特指的“IO流”，它是一种“流式编程”，是一种编程方式，可以看作是“流水线”。

例：给定一个集合

![image-20250204174353724](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204174353724.png)

​	需求一：筛选出姓张的人

![image-20250204174524424](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204174524424.png)

​		输出：[张三三, 张六六, 张八]

​	需求二：筛选出三个字的张姓人物

![image-20250204174735589](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204174735589.png)

​	需求三：遍历集合，将姓张且名字长度为3的人打印出来

![image-20250204174903799](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204174903799.png)

​	注意：每一步骤都是在之前步骤的基础上完成的，层层递进，这就是流水线。但是这样过于麻烦，所以要用到Stream流。

![image-20250204175724822](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204175724822.png)

​	对每一个需要判断的需求进行filter过滤，对需要遍历的需求进行forEach遍历

化简：

![image-20250204180057062](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204180057062.png)

#### 3.1 Stream流的获取

1.针对集合：Collection中的方法：Stream<E> stream()

![image-20250204180652244](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204180652244.png)

​	输出为地址值，即针对集合的stream没有重写toString方法

2.针对数组：Stream接口中的静态方法：static <T> Stream<T> of(T...values)

![image-20250204180756730](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204180756730.png)

​	输出为地址值，即针对数组的stream没有重写toString方法

#### 3.2 Stream流中的方法

1.forEach（逐一处理、遍历）

​	void forEach(Consumer<? super T> action);

​	注意：forEach方法是一个终结方法，使用完之后，Stream流不能再继续使用。

![image-20250204181114785](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204181114785.png)

![image-20250204181125199](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204181125199.png)

2.count（统计元素个数）

​	注意：count方法也是一个终结方法

![image-20250204181323026](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204181323026.png)

![image-20250204181334022](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204181334022.png)

3.filter（根据条件进行过滤）

​	Stream<T> filter(Predicate<? super T>predicate);

​	注意：返回了一个新的Stream流对象

![image-20250204182755076](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204182755076.png)

​	输出：

![image-20250204182813342](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204182813342.png)

​	化简：

![image-20250204183003372](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204183003372.png)

4.limit（获取stream流对象中的前n个元素）

​	Stream<T> limit(long maxSize)

​	注意：返回一个新的Stream流对象

![image-20250204183047510](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204183047510.png)

​	输出：

![image-20250204183100218](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204183100218.png)

5.skip（跳过stream流对象的前n个元素）

​	Stream<T> skip(long n)

​	注意：返回一个新的Stream流对象

![image-20250204183136257](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204183136257.png)

输出：

![image-20250204183151164](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204183151164.png)

6.concat（合并流对象）

​	static <T> Stream<T> concat(Stream<? extends T> a, Stream<? extends T> b)

​	注意：返回一个新的Stream流对象

![image-20250204183235558](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204183235558.png)

​	输出：

![image-20250204183249656](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204183249656.png)

7.collect（把Stream流转成集合）

​	![image-20250204183359642](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204183359642.png)

​	输出：

![image-20250204183412424](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250204183412424.png)

8.dinstinct（元素去重复）

​	Stream<T> distinct()

​	注意：该方法依赖hashCode和equals方法，被去重的元素底层需要重写hashCode和equals方法

![image-20250205011625155](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205011625155.png)

![image-20250205011648819](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205011648819.png)

​	输出：

![image-20250205011703361](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205011703361.png)

9.map（转换Stream流中的数据类型）

​	Stream<R> map(Function<T,R> mapper)

![image-20250205012447593](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205012447593.png)

​	输出：

![image-20250205012513044](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205012513044.png)

### 4.方法引用

#### 4.1 介绍

1.概述：引用方法

2.什么时候引用（使用条件）：

​	a.被引用的方法要写在重写方法里面

​	b.被引用的方法从参数上、返回值上要和所在的重写方法一致，而且引用的方法最好是操作重写方法的参数值

​	c.干掉重写方法的参数；干掉符号 -> ；干掉被引用方法的参数；将被引用方法的.改为::

![image-20250205014049726](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205014049726.png)

输出：

![image-20250205014104061](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205014104061.png)

#### 4.2 对象名--引用成员方法

1.使用对象名引用成员方法

​	格式：对象::成员方法名

2.需求：

​	函数式接口：Supplier

​		Java.util.function.Supplier<T> 接口

​	抽象方法：

​		T get()：用来获取一个泛型参数指定类型的对象数据

​		Supplier接口使用什么泛型，就可以使用get方法获取一个什么类型的数据

![image-20250205014911115](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205014911115.png)

​	输出：

![image-20250205014923330](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205014923330.png)

#### 4.3 类名--引用静态方法

格式：类名::静态成员方法

![image-20250205015701371](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205015701371.png)

​	输出：

![image-20250205015720686](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205015720686.png)

#### 4.4 类--构造引用

1.格式：构造方法名称::new

2.需求：

​	函数式接口：Function

​		java.util.function,Function<T,R>接口

​	抽象方法：

​		R apply(T t)：根据类型T的参数获取类型R的结果，用于类型转换

![image-20250205020630132](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205020630132.png)

​	输出：

![image-20250205020643114](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205020643114.png)

#### 4.5 数组--数组引用

格式：

​	数组的数据类型[]::new

​	int[]::new	创建一个int型的数组

​	double[]::new	创建一个double型的数组

![image-20250205021219155](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205021219155.png)

![image-20250205021229459](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205021229459.png)

### 5.jdk8以后新特性

#### 5.1 接口的私有方法

![image-20250205021740051](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205021740051.png)

例：

![image-20250205021943175](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205021943175.png)

![image-20250205022023371](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205022023371.png)

![image-20250205022048693](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205022048693.png)

#### 5.2 钻石操作符与匿名内部类集合

​	自jdk9之后，我们能够与匿名内部类共同使用钻石操作符<>（也就是泛型），即匿名实现类也支持类型自动推断。

例：

![image-20250205022431143](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205022431143.png)

​	可以化简为：

![image-20250205022506357](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205022506357.png)

​	也就是把泛型中的数据类型删去，虚拟机可以自行推断该数据类型，因此不会再报错。

#### 5.3 try_catch升级

![image-20250205022709942](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205022709942.png)

![image-20250205022749632](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205022749632.png)

![image-20250205022820933](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205022820933.png)

​	修改后：

![image-20250205022936488](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205022936488.png)

#### 5.4 局部变量类型自动推断

![image-20250205023031685](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205023031685.png)

![image-20250205023205420](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205023205420.png)

#### 5.5 switch表达式

![image-20250205023251864](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205023251864.png)

用箭头省略break：

![image-20250205023546823](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205023546823.png)

使用yield接收，传入switch语句前定义的变量：

![image-20250205023826730](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205023826730.png)

#### 5.6 文本块

格式：三引号 （内容） 三引号

![image-20250205023957891](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205023957891.png)

#### 5.7 instanceof模式匹配

![image-20250205024236701](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205024236701.png)

原来：

![image-20250205024216933](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205024216933.png)

改进：

![image-20250205024302633](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205024302633.png)

#### 5.8 Record类

![image-20250205024402504](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205024402504.png)

#### 5.9 密封类

![image-20250205024714107](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205024714107.png)

即：让谁继承，谁才能继承，不在关键字里面的类都不能继承



## 二十九、反射

### 1.Class对象

class对象：class文件对应的对象

class类：描述class对象的类叫作class类

![image-20250206012002584](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206012002584.png)

### 2.反射介绍

1.概述：解剖class对象的一个技术

2.问题：能解剖出class对象的什么？

​	a.解剖出成员变量：赋值

​	b.解剖出成员方法：调用

​	c.解剖出构造方法：创建对象

3.用反射的好处：所有代码都没有写死，让代码的灵活性更好，变得更通用。

4.怎么学反射？

​	a.将反射看成是一套API来学

​	b.通过案例体会反射的好处

5.问题：反射开始时要干什么？	获取class对象

### 3.获取Class对象

1.法一：调用Object中的getClass方法：

​	Class <?> getClass()

2.法二：不管是基本类型还是引用类型，虚拟机都提供一个静态成员：class，因此直接 类名.class

3.法三：Class类中的静态方法：

​	static Class<?> forName(String className)

​		className：传递的是类的全限定名（即 包名.类名）

![image-20250206014127588](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206014127588.png)

​	输出：

![image-20250206014139642](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206014139642.png)

​	注意：最通用的是方式三forName，因为参数为String，可以和properties文件结合使用；最常用的是方式二类名.class，因为方便。

### 4.反射构造方法

#### 4.1 获取public构造

**1.获取所有public类型的构造方法**

​	class类中的方法：

​		Constructor<?>[] getConstructors()：获取所有的public构造，并返回一个数组

​	如图所示，Person类中的public类型的构造方法全部输出，而private类型的构造方法不会输出

![image-20250206195106394](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206195106394.png)

![image-20250206195120159](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206195120159.png)

![image-20250206195128750](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206195128750.png)

**2.获取public类型的无参构造方法**

​	获取空参构造，使用Class类中的方法：

​		Constructor<T> getConstructor(Class<?> ... parameterTypes)：获取指定的public类型的构造方法

​			parameterTypes：参数类型；

​			... ：可变参，可以传递0个或多个参数

​		a.如果获取的是空参构造：参数不用写

​		b.如果获取的是有参构造：参数就写参数类型的class对象

![image-20250206200035795](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206200035795.png)

![image-20250206200048158](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206200048158.png)

**3.获取public类型的无参构造方法**

见 4.2：3.利用反射获取public形式的有参构造并创建对象

#### 4.2 public构造创建对象

**1.利用构造方法创建对象**

​	使用Constructor类中的方法：

​	T newInstance(Object ... initargs)：创建对象

​		initargs：传递的是构造方法的实参

​	如果根据无参构造new对象，则initargs为空；如果根据有参构造new对象，initargs就传递实参

![image-20250206201254045](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206201254045.png)

![image-20250206201307290](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206201307290.png)

**2.利用空参构造创建对象的快捷方式**

​	使用Class类中的方法（只适用于无参构造方法）：

​	T newInstance()：根据空参构造创建对象（与上面相比，少了一步获取构造方法constructor）

​	注意：该方法有使用前提，被反射的类中必须有public形式的无参构造方法

![image-20250206204144152](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206204144152.png)

![image-20250206204153546](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206204153546.png)

**3.利用反射获取public形式的有参构造并创建对象**

​	同	4.2 构造创建对象	的两张图片	根据有参构造创建对象

#### 4.3 获取private构造

**1.利用反射获取public、private类型的所有构造方法**

​	Constructor<?>[] getDeclaredConstructors()：获取所有构造方法，包括private

​	例：如图所示，public的构造方法和private的构造方法都能拿到

![image-20250206205151643](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206205151643.png)

![image-20250206205206634](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206205206634.png)

**2.利用反射获取public、private类型的指定构造方法**

​	Constructor<T> getDeclaredConstructor(类<?> ... parameterTypes)：获取指定构造方法，包括private

​		parameterTypes：参数类型的class对象，即String.class、Integer.class等

​	例：只拿带有String参数的构造方法

![image-20250206205537438](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206205537438.png)

![image-20250206205550243](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206205550243.png)

#### 4.4 private构造创建对象

利用该构造方法创建对象：**会报错**

![image-20250206205837254](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206205837254.png)

![image-20250206205852507](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206205852507.png)

​	原因：该构造方法的类型是private，无法访问；解决：使用setAccessible()方法

Constructor有一个父类叫做AccessibleObject，里面有一个方法：

​	void setAccessible(boolean flag)：修改访问权限

​		flag为true时：解除私有权限

![image-20250206210521334](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206210521334.png)		

![image-20250206210531413](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206210531413.png)

### 5.反射成员方法

#### 5.1 获取public方法

**1.利用反射获取所有public成员方法**

Class类中方法：

​	Method[] getMethods()：获取所有public类型的方法，包括父类中的public方法，返回一个数组

![image-20250206231312746](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206231312746.png)

![image-20250206231331598](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206231331598.png)

​	输出：

![image-20250206231353488](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206231353488.png)

​	注意：不仅能获取到当前类，也能获取到父类。如图既有Person类的方法，也有Object类的方法。

**2.利用反射获取指定public成员方法**

Class类中的方法：

​	Method getMethod(String name, Class<?> ... parameterTypes)：获取指定的public的成员方法

​		name：指定要获取的方法名

​		parameterType：方法参数类型的class对象（防止由于方法的重载而出现查找错误的现象）

![image-20250206235318845](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206235318845.png)

​	![image-20250206235334017](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206235334017.png)

#### 5.2 调用public方法

使用invoke方法，该方法是Method对象中的方法：

​	Object invoke(Object obj, Object ... args)：调用obj对象中的某个方法

​		obj：根据构造方法而创建出来的对象

​		args：方法实参，如果有参数则传递实参，否则为空

​		返回值：Object，接收被调用方法的返回值，如果没有返回值（void），则不用接收

​	例一：使用一个有参方法

![image-20250207000044478](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207000044478.png)

​	输出：

![image-20250207000109680](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207000109680.png)

​	例二：使用一个无参方法

![image-20250207011206642](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207011206642.png)

​	输出：

![image-20250207011218668](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207011218668.png)

#### 5.3 获取private方法

利用反射获取私有private成员方法

1.Method[] getDeclaredMethods()：获取public、private类型的所有成员方法，**包括private**

2.Method getDeclaredMethod(String name, 类<?> ... parameterTypes)：获取public、private类型的指定成员方法，**包括private**

​	name：指定要获取的方法名

​	parameterTypes：方法参数类型的class对象（防止由于方法的重载而出现查找错误的现象）

#### 5.4 调用private方法

调用该私有方法：会报错

![image-20250207015059584](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207015059584.png)

![image-20250207015201486](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207015201486.png)

​	输出：

![image-20250207015223529](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207015223529.png)

​	原因：该私有方法的类型是private，无法访问；解决：使用setAccessible()方法

Method有一个父类叫做AccessibleObject，里面有一个方法：

​	void setAccessible(boolean flag)：修改访问权限

​		flag为true时：解除私有权限

![image-20250207015644364](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207015644364.png)

​	输出：

![image-20250207015656078](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207015656078.png)

### 6.反射成员变量

#### 6.1 获取public属性

**1.利用反射获取所有public属性**

Class类中方法：

​	Field[] getFields()：获取所有public类型的属性，返回一个数组

![image-20250207021158595](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207021158595.png)

![image-20250207021214276](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207021214276.png)

![image-20250207021225555](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207021225555.png)

**2.利用反射获取指定public成员属性**

Class类中方法：

​	Field getField(String name)：获取指定的public的属性

例：见 6.2 使用public属性

#### 6.2 使用public属性

Field类中的方法：

​	1.void set(Object obj, Object value)：为属性赋值，相当于JavaBean中的set方法

​		obj：对象

​		value：赋予的值

​	2.Object get(Object obj)：获取属性值

​		obj：对象		

![image-20250207023759458](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207023759458.png)

​	输出：10

#### 6.3 获取private属性

利用反射获取私有private属性

1.Field[] getDeclaredFields()：获取public、private类型的所有属性，**包括private**

![image-20250207021342988](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207021342988.png)

![image-20250207021357561](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207021357561.png)

2.Field getDeclaredField(String name)：获取public、private类型的指定属性，**包括private**

​	name：指定要获取的属性名

见 6.4 使用private属性

#### 6.4 使用private属性

使用该私有属性：会报错

![image-20250207024158120](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207024158120.png)

​	输出：

![image-20250207024235263](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207024235263.png)

原因：该私有属性的类型是private，无法访问；解决：使用setAccessible()方法

Field有一个父类叫做AccessibleObject，里面有一个方法：

​	void setAccessible(boolean flag)：修改访问权限

​		flag为true时：解除私有权限

![image-20250207024458544](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207024458544.png)

​	输出：

![image-20250207024535284](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207024535284.png)

### 7.总结

使用反射的步骤：

1.使用 类名.class，通过Person.class，返回一个Class类型对象aClass

2.使用getConstructor/getDeclaredConstructor方法，通过aClass.getConstructor，返回一个构造方法constructor

3.使用newInstance方法，通过constructor.newInstance，返回一个1中该类名的对象（如果构造方法是无参，则可以使用快捷方式直接创建一个该类名对应的对象）

4.使用getMethod/getDeclaredMethod方法，通过aClass.getMethod，返回一个成员方法method

5.使用invoke方法，通过method.invoke（注意参数中要有2的constructor），返回一个该方法的返回值（如果该方法的返回值为void，则使用反射时同样不返回）

6.使用getField/getDeclaredField方法，通过aClass.getField，返回一个属性field

7.使用get/set方法，通过field.set（注意参数中要有2的constructor），为该属性赋值；通过field.get（注意参数中要有2的constructor），读取该赋值

### 8.编写框架

![image-20250207032136105](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207032136105.png)

步骤：
![image-20250207034553753](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207034553753.png)

![image-20250207034723519](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207034723519.png)

![image-20250207185257614](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207185257614.png)



## 三十、注解

### 1.注解介绍

1.引用数据类型：类 数组 接口 枚举 注解

2.作用：

​	说明：对代码进行说明，生成doc文档（API文档）

​	检查：检查代码是否符合条件

​	分析：对代码进行分析，起到了代替配置文件的作用

3.JDK中的注解：

​	@Override：检查此方法是否为重写方法

​	@Deprecated：将方法标记为过时，即方法名添加横线标记，表示不影响使用但是不推荐使用

​	@SuppressWarnings：消除警告	例：@SuppressWarnings("all")

![image-20250207221652461](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207221652461.png)

4.定义：

IDEA中创建：

![image-20250208010118391](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250208010118391.png)

定义注解：public @interface 注解名{}

定义属性（目的是增强注解的作用）：

​	数据类型 属性名()：此属性没有默认值，需要在使用注解的时候为其赋值

​	数据类型 属性名() default 赋值：此属性有默认值，如果有需要，还可以二次赋值

​	问题：注解中能定义什么类型的属性？

​		a.8种基本数据类型

​		b.String类型、class类型、枚举类型、注解类型

​		c.以上类型的一维数组

![image-20250207232957779](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207232957779.png)

5.注意：注解属性本质上是抽象方法，但是我们按照成员属性来理解，因为使用注解属性的时候需要等号来为其赋值。

### 2.注解使用

1.注解的使用说白了就是为注解中的属性赋值

2.使用位置上：在类上使用、方法上使用、成员变量上使用、局部变量上使用、参数位置使用等

3.使用格式：

​	a.@注解名(属性名 = 值, 属性名 = 值...)

​	b.如果属性中有数组：@注解名(属性名 = {元素1, 元素2...} )

![image-20250207233001976](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207233001976.png)

![image-20250207233011204](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207233011204.png)

​	其中，count属性有默认值，因此可以不用在注解中赋值

4.注意事项：

​	a.空注解可以直接使用（空注解就是注解中没有任何的属性）

​	b.不同的位置可以使用一样的注解，但是相同的位置不能使用一样的注解

​	例：相同的位置不能使用一样的注解

![image-20250207233558519](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207233558519.png)

​	改正：不同的位置可以使用一样的注解

![image-20250207233635918](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207233635918.png)

​	c.使用注解时，如果此注解中有属性，注解中的属性一定要赋值，如果有多个属性，用逗号隔开；如果注解中的属性有数组，则用大括号{}

​	d.如果注解中的属性值有默认值，那么就没有不需要重新赋值，反之则必须赋值

​	e.如果注解中只有一个属性，并且属性名叫**value**，那么使用注解的时候，属性名不用写，直接写值（包括单个类型，还包括数组）

​	例：

![image-20250207233904287](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207233904287.png)

![image-20250207233917209](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250207233917209.png)

### 3.注解解析

注解的解析：说白了就是将注解中的属性值获取出来

1.注解解析涉及到的接口：AnnotatedElement接口

​	实现类：AccessibleObject，Class，Constructor，Field，Method，Package，Parameter

2.解析思路：先判断指定位置上有没有使用指定的注解，如果有，获取指定的注解，再获取注解中的属性值

​	a.boolean isAnnotationPresent(Class<? extends Annotation> annotationClass)

​		判断指定位置上有没有指定的注解，比如：判断BookShelf上有没有@Book注解

​		先获取到BookShelf的class对象（参考反射），再用class对象调用isAnnotationPresent方法，其中参数为指定的注解.class		

```
Class<BookShelf> aClass = BookShelf.class;
boolean iap = aClass.isAnnotationPresent(Book.class);
```

​	b.getAnnotation(Class<T> annotationClass)

​		如果有指定注解，则获取该注解，比如：获取BookShelf上的Book注解

```
Class<BookShelf> aClass = BookShelf.class;
boolean iap = aClass.isAnnotationPresent(Book.class);
//如果结果为true，则证明有该注解
if (iap) {
    //返回值类型为获取的注解类型
    Book book = aClass.getAnnotation(Book.class);
}
```

![image-20250208000916697](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250208000916697.png)

![image-20250208000926035](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250208000926035.png)

![image-20250208000938693](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250208000938693.png)

​	问题：test01中，b为false，即解析失败。

​	原因：代码是在内存中执行的，但是@Book没有在内存中出现，即@Book没有进内存

​	解决：元注解

### 4.元注解使用

1.概述：元注解就是管理注解的注解，其本身也是一种注解

2.问题：从哪些方面管理？

​	a.控制注解的使用位置：控制注解是否能在类上、方法上、构造上等地方使用

​	b.控制注解的生命周期（即加载位置）：控制注解是否能在源码中、Class文件中、内存中出现

3.使用：

​	a.@Target：控制注解的使用位置

​		属性：ElementType[] value()	ElementType是一个枚举，里面的成员可以类名直接调用

​		ElementType中的成员：

​			TYPE：控制注解能使用在类上

​			FIELD：控制注解能使用在属性上

​			METHOD：控制注解能使用在方法上

​			PARAMETER：控制注解能使用在参数上

​			CONSTRUCTOR：控制注解能使用在构造上

​			LOCAL_VARIABLE：控制注解能使用在局部变量上

![image-20250208005049988](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250208005049988.png)

​		表示该注解只能用在类上和方法上。另外：如果不写@Target，则没有限制，即该注解可以放在任意位置。

​	b.@Retention：控制注解的生命周期（加载位置）

​		属性：RetentionPolicy value()	RetentionPolicy value()是一个枚举，里面的成员可以类名直接调用

​		RetentionPolicy中的成员：

​			SOURCE：控制注解能在源码中出现（默认存在）

​			CLASS：控制注解能在class文件中出现

​			RUNTIME：控制注解能在内存中出现

​		解决3中的问题：在@Book的注解代码上加上@Retention使该注解在内存中出现，即把@Book加载到内存中

![image-20250208005601417](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250208005601417.png)

​		输出：

![image-20250208005723411](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250208005723411.png)



## 三十一、补充

### 1.设计模式

![image-20250126034640708](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250126034640708.png)

#### 1.1 模板方法设计模式

模板方法模式：定义一个操作中的算法的骨架，而将一些步骤延迟到子类中，明确了一部分功能，而另一部分功能不明确，需要延伸到子类中实现。

例：饭店中吃饭：点菜、吃菜和买单三个步骤。点菜和买单基本上是一致的，但是吃菜不同，吃法也不同。明确了一部分功能而另一部分功能不明确。

#### 1.2 单例模式

1.目的：单（一个）例（实例，对象）

​	让一个类只产生一个对象，供外界使用

2.分类：

​	a.饿汉式：迫不及待地需要对象，所以对象需要快速的new出来

​	b.懒汉式：不着急要对象，什么时候使用就什么时候new

##### 1.2.1 饿汉式

![image-20250127004143156](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250127004143156.png)

##### 1.2.2 懒汉式

线程不安全：

![image-20250127012843450](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250127012843450.png)

改进（线程安全）：

![image-20250127013337586](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250127013337586.png)

### 2.Lombok

1.作用：简化JavaBean开发

2.使用：

​	a.下载插件（idea2022及之后版本不用下载，软件自带）

​	b.导入lombok的jar包

​	c.修改设置

![image-20250127014505552](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250127014505552.png)

#### 2.1 lombok介绍

Lombok通过增加一些处理程序，可以让JavaBean变得更加简洁、快速。

Lombok能以注解形式来简化Java代码，提高开发效率。开发中经常需要写的JavaBean，都需要花时间去添加相应的getter\setter，也许还要去写构造器、equals等方法，而且需要维护。

Lombok能通过注解的方式，在编译时自动为属性生成构造器、getter\setter、equals、hashcode、toString方法。出现的神奇就是在源码中没有getter和setter方法，但是在编译的时候生成的字节码文件中有getter、setter方法。这样就省去了手动重建这些代码的麻烦，使代码看起来更简洁些。

#### 2.2 lombok常用注解

1.@Getter\@Setter

​	作用：生成成员变量的get和set方法。

​	位置：写在成员变量上，指对当前成员变量有效；写在类上，则对所有成员变量有效。

​	注意：静态成员变量无效。

![image-20250127015137786](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250127015137786.png)

![image-20250127015150150](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250127015150150.png)

2.@ToString

​	作用：生成toString方法。

​	位置：注解只能写在类上。

3.@NoArgsConstructor/@AllConstructor

​	@NoArgsConstructor：无参数构造方法。

​	@AllArgsConstructor：满参数构造方法。

​	位置：注解只能写在类上。

![image-20250127015847471](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250127015847471.png)

![image-20250127015909521](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250127015909521.png)

​	输出：

![image-20250127015920873](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250127015920873.png)

4.@EqualsAndHashCode

​	作用：生成hashCode和equals方法。

​	位置：注解只能写在类上。

5.@Data

​	作用：生成get/set、toString、hashCode、equals、无参数构造方法

​	位置：注解只能写在类上。

![image-20250127020113557](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250127020113557.png)

![image-20250127020125622](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250127020125622.png)

### 3.Junit

#### 3.1 介绍

1.概述：Junit是一个单元测试框架，可以代替main方法去执行其他的方法

2.作用：单独执行一个方法，测试该方法是否有误（是否能跑通）

3.注意：Junit是第三方工具，所以使用之前需要导入jar包

#### 3.2 基本使用

1.导入Junit的jar包

2.定义一个方法，在方法上写注解：@Test

3.执行方法：

​	a.点击该方法左边的绿色按钮，点击run执行（单独执行一个指定的方法）

![image-20250205182004096](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205182004096.png)

​	b.如果想要执行所有带有@Test的方法，则需要点击类名左边绿色按钮，再点击run执行（执行当前类中所有带有@Test的方法）

![image-20250205182027205](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205182027205.png)

#### 3.3 注意事项

1.@Test不能修饰静态static方法

2.@Test不能修饰带参数的方法

3.@Test不能修饰带返回值的方法

#### 3.4 相关注解

1.@Before：在@Test之前执行，有多少个@Test执行，@Before就执行多少次。（作用：初始化一些数据）

2.@After：在@Test之后执行，有多少个@Test执行，@After就执行多少次。（作用：释放资源）

例：执行add方法

![image-20250205182503835](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205182503835.png)

​	输出：

![image-20250205182542701](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205182542701.png)

例：执行所有方法

​	输出：

![image-20250205182608499](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205182608499.png)

### 4.类加载机制

#### 4.1 类的加载时机

1.new对象

2.new子类对象（new子类对象先初始化父类）

3.执行main方法

4.调用静态成员

5.利用反射去创建class对象

![image-20250205231008187](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250205231008187.png)

#### 4.2 类加载器ClassLoader

1.概述：在jvm中，负责将本地上的class文件加载到内存的对象就叫作类加载器（ClassLoader）

2.分类：

​	BootStrapClassLoader：跟类加载器，C语言实现，程序员是获取不到的；也称为引导类加载器，主要负责Java的核心类加载，比如System、String等，jre/lib/rt.jar下的类都是核心类

​	ExtClassLoader：扩展类加载器，负责jre的扩展目录中的jar包的加载；在jdk中jre的lib目录下的ext目录

​	AppClassLoader：系统类加载器，负责在jvm启动时加载来自java命令的class文件（自定义类），以及classPath环境变量所指定的jar包（第三方jar包）

​	不同的类加载器负责加载不同的类

3.三者的关系（从类加载机制层面）：

​	AppClassLoader的父类加载器是ExtClassLoader，ExtClassLoader的父类加载器是BootStrapClassLoader，但是，他们从代码级别上来看，并没有真正的字父类继承关系，而是有一个共同的父类ClassLoader。

4.获取类加载器对象：

​	getClassLoader()：是Class对象中的方法，直接用 类名.Class.getClassLoader()进行使用

![image-20250206010421210](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206010421210.png)

​	输出：

![image-20250206010439256](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206010439256.png)

​	注意：null是因为BootStrapClassLoader是用C语言实现的，程序员获取不到，所以输出null

5.双亲委派机制（全盘负责委托机制）

![image-20250206011013584](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206011013584.png)

6.类加载器的cache缓存机制

​	一个类加载到内存之后，缓存中也会保存一份，后面如果再使用此类，如果缓存中保存了这个类，就直接返回它；如果缓存中没有，则再加载这个类，下一次如果有其他类使用时就不用再加载了，直接在缓存中请求，保证了类在内存中的唯一性。

7.总结：类加载器的双亲委派和缓存机制共同造就了加载器的特点：保证了类在内存中的唯一性。

![image-20250206011434754](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250206011434754.png)

### 5.枚举

#### 5.1 介绍

1.概述：枚举是五大引用数据类型之一

2.IDEA创建

![image-20250208010006326](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250208010006326.png)

3.定义：public enum 枚举类名 {}	所有枚举类的父类都是Enum

4.定义枚举值：

​	a.枚举值特点：都是static final，即都是常量，但是定义时不能写这两个单词，否则会报错；写完所有枚举值之后加一个分号，且枚举值的名字要大写

![image-20250208010428805](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250208010428805.png)

​	b.使用枚举值：类名直接调用

![image-20250208010638607](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250208010638607.png)

​	c.注意：每一个枚举值都是当前枚举类的对象，即：

![image-20250208011052179](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250208011052179.png)

5.问题：枚举类中的枚举值都是什么类型的？是当前类型，即State

6.枚举中其他成员：构造方法、方法等

​	在枚举中定义的构造方法默认都必须是私有private

7.使用场景：表示对象的状态，可以提供构造方法和get方法进行解释补充

![image-20250208011631640](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250208011631640.png)

![image-20250208011653585](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250208011653585.png)

![image-20250208011802821](C:\Users\13156\AppData\Roaming\Typora\typora-user-images\image-20250208011802821.png)

​	输出：未发货

#### 5.2 枚举的方法

String toString()：返回枚举值的名字（不使用也默认调用）

values()：返回所有的枚举值

valueOf(String str)：将一个字符串转成枚举类型
