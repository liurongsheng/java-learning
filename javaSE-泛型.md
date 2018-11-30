# javaSE-泛型

泛型是 java se1.5 的新特性，泛型的本质是参数化类型，也就是说所操作的数据类型被指定为一个参数。
这种参数类型可以用在类、接口和方法的创建中，分别称为泛型类、泛型接口、泛型方法

java 语言引入泛型的好处是安全简单。

在 java se1.5 之前， 没有泛型的情况下，通过对类型Object 的引用来实现参数的“任意化”，“任意化” 带来的缺点是要做显式的强制类型转换， 
而这种转换是要求开发者对实际参数类型可以预知的情况下进行的，对于强制类型转换错误的情况，编译器可能不提示错误，
在运行的时候才出现异常，这是一个安全隐患。

泛型的好处是在编译的时候检查类型安全，并且所有的强制转换都是自动和隐式的，提高代码的重用率。

```
import java.util.*;
public class Generics {
  public static void main(String[] args) {
    ArrayList<Dog> al=new ArrayList<Dog>(); //<Dog> 即泛型的指定参数，提高安全性
    ArrayList bl=new ArrayList();
    
    // 创建一只狗
    Dog dog1=new Dog();
  
    // 放入到集合中
    al.add(dog1);
  
    // 取出
    Dog temp=al.get(0); // 引用泛型后即可不用强转， Dog temp=(Dog)al.get(0);
    Cat temp1=(Cat)bl.get(0);
  }
}
```

泛型有下面几个优点：
1. 类型安全
2. 向后兼容
3. 层次清晰
4. 性能较高
