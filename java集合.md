# java集合

1. 要求线程安全，使用 Vector, Hashtable
2. 不要求线程安全，使用 ArrayList, LinkedList, HashMap
3. 要求 key 和 value 键值，则使用 HashMap, Hashtable
4. 数据量很大，又要线程安全，则使用 Vector


## Set 结构的集合类
- HashSet 类
- TreeSet 类

HashSet 是基于 HashMap 实现的， HashSet 底层采用 HashMap 来保存所有元素

hashCode() 和 equal() 是 HashMap 用的，因为无需排序所以只需要关注定位和唯一性即可
hashCode() 是用来计算 hash 值的， hash 值是用来确定 hash 表索引的
hash 表中的一个索引存放的是一张链表，所以还要通过 equal() 循环比较链上的每一个对象才可以真正定位到键值对应的 Entry

put 操作时，如果 hash 表中没定定位到， 就在链表前加一个 Entry, 如果定位到了, 则更换 Entry 中的 value(值) 并返回旧 value(值)

覆写 key 的 hashCode() 和equal() 时一定要注意， 不要把它们和可变属性关联上，否则属性变了之后 hashCode 会变， equal 也会为 false ，
这样在 Map 中就找不到它了。而且这样的对象因为找不到它，所以得不到释放，这样就变成了一个无效引用( 相当于内存泄漏)

TreeSet 集合类是一个有序集合，它的元素按照升序排序，默认是自然顺序排列，也就是说 TreeSet 中的对象元素需要实现 Comparable 接口。
TreeSet 与 HashSet 类一样没有 get() 方法来获取列表中的元素，所以也只能通过迭代器方法来获取。

HashSet 与 TreeSet 集合类的区别：
HashSet 是基于 hash 算法实现的，性能优于TreeSet。通常使用 HashSet，在我们需要对其中元素排序的时候才使用 TreeSet


Queue结构的集合

Queue 接口与 List、Set 同一级别，都是继承了 Collection 接口。LinkedList 实现了 Queue 接口。
Queue 接口窄化了对 LinkedList 的方法的访问权限（即在方法中的参数类型如果是 Queue 时，就完全只能访问 Queue 接口所定义的方法了，
而不能直接访问 LinkedList 的非 Queue 的方法），以使得只有恰当的方法才可以使用。

队列是一种数据结构。它有两个基本操作： 在队列尾部加人一个元素， 和从队列头部移除一个元素。就是说，
队列以一种先进先出的方式管理数据， 如果你试图向一个已经满了的阻塞队列中添加一个元素或者是从一个空的阻塞队列中移除一个元索，将导致线程阻塞。

## List/Set 和 Map 的区别

List 按对象进入的顺序保存对象，不做排序和编辑操作。
Set 对每个对象只接受一次，并使用自己内部的排序方法( 通常，你只关心某个元素是否属于 Set 而不关心它的顺序 -- 否则使用List)
Map 同样对每个元素保存一份， 但这是基于" 键"(key) 的，Map也有内置的排序， 因而不关心元素添加的顺序。

如果添加元素的顺序对程序设计很重要， 应该使用 LinkedHashSet 或者 LinkedHashMap

实际上有两种List：一种是基本的 ArrayList 其优点在于随机访问元素，
另一种是更强大的 LinkedList，它并不是为快速随机访问设计的，而是具有一套更通用的方法。



