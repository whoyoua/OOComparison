# Language Purpose

[Go back to README.md](README.md)

## 1. Why was the language created?

* JAVA

  [James Gosling](https://en.wikipedia.org/wiki/James_Gosling), [Mike Sheridan](https://en.wikipedia.org/wiki/Mike_Sheridan), and [Patrick Naughton](https://en.wikipedia.org/wiki/Patrick_Naughton) initiated the Java language project in June 1991.

  Java was originally designed for interactive television, but it was too advanced for the digital cable television industry at the time.The language was initially called Oak after an oak tree that stood outside Gosling's office. Later the project went by the name Green and was finally renamed Java, from Java coffee.

  Gosling designed Java with a C/C++-style syntax that system and application programmers would find familiar.

  Reference: <https://en.wikipedia.org/wiki/Java_(programming_language)>

---
* Swift

  Swift is designed to work with Apple's [Cocoa](https://en.wikipedia.org/wiki/Cocoa_(API) and [Cocoa Touch](Cocoa Touch) frameworks and the large body of extant [Objective-C (ObjC)](https://en.wikipedia.org/wiki/Objective-C) code written for Apple products. It is built with the open source LLVM compiler framework and has been included in Xcode since version 6. On platforms other than Linux, it uses the Objective-C runtime library which allows C, Objective-C, C++ and Swift code to run within one program.

  Reference: <https://en.wikipedia.org/wiki/Objective-C>

  According to [Chris Lattner](https://en.wikipedia.org/wiki/Chris_Lattner), director of Apple’s Developer Tools Department, the Swift programming language has only been in development since July 2010.

  While Apple could have justified the creation of Swift by simply saying, “hey, this is better than Obective-C” , Lattner claims that his motivations for the project were far bigger in scope: "I hope that by making programming more approachable and fun, we’ll appeal to the next generation of programmers and to help redefine how Computer Science is taught."

  Reference:
    <https://www.quora.com/Why-has-Apple-created-a-new-programming-language-in-Swift>



## 2. What problems was the language trying to address?

* JAVA

  An environment that allows programs to execute is called platform. The program that is compiled in one operating system if it is able to be executed in another operating system is called platform independent program and that language is called platform independent language.

  C and C++ does not provide platform in-dependency where as java is a platform independent language. Java is invented to support developing internet applications by providing platform in-dependency.That's why java programming language is introduced.

  Reference: <http://java-intellectual.blogspot.com/2011/09/why-java-programming-language-is.html>

---

* Swift

  The programming language Objective-C was originally developed in the early 1980s. It was selected as the main language used by [NeXT](https://en.wikipedia.org/wiki/NeXT) for its [NeXTSTEP](https://en.wikipedia.org/wiki/NeXTSTEP) operating system, from which OS X and iOS are derived.

  Portable Objective-C programs that do not use the Cocoa or Cocoa Touch libraries, or those using parts that may be ported or reimplemented for other systems, can also be compiled for any system supported by [GNU Compiler Collection (GCC)](https://en.wikipedia.org/wiki/GNU_Compiler_Collection) or [Clang](https://en.wikipedia.org/wiki/Clang).

## 3. Is the language a reaction to a previous language or a replacement for another language?

* JAVA

  C and C++ are being replaced by Java for many applications, but they would never become completely obsolete.

  Creating software that runs on multiple platforms is incredibly costly and time consuming. Software that is written in C or C++ has to be adapted and recompiled for each computer that it would run on. Quite often it is not a trivial task as C/C++ is very dependent on the library files and API’s used in the code. Java's multi-platform capability makes it a natural choice for use on the Internet. The Internet is used daily by millions of people on a wide array of computing platforms. Although Java's portability gives it a clear advantage over other languages, this feature also creates one of Java¹s biggest disadvantages - it's performance.

  The exceptions, garbage collection and automatic type checking features of languages like Java outweigh most of the performance penalties these languages have. However, C and C++ would live on, as they are needed for real-time applications where timing and performance are crucial. But, once Java closes the gap in performance, fewer applications would be written in C++. But C/C++ would never completely disappear, similarly to other languages like Fortran and Cobol, which are still being used by some companies.

|Tables|JAVA|C++|
  |------|----|---|
  |Inheritance|Single (but with mulitple subtyping)|Mutiple|
  |Preprocessor|No|Yes|
  |Separate Interface/Implementation|No(interface generated from code)|Yes|
  |Garbage Collection|Yes|No|
  |Operator Overloading|No|Yes|
  |Pointer Arithmetic|No|Yes|
  |Generics|No(but extensive polymorphism)|Yes(templates)|
  |Exceptions|Yes|Yes|
  |Native Multi-threading|Yes|No|

  Reference:
   <https://www.cs.rutgers.edu/~rmartin/teaching/spring03/cs553/papers01/04.pdf>


---

* Swift

  In June, 2014, Apple’s announced and launched its new programming language called Swift.

  The Worldwide Developer Conference(WWDC) event, also saw the release of a 550-page language guide, which appeared on Apple’s iBooks store.

  Apple's platforms used to use Objective-C as the main programming language, but with the creation of Swift, will the Objective-C be replaced by Swift?

  According to apple, the following are some of the highlights of Swift.
  * Closures (similar to blocks in C and Objective-C) unified with function pointers
  * Tuples and multiple return values
  * Generics
  * Fast and concise iteration over a range or collection
  * Structs that support methods, extensions, protocols.
  * Functional programming patterns, e.g.: map and filter

  Reference: <https://techcrunch.com/2014/06/02/apple-launches-swift-a-new-programming-language-for-writing-ios-and-os-x-apps/>

  As a result of the success of the Swift rollout and implementation, Objective-C has taken a severe dive in popularity.

  In its October 2015 report, [TIOBE](https://en.wikipedia.org/wiki/TIOBE_index) ranked Objective-C at 14 and Swift at 15.However, just a year prior, in the TIOBE October 2014 report, Objective-C was the 3rd most popular programming language in use. The drop to 14th overall this year represented a decline of 11 spots in the index. Objective-C lost its place in the Top 10, replaced by Ruby.

  In March 2017, less than three years after its official debut, Swift made the top 10 in the monthly TIOBE index ranking of popular programming languages.(<https://en.wikipedia.org/wiki/Swift_(programming_language)>)

  It can seen from the data that many coders have moved away from Objective-C to Swift, but Objective-C will still exist for a while. Most example codes, which are shared all over the world, are written in Objective-C. Many companies and the industry will keep using it before trying to use Swift. In addition, Objective-C is constantly being updated.

  Reference: <https://dzone.com/articles/objective-c-poised-for-swift-replacement-as-apples>

  There is a youtube video that compares Swift with Objective-C.
  [![IMAGE ALT TEXT HERE](http://img.youtube.com/vi/MIKA1W6c0eI/0.jpg)](http://www.youtube.com/watch?v=MIKA1W6c0eI)

[Go back to README.md](README.md)
