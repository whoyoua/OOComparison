# Multithreading
[Go back to README.md](README.md)

## Threads or thread-like abilities

* JAVA

  JAVA uses threads, which are objects like any other Java objects.

  Threads are instances of class **java.lang.Thread**, or instances of subclasses of this class. In addition to being objects, java threads can also execute code.

  There are two ways to start a thread.

  * Provide a Runnable object

    The Runnable interface defines a single method, run, meant to contain the code executed in the thread. The Runnable object is passed to the Thread constructor, as in the HelloRunnable example:

    ```JAVA
    public class HelloRunnable implements Runnable {

      public void run() {
          System.out.println("Hello from a thread!");
        }

        public static void main(String args[]) {
          (new Thread(new HelloRunnable())).start();
        }
    }
    ```

  * Subclass Thread.

    The Thread class itself implements Runnable, though its run method does nothing. An application can subclass Thread, providing its own implementation of run, as in the HelloThread example:

    ```JAVA
      public class HelloThread extends Thread {
        public void run() {
          System.out.println("Hello from a thread!");
        }

        public static void main(String args[]) {
          (new HelloThread()).start();
        }
      }
    ```

  References:

  <https://docs.oracle.com/javase/tutorial/essential/concurrency/simple.html>

---

* Swift

  Grand Central Dispatch is probably one of the most used technologies on all Apple platforms when it comes to performance, concurrency, parallelization and threading.

  ```Swift
    DispatchQueue.global(qos: .background).async {
      print("This is run on the background queue")

      DispatchQueue.main.async {
        print("This is run on the main queue, after the previous code in outer block")
    }
  }
  ```

  Or users can use the operation queues.

  ```Swift
    let queue = OperationQueue()

    queue.addOperation() {
      // do something in the background

      OperationQueue.main.addOperation() {
        // when done, update your UI and/or model on the main queue
      }
    }
  ```

  References:

  <http://stackoverflow.com/questions/24056205/how-to-use-background-thread-in-swift>

  <http://stackoverflow.com/questions/24589575/how-to-do-multithreading-concurrency-or-parallelism-in-ios-swift/24894811#24894811>

## How is multitasking accomplished?

* JAVA

  Multithreading in java is a process of executing multiple threads simultaneously.

  Thread is basically a lightweight sub-process, a smallest unit of processing. Multiprocessing and multithreading, both are used to achieve multitasking.

  Here is a example of performing multiple tasks by multiple threads.

  ```JAVA
  class Simple1 extends Thread{  
    public void run(){  
      System.out.println("task one");  
    }  
  }  

  class Simple2 extends Thread{  
    public void run(){  
      System.out.println("task two");  
    }  
  }  

  class TestMultitasking3{  
    public static void main(String args[]){  
      Simple1 t1=new Simple1();  
      Simple2 t2=new Simple2();  

      t1.start();  
      t2.start();  
    }  
  }  
  ```

  References:

  <https://www.javatpoint.com/multitasking-in-multithreading>

  <https://www.javatpoint.com/multithreading-in-java>

---

* Swift

  Here is a example of multithreading with low-level C-style functions:

  ```Swift
    dispatch_async(dispatch_get_global_queue(DISPATCH_QUEUE_PRIORITY_DEFAULT, 0)) {  
        // Download file or perform expensive task

      dispatch_async(dispatch_get_main_queue()) {  
        // Update the UI  
      }
    }
  ```

  In the example above an asynchonous task is dispatched with **dispatch_async()**. The actual task is a closure, which first downloads a file and then updates the UI. The task is dispatched to an operation queue and is given a priority.

  When the task finishes, another **dispatch_async()** call is made to execute another task on the main thread.

  References:
  
  <https://learnappmaking.com/grand-central-dispatch-swift-3/>

---

[Go back to README.md](README.md)
