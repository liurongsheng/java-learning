# java面向对象编程

计算机语言的发展向接近人的思维方式演变

汇编语言 [ 面向机器]

c 语言 [ 面向过程]

java 语言 [ 面向对象]

类和对象的关系

从猫类到对象，目前有几种说法： 
1. 创建一个对象； 
2. 实例化一个对象；
3. 对类实例化... 

以后大家听到这些说法，不要模糊。*对象就是实例，实例就是对象*
java 最大的特点就是面向对象。

## java 中如何定义一个类？ 

[ 类名的首写字母大写] 可根据程序的需要定义类
```
class Cat{
// 下面的就是类的成员变量 （成员变量也就是所说的属性）
    int age;
    String name;
    String color;
    Master myMaster;
}
```

## 类和对象的区别和联系
1. 类是抽象的，概念的，代表一类事物，比如人类，猫类..
2. 对象是具体的，实际的，代表一个具体事物
3. 类相对 对象来说是模板，对象是类的一个个个体
```
package 包名;
class 类名 extends 父类 implements
接口名{
    成员变量;
    构造方法;
    成员方法;
}
```
## 创建一个对象有两种方法
1. 先声明再创建
    1. 对象声明：类名对象名
    2. 对象创建：对象名=new 类名()
    
2. 一步到位法
类名对象名=new 类名()

## 类的成员变量
成员变量是类的一个组成部分， 

一般是基本数据类型， 也可是引用类型。

比如我们前面定义猫类的int age 就是成员变量。

## 类的成员方法（成员方法也叫成员函）
public 返回数据类型方法名( 参数列表)
{
    语句;// 方法( 函数) 主体
}
1. 参数列表：表示成员函数输入
2. 数据类型( 返回类型) ：表示成员函数输出
3. 函数主体：表示为了实现某一功能代码块

## 类的成员方法-- 声明
public int test(int a); /* 方法声明*/

访问修饰符 数据类型 函数名( 参数列表);
区别就是没有函数体

## 类的构造函数方法

1. 构造方法名和类名相同
2. 构造方法没有返回值
3. 主要作用是完成对新对象的初始化
4. 在创建新对象时，系统自动的调用该类的构造方法；
5. 一个类可以有多个构造方法
6. 每一个类都有一个默认的构造方法

```java
package com.liu.test;

public class Test {
	public static void main(String[] args) {
		// 定义一个人类
		class Person {
			int age;
			String name;
			// 默认构造方法
			public Person() {
			}
			// 构造方法的主要用处是：初始化你的成员属性( 变量)
			// 构造方法
			public Person(int age, String name) {
				System.out.println(" 我是构造1");
				age = age;
				name = name;
			}
			// 构造方法2
			public Person(String name) {
				System.out.println(" 我是构造2");
				name = name;
			}
		}
	}
}
```

## 类变量和类方法

什么是类变量：

类变量是该类的所有对象共享的变量，任何一个该类的对象去访问它时，取到的都是相同的值，
同样任何一个该类的对象去修改，修改的也是同一个变量。

什么时候需要用类变量
属于公共的属性用类变量

如何定义类变量？

定义语法：

    访问修饰符 static 数据类型 变量名;

如何访问类变量？

    类名.类变量名 或者 对象名.类变量名

什么是类方法：

    类方法是属于所有对象实例的

什么时候需要用类方法

    属于公共的方法用类方法

定义语法：

    访问修饰符 static 数据返回类型 方法名(){}

#### 注意：类方法中不能访问非静态变量

#### 非静态方法可以访问非静态变量（类变量），同时也可以访问静态变量。

类方法可以通过类名.类方法名直接访问

## 类变量与实例变量区别，类方法类似
加上static 称为类变量或静态变量，否则称为实例变量
类变量是与类相关的，公共的属性

---

# 面向对象编程的三大特征

1. 封装
2. 继承
3. 多态

## 什么是抽象
我们在前面去定义一个类时候， 实际上就是把一类事物的共有的属性和行为提取出来，
形成一个物理模型( 模版) 。这种研究问题的方法称为抽象。

## 什么是封装
封装就是把抽象出的数据和对数据的操作封装在一起，数据被保护在内部，
程序的其他部分只有通过被授权的操作（成员方法）才能对数据进行操作。

比如通过遥控操作电视机就是典型的封装

### 封装--访问控制修饰符
java提供四种访问控制修饰符号控制方法和变量的访问权限

1. 公开级别，用 public 修饰，对外公开
2. 受保护级别，用 protected 修饰，对子类和同一个包中的类公开
3. 默认级别，没有修饰符号，向同一个包的类公开
4. 私有级别，用 private 修饰，只有类本身可以访问，不对外公开
```
访问级别 访问控制修饰符  同类 同包 子类  不同包
公开     public         1   1    1      1
受保护   protected      1   1    1      0
默认     无             1   1    0      0
私有    private         1   0    0      0
```
#### 包的三大作用
1. 区分相同名字的类
2. 当类很多时，可以很好的管理类
3. 控制访问范围

#### 包 -打包命令
package com.ceshi;

#### 包 -命令规范
小写字母 比如 com.sina.ceshi

#### 包 -常用的包
一个包下包含很多的类，java中常用的包有
```
java.lang.*包，自动引入
java.util.*包，工具包
java.net.*包，网络包
java.awt.*包，窗口工具包
```
#### 包 -如何引入
语法： import 包;
>import java.awt.*;

## 继承
继承可以解决代码复用，让我们的编程更加靠近人类思维。
当多个类存在相同的属性( 变量)和方法时，可以从这些类中抽象出父类，

在父类中定义这些相同的属性和方法，所有的子类不需要重新定义这些属性和方法，
只需要通过extends 语句来声明继承父类：

语法： class 子类extends 父类
子类就会自动拥有父类定义的某些属性和方法

###  除了private 修饰的属性和方法不能被继承，其他三个修饰符都可以被继承
父类的public 修饰符的属性和方法；
protected 修饰符的属性和方法；
默认修饰符属性和方法被子类继承了，
父类的private 修饰符的属性和方法不能被子类继承。

注意事项
1. 子类最多只能继承一个父类( 指直接继承)
2. java 所有类都是Object 类的子类 ( 所有的子类都可以逐级继承，例: 爷-> 父-> 子-> 孙)
3. JDK6 中有202 个包 3777 个类、接口、异常、枚举、注释和错误
4. 在做开发的时候，强烈建议大家多查jdk 帮助文档
5. 在使用类时，实在不知道怎么办，多使用搜索引擎

## 方法重载(overload) 和方法覆盖(override)

>方法重载(overload)

简单的说： 方法重载就是在类的同一种功能的多种实现方式，到底采用哪种方式，取决于调用者给出的参数。
注意事项：
1. 方法名相同
2. 方法的参数类型，个数，顺序至少有一项不同
3. 方法返回类型可以不同(只是返回类型不一样，不能构成重载)
4. 方法的修饰符可以不同(只是控制访问修饰符不同，不能构成重载)

 >方法覆盖(override)
 
 方法覆盖就是子类有一个方法， 和父类的某个方法的名称、返回类型、参数一样，
 那么我们就说子类的这个方法覆盖了父类的那个方法。
 
 方法覆盖有很多条件，有些书上说的比较细，总的讲有两点一定注意：
 1. 子类的方法的返回类型，参数，方法名称，要和父类的返回类型，参数，方法名称完全一样，否则编译出错。
 2. 子类方法不能缩小父类方法的访问权限。

## 多态
就是指一个引用( 类型) 在不同情况下的多种状态。
也可以理解成： 多态是指通过指向父类的指针，来调用在不同子类中实现的方法。

实现多态有两种方式：
1. 继承
2. 接口 
```java
package com.liu.test;

public class Test {
	public static void main(String[] args) {
		// 非多态演示
		Cat cat = new Cat();
		cat.cry();
		Dog dog = new Dog();
		dog.cry();
		// 多态演示
		Animal an = new Cat();
		an.cry();
		an = new Dog();
		an.cry();
	}
}

// 动物类
class Animal {
	String name;
	int age;

	public String getName() {
		return name;
	}

	public void setName(String name) {
		this.name = name;
	}

	public int getAge() {
		return age;
	}

	public void setAge(int age) {
		this.age = age;
	}

	// 动物会叫
	public void cry() {
		System.out.println(" 不知道怎么叫");
	}
}

// 创建Dog子类并继承Animal 父类及覆盖cry 方法
class Dog extends Animal {
	// 狗叫
	public void cry() {
		System.out.println(" 汪汪叫");
	}
}

class Cat extends Animal {
	// 猫自己叫
	public void cry() {
		System.out.println(" 猫猫叫");
	}
}
---
 猫猫叫
 汪汪叫
 猫猫叫
 汪汪叫
```
java 允许父类的引用变量引用它的子类的实例( 对象)
Animal an=new Cat(); // 这种转换时自动完成的

## 抽象类

当父类的一些方法不能确定时，可以用abstract 关键字来修饰该方法[抽象方法] ，用abstract 来修饰该类[抽象类] 。

抽象类是java 中一个比较重要的类。
1. 用abstract 关键字来修饰一个类时，这个类就是抽象类。
2. 用abstract 关键字来修饰一个方法时，这个方法就是抽象方法。
3. abstract 抽象类中的abstract 抽象方法是不允许在抽象类中实现的，一旦实现就不是
抽象方法和抽象类了。abstract 抽象方法只能在子类中实现。
4. 抽象类中可以拥有实现方法。
5. 抽象方法在编程中用的不是很多，但是在公司笔试时，却是考官比较爱问的知识点。

注意事项：
1. 抽象类不能被实例化
2. 抽象类不一定要包含abstract 方法。也就是说，抽象类可以没有abstract 抽象方法。
3. 一旦类包含了abstract 抽象方法，则这个类必须声明为abstract 抽象类。
4. 抽象方法不能有主体。
    1. 正确的抽象方法例： abstract void abc();
    2. 错语的抽象方法例： abstract void abc(){}
    
## 接口
接口-- 为什么有？

USB插槽就是现实中的接口。

什么是接口？

接口就是给出一些没有内容的方法，封装到一起，到某个类要使用的时候，在根据具体情况把这些方法写出来。

接口的建立语法： interface 接口名{ 方法;}
语法： 
```
class 类名 implements 接口{
    方法;
    变量;
}    
```
接口是更加抽象的抽象的类，抽象类里的方法可以有方法体，接口里的所有方法都没有方法体。
接口体现了程序设计的多态和高内聚低偶合的设计思想。

注意事项
1. 接口不能被实例化
2. 接口中所有的方法都不能有主体。错误语法例：void aaa(){} ←( 注意不能有花括号)
接口可以看作更加抽象的抽象类。
3. 一个类可以实现多个接口
4. 接口中可以有变量[ 但变量不能用private 和protected 修饰]
    1. 接口中的变量，本质上都是static 的而且是final 类型的，不管你加不加static 修饰
    2 . 在java 开发中，我们经常把常用的变量，定义在接口中，作为全局变量使用访问形式：接口名. 变量名
5. 一个接口不能继承其它的类，但是可以继承别的接口
```java
package com.liu.test;

public class Usb {
	public static void main(String[] args) {
		UsbInterface u = new Camera();
		u.start();
		u.stop();
	}
}

interface UsbInterface {
	int a = 1; // 加不加static 都是静态的，不能用private 和protected 修饰
// 声明了两个方法

	public void start(); // 接口开始工作

	public void stop(); // 接口停止工作
}

// 编写了一个相机类，并实现了UsbInterface 接口
//一个重要的原则：当一个类实现了一个接口，要求该类把这个接口的所有方法全部实现
class Camera implements UsbInterface {
	public void start() {
		System.out.println(" 我是相机，开始工作了..");
	}

	public void stop() {
		System.out.println(" 我是相机，停止工作了..");
	}
}
---
 我是相机，开始工作了..
 我是相机，停止工作了..
```

## 实现接口 VS 继承类
java 的继承是单继承，也就是一个类最多只能有一个父类，这种单继承的机制可保证类的纯洁性，
比C++中的多继承机制简洁。但是不可否认，对子类功能的扩展有一定影响。

所以：
1. 实现接口可以看作是对继承的一种补充。(继承是层级式的，不太灵活。修改某个类就会打破继承的平衡，
而接口就没有这样的麻烦，因为它只针对实现接口的类才起作用)

2. 实现接口可在不打破继承关系的前提下，对某个类功能扩展，非常灵活。


### 用接口实现多态
java 中多态是个难以理解的概念，但同时又是一个非常重要的概念。java 三大特性之一( 继承，封装，多态)，
我们可以从字面上简单理解：就是一种类型的多种状态，以下通过卖小汽车的例子说明什么是多态。

```java
package com.liu.test;

public class Test {

	public static void main(String[] args) {
		CarShop aShop = new CarShop();
		// 卖出一辆宝马
		aShop.sellCar(new BMW());
		// 卖出一辆奇瑞QQ
		aShop.sellCar(new CheryQQ());
		// 卖出一辆桑塔纳
		aShop.sellCar(new Santana());
		System.out.println(" 总收入： " + aShop.getMoney());
	}
}

// 汽车接口
interface Car {
	// 汽车名称
	String getName();

	// 获得汽车售价
	int getPrice();
}

// 宝马
class BMW implements Car {
	public String getName() {
		return "BMW";
	}

	public int getPrice() {
		return 300000;
	}
}

// 奇瑞QQ
class CheryQQ implements Car {
	public String getName() {
		return "CheryQQ";
	}

	public int getPrice() {
		return 20000;
	}
}

// 桑塔纳汽车
class Santana implements Car {
	public String getName() {
		return "Santana";
	}

	public int getPrice() {
		return 80000;
	}
}

// 汽车出售店
class CarShop {
	// 售车收入
	private int money = 0;

	// 卖出一部车
	public void sellCar(Car car) {
		System.out.println(" 车型： " + car.getName() + " 单价： " + car.getPrice());
		// 增加卖出车售价的收入
		money += car.getPrice();
	}

	// 售车总收入
	public int getMoney() {
		return money;
	}
}
---
 车型： BMW 单价： 300000
 车型： CheryQQ 单价： 20000
 车型： Santana 单价： 80000
 总收入： 400000

```
继承是多态得以实现的基础。
从字面上理解，多态就是一种类型( 都是Car 类型) 表现出多种状态
( 宝马汽车的名称是BMW，售价是300000；奇瑞汽车的名称是CheryQQ，售价是2000) 。

将一个方法调用同这个方法所属的主体( 也就是对象或类) 关联起来叫做绑定，分前期绑这下和后期绑定两种。

下面解释一下它们的定义：
1. 前期绑定：在程序运行之前进行绑定，由编译器和连接程序实现，又叫做静态绑定。
比如static 方法和final 方法，注意，这里也包括private 方法，因为它是隐式final 的。

2. 后期绑定：在运行时根据对象的类型进行绑定，由方法调用机制实现，因此又叫做动态绑定，
或者运行时绑定。除了前期绑定外的所有方法都属于后期绑定。

多态就是在后期绑定这种机制上实现的。
多态给我们带来的好处是消除了类之间的偶合关系，使程序更容易扩展。

比如在上例中， 新增加一种类型汽车的销售。只需要让新定义的类实现Car 类并实现它的所有方法， 
而无需对原有代码做任何修改， CarShop 类的sellCar(Carcar) 方法就可以处理新的车型了。

