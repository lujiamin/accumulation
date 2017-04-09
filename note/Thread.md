## 如何实现多线程
- 继承 Thread 类，重写 run() 方法
```
class MyThread extends Thread{
	public void run(){

	}
}
```
- 实现 Runnable() 接口，并实现该接口的 run() 方法
```
class MyThread implements Runnable{
	public void run(){

	}
}
```
- 实现 Callable 方法重写 call 方法

## run() 方法和 start() 方法的区别
- 调用线程类的 start() 方法来启动一个线程。在调度过程中，JVM通过调用 run() 方法来完成实际的操作。
- 直接调用 run() 方法,会被当成普通函数调用，无法实现多线程的目的。

## 多线程同步的实现方法
#### synchronized 关键字
- synchronized 方法，把需要被同步的资源的操作放到方法中，就能保证这个方法在同一时刻被一个线程访问。但是当方法体量非常大时，会影响整个程序的效率。
- synchronized 块 
```
synchronized(synObj){
	
}
```  
- 获取多个锁时，会按相反的顺序释放，并且是自动解锁。不会因为异常导致锁没有被释放而出现死锁。

#### wait() 和 notify()
- 由于使用 synchronized 后，线程 A1 执行完成后，线程 A2 才能继续执行。可以使用 wait() 方法，释放对象锁，进入等待状态，并调用 notify() 或者 notifyAll() 方法唤醒其他线程，并允许他们获得锁。

####  Lock
- 获取锁之后，需要开发人员在 finally 块中手动释放，否则会引起死锁的发生。
- tryLock() 采用非阻塞的方式去获取锁。
```
Lock lock=new ReentrantLock();
try{
    lock.lock();
    }finally{
        lock.unlock();
    }
```

## volatile
- 被 volatile 修饰的变量，系统每次用到它时都是直接从对应的内存中提取，而不是利用缓存。所有线程在任何时候看到的变量的值都是相同的。
- volatile 不能保证操作的原子性。
- 使用 volatile 会阻止编译器对代码的优化，会降低程序的运行的效率。

## 终止线程的方法
- Thread.stop() 来终止线程时，会释放已经锁定的所有监视资源。但是当任何一个受这些监视资源保护的对象处于一个不一致的状态，其他线程会看到这一状态，导致程序执行的不确定性。
- 调用 suspend() 方法，将一个有锁的线程挂起，这时容易造成死锁。
- 使用 interrupt() 方法中断线程，会抛出 InterruptedException 异常，可以在 run() 方法中捕获这个异常来让线程安全退出。

## 守护线程(服务线程、后台线程)
- 只要有非守护线程还在运行，程序就不会终止。
- 设置守护线程，t.setDaemon(true);要设置在 start() 放方法之前。
- 典型例子，垃圾回收器。只要 JVM 启动，它始终运行，实时监控和管理系统中可以被回收的资源。

## join() 方法
- 调用该方法的线程在执行完 run() 方法后，再执行 join() 方法后面的代码
- t.join(2000); 等待线程 t 结束，但是只等待 2 s。