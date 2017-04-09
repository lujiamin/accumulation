## ArrayList,LinkedList,Vector
- 三者都实现了 List 接口，均为可伸缩数组，即可以动态改变长度.
- ArrayList 和 Vector 在内存中数据存储是连续的.
- Vector 是线程安全的，而 ArrayList 不是。因此 Vector 性能上略逊于 ArrayList.
- LinkedList 采用双向链表实现，对数据的索引需要从头开始，因此访问效率比较低，但是插入效率较高.
- LinkedList 不是线性安全的容器.

## HashSet,LinkedHashSet,TreeSet
- HashSet 基于散列表实现,基本方法的时间复杂度为O(1)。不能保证元素的排列顺序，只能存放一个 null 值。
- LinkedHashSet 基于哈希表和链表实现的，使用链表维护了元素插入的顺序。基本方法的时间复杂度为O(1).
- TreeSet 基于红黑树实现。基本方法的时间复杂度为O(log(n)),是 SortedSet 接口的唯一实现类，元素已经进行了排序.

## HashMap,TreeMap ,WeakHashMap,LinkedHashMap
- HashMap 使用最多，顺序随机。插入删除定位最好使用 HashMap
- LinkedHashMap 维护了输入的顺序
- TreeMap 实现了 SortMap 接口，能够将保存的记录根据键(key)排序。
- WeakHashMap 中 key 采用了弱引用，只要key不再被外部引用，它就可以被垃圾回收器回收。

## HashMap 和HashTable
- 它们都实现了 Map 接口。
- HashMap 允许一个 null 键，HashTable 不允许。
- HashTable 是线程安全的，HashMap 不支持线程安全。