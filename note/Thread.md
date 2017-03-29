### 如何实现多线程
- 继承 Thread 类，重写 run() 方法
- 实现 Runnable() 接口，并实现该接口的 run() 方法
- 实现 Callable 方法重写 call 方法

### run() 方法和 start() 方法的区别
- 调用线程类的 start() 方法来启动一个线程。在调度过程中，JVM通过调用 run() 方法来完成实际的操作。
- 直接调用 run() 方法,会被当成普通函数调用，无法实现多线程的目的。

### 多线程同步的实现方法
- synchronized 关键字
 - synchronized 方法，把需要被同步的资源的操作放到方法中，就能保证这个方法在同一时刻被一个线程访问。但是当方法体量非常大时，会影响整个程序的效率。
 - synchronized 块 
```
synchronized(synObj){
	
}
```  
- wait() 和 notify()
 - 由于使用 synchronized 后，线程 A1 执行完成后，线程 A2 才能继续执行。可以使用 wait() 方法，释放对象锁，进入等待状态，并调用 notify() 或者 notifyAll() 方法唤醒其他线程，并允许他们获得锁。
-  Lock