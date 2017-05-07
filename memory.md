# Memory management
[Go back to README.md](README.md)

## How is it handled?

* JAVA

  In JAVA, developer do not need to manage memory explicitly. Allocation and deallocation of memory will be handled by [JAVA virtual machine(JVM)](https://en.wikipedia.org/wiki/Java_virtual_machine) and specially the garbage collector.

  References:

  <http://www.baeldung.com/java-memory-management-interview-questions>

---

* Swift

  Swift is able to handle much of the memory management (allocation and deallocation )of the application by using the automatic reference counting, or ARC. As a result, users do not have explicitly participate in the memory management.

  References:

  <https://www.raywenderlich.com/134411/arc-memory-management-swift>


## How does it work?

* JAVA

  JAVA objects are stored in the heap, which will be created by the JVM and change the size while the application run.  When the heap becomes full, garbage will be collected. During the garbage collection, objects that are no longer used are cleared, so new objects can be created in heap.

  Small objects are allocated in thread local areas (TLAs). The thread local areas are free chunks reserved from the heap and given to a JAVA thread for exclusive use. The thread can then allocate objects in its TLA without synchronizing with other threads. When the TLA becomes full, the thread simply requests a new TLA. The TLAs are reserved from the nursery if such exists, otherwise they are reserved anywhere in the heap.

  Large objects that don’t fit inside a TLA are allocated directly on the heap. When a nursery is used, the large objects are allocated directly in old space. Allocation of large objects requires more synchronization between the JAVA threads, although the  JVM uses a system of caches of free chunks of different sizes to reduce the need for synchronization and improve the allocation speed.

  References:

  <https://www.quora.com/How-does-memory-management-work-in-Java>

  <https://docs.oracle.com/cd/E13150_01/jrockit_jvm/jrockit/geninfo/diagnos/garbage_collect.html#wp1085990>

---
* Swift

  Every time users create a new instance of a class, ARC will allocate a chunk of memory to store information about that instance. This memory holds information about the type of the instance, together with the values of any stored properties associated with that instance.

  When an instance is no longer needed, ARC frees up the memory used by that instance so that the memory can be used for other purposes instead. This ensures that class instances do not take up space in memory when they are no longer needed.

  Whenever users assign a class instance to a property, constant, or variable, that property, constant, or variable makes a strong reference to the instance. The reference is called a “strong” reference because it keeps a firm hold on that instance, and does not allow it to be deallocated for as long as that strong reference remains.

  As a result, ARC tracks how many properties, constants, and variables are currently referring to each class instance so that it will not deallocate an instance as long as at least one active reference to that instance still exists.

  References:

  <https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/AutomaticReferenceCounting.html>



## Garbage collection?

* JAVA

  Garbage collection is the process of looking at heap memory and identify whether the objects are in use or not, then delete the unused objects.

  The biggest advantage of garbage collection is removing the burden of manual memory allocation and deallocation, so the users do not have to focus on the manage the memory.

  However, the garbage collection also has the disadvantage. When the garbage collector runs, it has an effect on the application’s performance because all other threads in the application have to be stopped to allow the garbage collector thread to effectively do its work, which may cause unacceptable freeze.


  References:
  <http://www.baeldung.com/java-memory-management-interview-questions>

---
* Swift

  There is no "garbage collection" that can be seen in JAVA. On the contrary, Swift uses automatic reference counting to manage the memory.

  References:

  <https://www.quora.com/Why-doesnt-Apple-Swift-adopt-the-memory-management-method-of-garbage-collection-like-in-Java>

## Automatic reference counting?

* JAVA

  JAVA does not use the ARC (automatic reference counting).

  JAVA uses the Mark-and-Sweep Garbage Collector to release the objects that are not used anymore on the heap.

  A mark and sweep garbage collection consists of two phases, the mark phase and the sweep phase.

  During the mark phase all objects that are reachable from Java threads, native handles and other root sources are marked as alive, as well as the objects that are reachable from these objects and so forth. This process identifies and marks all objects that are still used, and the rest can be considered garbage.

  During the sweep phase the heap is traversed to find the gaps between the live objects. These gaps are recorded in a free list and are made available for new object allocation.

  References:

  <http://stackoverflow.com/questions/30628536/mark-and-sweep-vs-automatic-reference-counting>

  <https://docs.oracle.com/cd/E13150_01/jrockit_jvm/jrockit/geninfo/diagnos/garbage_collect.html#wp1085786>

---
* Swift

  Swift uses Automatic Reference Counting (ARC) to track and manage app’s memory usage. ARC will automatically frees up the memory used by class instances when those instances are no longer needed.

  ARC differs from garbage collection in that there is no background process that deallocates the objects asynchronously at runtime.

  Unlike garbage collection, ARC does not handle [reference cycles](https://en.wikipedia.org/wiki/Reference_counting#reference_cycle) automatically. This means that as long as there are "strong" references to an object, it will not be deallocated. Strong cross-references can accordingly create [deadlocks](https://en.wikipedia.org/wiki/Deadlock) and [memory leaks](https://en.wikipedia.org/wiki/Memory_leak). It is up to the developer to break cycles by using weak references.

  References:

  <https://en.wikipedia.org/wiki/Automatic_Reference_Counting>

  <https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/AutomaticReferenceCounting.html>
  
---
[Go back to README.md](README.md)
