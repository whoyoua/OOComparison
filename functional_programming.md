# Functional programming

[Go back to README.md](README.md)

## Does the language support functional programming?

* JAVA

  What is functional programming? The simple answer: Everything is a mathematical function. Functional programming languages can have objects, but generally those objects are immutable -- either arguments or return values to functions. There are no for/next loops, as those imply state changes. Instead, that type of looping is performed with recursion and by passing functions as arguments.

  Users can obviously implement things following a functional paradigm. However, the Java language doesn't provide the syntactic sugar for it, so some things will be tedious at best, and some other ones will be extremely arcane.

  To do functional programming you typically need:

  * First class functions - easy to create in Java by defining an abstract class or interface that represents your "Function" and has an "apply" method which applies the function to one or more parameters.

  * Closures - create an instance of your function object above with the closed-over values stored in final fields. You can use an anonymous inner class for this.

  * A library of standard higher order functions - this is trickier, however you can still write your own to bootstrap a simple functional language in a few hours. If you want something fancier, you can check out other functional libraries people have built in Java.

  Here is a  functional programming library i find on the internet.

  (http://www.functionaljava.org/)

  Functional Java is an open source library facilitating functional programming in Java. The library implements numerous basic and advanced programming abstractions that assist composition oriented development. Functional Java also serves as a platform for learning functional programming concepts by introducing these concepts using a familiar language.

  The library is intended for use in production applications and is thoroughly tested using the technique of automated specification-based testing with [ScalaCheck](http://www.scalacheck.org/) and Functional Java’s Quickcheck module. Functional Java is compiled with Java 8 targeting Java 6 bytecode. The use of lambdas within the project are backported with the [Retro Lambda](https://github.com/orfjackal/retrolambda) library, supporting Java versions 5 to 8 and beyond.

  ### Functional Java provides abstractions for the following types:

  Basic Data Structures - total and partial functions, products, unit, option, unbiased and right biased unions (either and validation), void.

  Immutable Collections - array, list, vector, stream, set, map, finger tree, priority queue, heterogenous list, difference lists.

  Other Abstractions - monoid, semigroup, natural, random number generator, reader, writer, state, input/output, parser, zipper, specification based testing, actors, concurrency, optics (lens, prism, fold, traversal and others) and type conversion.

  See the [features page](http://www.functionaljava.org/features.html) for a brief description of each of these types.

  Here is a example of using JAVA in a functional way.

  ```JAVA
  final Array<Integer> a = array(1, 2, 3);
  final Array<Integer> b = a.map(i -> i + 42);
  arrayShow(intShow).println(b); // {43,44,45}

  // combine into a single step
  arrayShow(intShow).println(array(1, 2, 3).map(i -> i + 42));
  ```

  References:

  <http://www.javaworld.com/article/2078610/java-concurrency/functional-programming--a-step-backward.html>

  <http://www.functionaljava.org/>

---

* Swift

  Swift also support the functional programming. With Swift, functional programming techniques become a viable and important part of your programming toolkit.

  Here is a example of functional programming in Swift.

  In old way:

  ```Swift
  var evens = [Int]()
  for i in 1...10 {
  if i % 2 == 0 {
    evens.append(i)
  }
  }
  println(evens)
  ```

  This little script is very simple; the key points of the algorithm are as follows:
  * Creating an empty (and mutable) array.
  * The for loop iterates over the numbers from 1 to 10 (remember “…” is inclusive!).
  * If the condition (that the number must be even) is met, adding it to the array.

  The above code is imperative in nature. The instructions tell the computer how to locate the even numbers by giving it explicit instructions that use basic control structures, in this case if and for-in.

  In functional way:

  ```Swift
  func isEven(number: Int) -> Bool {
  return number % 2 == 0
  }
  evens = Array(1...10).filter(isEven)
  println(evens)
  ```

  The functional version of this code is certainly more concise than the imperative equivalent. This simple example exhibits a few interesting features that are common to all functional languages:

  1. Higher-order functions: These are functions that you pass as arguments to other functions. In this simple example, filter requires that you pass a higher-order function.
  2. First-class functions: You can treat functions just like any other variable; you can assign them to variables and pass them as arguments to other functions.
  3. Closures: These are effectively anonymous functions you create in-place.

  To know more about the functional programming in Swift. Please checking the references.

  References:
  
  <https://www.raywenderlich.com/82599/swift-functional-programming-tutorial>

  <https://news.realm.io/news/functional-programming-swift-chris-eidhof/>

---
[Go back to README.md](README.md)
