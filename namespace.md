# Name spaces

[Go back to README.md](README.md)

## How are name spaces implemented?

* JAVA

  JAVA uses packages and classes to implement the name spaces. A **package** is a named collection of classes (and possibly subpackages). Packages serve to group related classes and define a namespace for the classes they contain.

  The Java platform includes packages with names that begin with **java**, **javax**, and **org.omg**. (Sun also defines standard extensions to the Java platform in packages whose names begin with javax.)

  The most fundamental classes of the language are in the package java.lang. Various utility classes are in java.util. Classes for input and output are in java.io, and classes for networking are in java.net. Some of these packages contain subpackages. For example, java.lang contains two more specialized packages, named java.lang.reflect and java.lang.ref, and java.util contains a subpackage, java.util.zip, that contains classes for working with compressed ZIP archives.

  Every class has both a simple name, which is the name that is given in its definition, and a fully qualified name, which includes the name of the package of which it is a part.

  The **String class**, for example, is part of the **java.lang** package, so its fully qualified name is **java.lang.String**.

  So how to define a package?

  To specify the package a class is to be part of, you use a package directive. The **package** keyword, if it appears, must be the first token of Java code (i.e., the first thing other than comments and space) in the Java file. The keyword should be followed by the name of the desired package and a semicolon. Consider a file of Java code that begins with this directive:

  ```JAVA
  package com.davidflanagan.jude;
  ```

  All classes defined by this file are part of the package named com.davidflanagan.jude.

  If no package directive appears in a file of Java code, all classes defined in that file are part of a default unnamed package.

  Sun proposes a package-naming scheme, which guarantees globally unique package names. The scheme is to use  Internet domain name, with its elements reversed, as the prefix for all package names.

  For example, if there is a domain **davidflanagan.com**, so all my Java packages begin with **com.davidflanagan**.


  References:
  <https://docstore.mik.ua/orelly/java-ent/jnut/ch02_11.htm>

---

* Swift

  A **namespace** in Swift is a named region of a program. As such they provide virtual grouping within our code where things outside of the namespace cannot access things inside of the namespace without first mentioning the namespaces itself.

  This provides a virtual partitioning separating the names in one namespace from the names in another. It also allows two items to be declared with the same name as long as they are in different namespaces.

  In Swift, unlike in some other languages, the declaration of namespaces is **implicit**, which means that namespaces are not declared explicitly. Instead Swift creates a namespace at the boundary of each module. That means an app has it’s own namespace and any framework users write will have it’s own separate namespace.

  References:
  <https://andybargh.com/lifetime-scope-and-namespaces-in-swift/>

## How are name spaces used?

* JAVA

  In JAVA, name spaces are used by importing the classes and packages.

  A class in a package **p** can refer to any other class in **p** by its simple name. And, since the classes in the **java.lang** package are so fundamental to the Java language, any Java code can refer to any class in this package by its simple name. Thus, you can always type **String**, instead of **java.lang.String**.

  By default, however, you must use the fully qualified name of all other classes. So, if you want to use the **File** class of the **java.io** package, you must type **java.io.File**.

  Specifying package names explicitly all the time quickly gets tiring, so Java includes an import directive you can use to save some typing.

  **import** is used to specify classes and packages of classes that can be referred to by their simple names instead of by their fully qualified names. The import keyword can be used any number of times in a Java file, but all uses must be at the top of the file, immediately after the package directive, if there is one. There can be comments between the package directive and the import directives, but there cannot be any other Java code.

  The import directive is available in two forms.

  To specify a single class that can be referred to by its simple name, follow the import keyword with the name of the class and a semicolon:

  ```JAVA
  import java.io.File;    // Now we can type File instead of java.io.File
  ```

  To import an entire package of classes, follow import with the name of the package, the characters asterisk, and a semicolon. In addition, if you want to use several other classes from the java.io package, just simply import the entire package:

  ```JAVA
  import java.io.*;   // Now we can use simple names for all classes in java.io
  ```

  This package import syntax does not apply to subpackages. If you import the java.util package, you will still refer to the **java.util.zip.ZipInputStream** class by its fully qualified name.

  If two classes with the same name are both imported from different packages, neither one can be referred to by its simple name.

  As a result, to resolve this naming conflict unambiguously, you must use the fully qualified name of both classes.

  References:
  <https://docstore.mik.ua/orelly/java-ent/jnut/ch02_11.htm>

---

* Swift

  To access items in one namespace from the code in another, users must first import the module containing the item by using the **import** declaration. The import declaration in its most basic form, consists of the import keyword followed by the name of the module that users wish to import:

  ```Swift
  import ModuleName
  ```

  By default, this imports everything in the named module and makes it accessible in the code. In addition to the basic form though, users can also import specific symbols from a module.

  In this case, Swift can also use the **import** keyword and follow it with the kind of thing users want to **import** (class, function, variable etc), the name of the module users wish to import it from, and the name of the item users wish to import:

  ```Swift
  import itemType ModuleName.ItemName  
  ```

  When using this form, the item type can be one of:

  – typealias

  – struct

  – class

  – enum

  – protocol

  – var

  – func

  Then how to actually distinguish between two items with the same name in different namespaces?

  To access an item within a namespace, a period(.) is needed. The period separates the name of the namespace(essentially the module name) from the item that wishing to access and use this syntax to distinguish between two items in different namespaces. For example:

  ```Swift
  import class Foundation.NSString
  class NSString {
    var welcome = "Hello!"
  }
  var myStr = NSString() // Local NSString Class
  var otherStr = Foundation.NSString() // Foundation NSString Class.
  myStr.welcome
  ```

  One thing to not here is that as a shortcut, when accessing code that is in the same namespaces, Swift allows users to drop the namespaces prefix.

  In reality, it’s not that common to have to explicitly deal with namespaces in Swift. They are there as a convenience and provide a nice mechanism for protecting users from namespace clashes such as in the example above. The key thing to remember is that the namespaces in Swift are implicitly declared at the module boundaries.

  References:
  <https://andybargh.com/lifetime-scope-and-namespaces-in-swift/>

---

[Go back to README.md](README.md)
