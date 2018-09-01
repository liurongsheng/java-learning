### print println的区别
print不换行
println打印的时候自带了换行
```
System.out.print("*");
System.out.print(" ");
System.out.print();//会报错
System.out.println();//不会会报错
```

### 判断两个数谁比较大
```java
package com.liu.test;
import java.io.*;
public class Test {
	public static void main(String[] args) {
		try{
			// 输入流，从键盘接收数
			InputStreamReader isr=new InputStreamReader(System.in);
			BufferedReader br=new BufferedReader(isr);
			// 给出提示
			System.out.println(" 请输入第一个数");
			// 从控制台读取一行数据
			String a1=br.readLine();
			System.out.println(" 请输入第二个数");
			String a2=br.readLine();
			// 把String 转为float
			float num1=Float.parseFloat(a1);
			float num2=Float.parseFloat(a2);
			if(num1>num2){System.out.println(" 第一个大");}
			if(num1==num2){System.out.println(" 相等");}
			if(num1<num2){System.out.println(" 第二个大");}
			}catch(Exception e){
			e.printStackTrace();
			}
	}
}
```

### 输出金字塔的一半
```java
package com.liu.test;
public class Test {
	public static void main(String[] args) {
		int lay = 4;
		// 表示有多少层
		for (int i = 1; i <= lay; i++) {
			// 打印*
			for (int j = 1; j <= i; j++) {
				System.out.print("*");
			}
			System.out.println(); // 换行
		}
	}
} 
---
*
**
***
****
```

### 输出金字塔
```java
package com.liu.test;

public class Test {
	public static void main(String[] args) {
		int lay = 10; // 表示有多少层
		for (int i = 1; i <= lay; i++) {
			// 找出规律
			// 1->3 2->2 3->1 4->0 找出空格
			for (int k = 1; k <= lay - i; k++) {
				System.out.print(" ");
			}
			// 打印*
			// 1->1 2->3 3->5 4->7 找出星的规律
			for (int j = 1; j <= (i - 1) * 2 + 1; j++) {
				System.out.print("*");
			}
			System.out.println(); // 换行
		}
	}
}
---
         *
        ***
       *****
      *******
     *********
    ***********
   *************
  ***************
 *****************
*******************
```

### 输出实心菱形
```java
package com.liu.test;

public class Test {
	public static void main(String[] args) {
		int lay = 4; // 菱形上半部行数
		for (int i = 1; i <= lay - 1; i++) { // 判断循环上半部分
			for (int k = 1; k <= lay - i; k++) { // 找行内* 号前输出空格
				System.out.print(" ");
			}
			for (int j = 1; j <= (i - 1) * 2 + 1; j++) { // 找行内输出星的位置
				System.out.print("*");
			}
			System.out.println(); // 换行
		}
		for (int i = 1; i <= lay; i++) { // 判断循环菱形下半部分
			for (int k = 1; k <= i - 1; k++) { // 判断循环找* 号前要输出空格处
				System.out.print(" ");
			}
			for (int j = 1; j <= (lay - i) * 2 + 1; j++) { // 判断循环行长度
				System.out.print("*");
			}
			System.out.println(); // 输出换行
		}
	}
}
---
   *
  ***
 *****
*******
 *****
  ***
   *
```