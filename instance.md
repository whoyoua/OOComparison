# Instance reference name in data type (class)

[Go back to README.md](README.md)

## this? or self?

* JAVA

  Within an instance method or a constructor, this is a reference to the current object — the object whose method or constructor is being called. You can refer to any member of the current object from within an instance method or a constructor by using this.

  * Using this with a Field
  The most common reason for using the this keyword is because a field is shadowed by a method or constructor parameter.

  For example, the **Point** class was written like this:

  ```JAVA
  public class Point {
    public int x = 0;
    public int y = 0;

    //constructor
    public Point(int a, int b) {
        x = a;
        y = b;
    }
  }
  ```

  but it could have been written like this:

  ```JAVA
  public class Point {
    public int x = 0;
    public int y = 0;

    //constructor
    public Point(int x, int y) {
        this.x = x;
        this.y = y;
    }
  }
  ```

  Each argument to the constructor shadows one of the object's fields — inside the constructor x is a local copy of the constructor's first argument. To refer to the Point field x, the constructor must use this.x.

  * Using this with a Constructor

  From within a constructor, you can also use the this keyword to call another constructor in the same class. Doing so is called an explicit constructor invocation. Here's another Rectangle class, with a different implementation from the one in the Objects section.

  ```JAVA
  public class Rectangle {
    private int x, y;
    private int width, height;

    public Rectangle() {
        this(0, 0, 1, 1);
    }
    public Rectangle(int width, int height) {
        this(0, 0, width, height);
    }
    public Rectangle(int x, int y, int width, int height) {
        this.x = x;
        this.y = y;
        this.width = width;
        this.height = height;
    }
  }
  ```

  This class contains a set of constructors. Each constructor initializes some or all of the rectangle's member variables. The constructors provide a default value for any member variable whose initial value is not provided by an argument. For example, the no-argument constructor creates a 1x1 Rectangle at coordinates 0,0. The two-argument constructor calls the four-argument constructor, passing in the width and height but always using the 0,0 coordinates. As before, the compiler determines which constructor to call, based on the number and the type of arguments.

  References:
  <https://docs.oracle.com/javase/tutorial/java/javaOO/thiskey.html>

---
* Swift

  Every instance of a type has an implicit property called self, which is exactly equivalent to the instance itself. You use the self property to refer to the current instance within its own instance methods.

  For example, there is a **Counter** class like this:

  ```Swift
  class Counter {
      var count = 0
      func increment() {
          count += 1
      }
      func increment(by amount: Int) {
          count += amount
      }
      func reset() {
          count = 0
      }
  }
  ```

  The increment() method, could have been written like this by using **self** key word:

  ```Swift
  func increment() {
    self.count += 1
  }
  ```

  If users don’t explicitly write self, Swift assumes that users are referring to a property or method of the current instance whenever you use a known property or method name within a method. This assumption is demonstrated by the use of count (rather than self.count) inside the three instance methods for Counter.

  The main exception to this rule occurs when a parameter name for an instance method has the same name as a property of that instance. In this situation, the parameter name takes precedence, and it becomes necessary to refer to the property in a more qualified way. You use the self property to distinguish between the parameter name and the property name.

  Here, self disambiguates between a method parameter called x and an instance property that is also called x:

  ```Swift
  struct Point {
    var x = 0.0, y = 0.0
    func isToTheRightOf(x: Double) -> Bool {
        return self.x > x
    }
  }
  let somePoint = Point(x: 4.0, y: 5.0)
  if somePoint.isToTheRightOf(x: 1.0) {
    print("This point is to the right of the line  where x == 1.0")
  }
  // Prints "This point is to the right of the line where x == 1.0"
  ```

  Without the self prefix, Swift would assume that both uses of x referred to the method parameter called x.

  References:
  <https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/Methods.html>

---

[Go back to README.md](README.md)
