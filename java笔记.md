# java笔记

## java 程序运行关系
```
1.java 源文件(.java 文件)
2.java 编译器即javac.exe
3.java 字节码文件(.class 文件)
4.由解释执行器即(java.exe) 将字节码文件加载到java 虚拟器(jvm)
5.字节码文件(.class) 就会在java 虚拟机中执行
```

## java 基本数据类型四大类型
整数类型、小数( 浮点) 类型、布尔类型、字符类型

### 整数类型
可以表示一个整数， 常用的整数类型有： byte,short,int,long
```
主要区别是数据大小范围，请大家看一个小案例。
byte 占用内存 1 个字节范围： -128 至127
short 占用内存 2 个字节范围： -32768 至32767
int 占用内存 4 个字节范围： -2147483648 至2147483647 2的31次方-1 至 2的31次方
long 占用内存 8 个字节范围： 9223372036854775807 至 -9223372036854775808  2的64次方-1 至 2的64次方
```

### 小数( 浮点) 类型
可以表示一个小数，常用的小数( 浮点) 类型有：float( 单精度),double( 双精度)
```
float 占用内存四个字节范围： 3.4E-38 至3.4E+38 只能提供7 位有效数字
double 占用内存八个字节范围： 1.7E-308 至1.7E+308 可提供16 位有效数字
```

### 布尔类型
可以表示"真" 或者"假" ，类型是boolean

### 字符类型
可以表示单个字符，字符类型是char 。char 是两个字节( 可以存放汉字)
多个字符我们称为字符串，在java 中String 这种数据类型表示，
但是String 不是基本数据类型，而是类，类是复合数据类型。

在java 中，对char 进行运算的时候，直接当做ascii 码对应的整数对待。
int test1='a'+'b'; 输出值195 
char test2='a'+'b'; 输出值? 
char test3='a'+'中'; 输出值于

### 基本数据类型转换

数据类型可以自动的从低精度-->高精度。高精度不能自动转为低精度
byte 小于<short 小于<int 小于<long 小于<float 小于<double
在java 中的小数默认是double 数据类型
float 赋值时要在值后加f
long 赋值时要在值后加l

强制转换
int a=(int)1.2;


---

# java 数组

## 定义数组

数据类型数组名[] = new 数据类型[ 数组大小];

int a[] = new int[5];
// 定义一个数组名为a 的整型数组，并可以放入5 个整型数。

## 数组初始化

数据类型数组名[] = { 元素值, 元素值...};

int a[] = {2,5,6,7,8,89,90,34,56};

相当于
int a[] = new int[9];
int a[0] = 2;int a[1]=5;int a[2]=6;...a[8]=56;

## 一维数组总结

1. 数组可存放同一类型数据；
2. 简单数据类型(int,float) 数组，可直接赋值；
3. 对象数组在定义后，赋值时需要再次为每个对象分配空间[ 即： new 对象]；
4. 数组大小必须事先指定；
5. 数组名可以理解为指向数组首地址的引用；
6. 数组的下标是从0 开始编号的；

---


