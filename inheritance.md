# Inheritance / extension

[Go back to README.md](README.md)

* JAVA

  JAVA supports the [inheritance](https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming)), which means that classes can be derived from other classes and inheriting the fields and methods defined in those classes.

  The class that derived from other classes is called subclass, and class where the subclass derived is called superclass.

  There is a example of inheritance that from JAVA documentation.

  ```JAVA
      public class Bicycle {

        // the Bicycle class has three fields
        public int cadence;
        public int gear;
        public int speed;

        // the Bicycle class has one constructor
        public Bicycle(int startCadence, int startSpeed, int startGear) {
        gear = startGear;
        cadence = startCadence;
        speed = startSpeed;
    }

      // the Bicycle class has four methods
      public void setCadence(int newValue) {
        cadence = newValue;
    }

      public void setGear(int newValue) {
        gear = newValue;
    }

      public void applyBrake(int decrement) {
        speed -= decrement;
    }

      public void speedUp(int increment) {
        speed += increment;
    }

  }
    ```

  In the class of **Bicycle**, there are three fields (cadence,gear,speed), one constructor and four methods (setCadence, setGear, applyBrake and speedUp). As a result, the subclasses of **Bicycle** will have these four fields and methods, and they do not have to repeat the code. In addition, they can also add more fields, methods and use the constructor of **Bicycle** to build new constructor.

  The following are what you can do in the subclass:

  * The inherited fields can be used directly, just like any other fields.
  * You can declare a field in the subclass with the same name as the one in the superclass, thus hiding it (not recommended).
  * You can declare new fields in the subclass that are not in the superclass.
  * The inherited methods can be used directly as they are.
  * You can write a new instance method in the subclass that has the same signature as the one in the superclass, thus overriding it.
  * You can write a new static method in the subclass that has the same signature as the one in the superclass, thus hiding it.
  * You can declare new methods in the subclass that are not in the superclass.
  * You can write a subclass constructor that invokes the constructor of the superclass, either implicitly or by using the keyword super.

  Here is a example of a subclass.

  ```JAVA
  public class MountainBike extends Bicycle {

    // the MountainBike subclass adds one field
    public int seatHeight;

    // the MountainBike subclass has one constructor
    public MountainBike(int startHeight,
                        int startCadence,
                        int startSpeed,
                        int startGear) {
        super(startCadence, startSpeed, startGear);
        seatHeight = startHeight;
    }   

    // the MountainBike subclass adds one method
    public void setHeight(int newValue) {
        seatHeight = newValue;
    }   
  }
  ```

  As can be seen in the subclass **MountainBike**, an new field (seatHeight) and a method (setHeight) are defined. It also show how to use **super** keyword to invoke a superclass's constructor. With super(), the superclass no-argument constructor is called. With super(parameter list), the superclass constructor with a matching parameter list is called.

  Notice: Invocation of a superclass constructor must be the first line in the subclass constructor.

  JAVA supports the multiple inheritance of type, which means that a class can implement more than one interface so that a class has multiple types. However, in JAVA, a class can only inherit one superclass.

  References:
  <https://docs.oracle.com/javase/tutorial/java/IandI/subclasses.html>
  <https://docs.oracle.com/javase/tutorial/java/IandI/super.html>
  <https://docs.oracle.com/javase/tutorial/java/IandI/multipleinheritance.html>


---

* Swift

  Swift supports both inheritance and extension.

  In swift, a class that does not inherit any class is called base class.

  Here is a example of base class called Vehicle:

  ```Swift
  class Vehicle {
    var currentSpeed = 0.0
    var description: String {
        return "traveling at \(currentSpeed) miles per hour"
    }
    func makeNoise() {
        // do nothing - an arbitrary vehicle doesn't necessarily make a noise
    }
}
  ```

  To realize the inheritance, a subclass need to be defined.

  Like Java, the subclass in Swift can inherit characteristics from the existing class and new characteristics can also be defined in subclass.

  There is a subclass **Bicycle** of **Vehicle**.

  ```Swift
  class Bicycle: Vehicle {
    var hasBasket = false
  }
  ```

  Users can override the methods and properties in the subclass. Users need to prefix overriding definition with the **override** keyword. Overriding by accident can cause unexpected behavior, and any overrides without the override keyword are diagnosed as an error when your code is compiled.

  ```Swift
  class Train: Vehicle {
    override func makeNoise() {
        print("Choo Choo")
    }
  }
  ```

  In Swift, users can also access the superclass version of a method, property, or subscript by using the **super** prefix.

  Extension are also supported by Swift. Extension in swift can:
  * Add computed instance properties and computed type properties
  * Define instance methods and type methods
  * Provide new initializers
  * Define subscripts
  * Define and use new nested types
  * Make an existing type conform to a protocol

  To declare extensions, the **extension** keyword is needed.

  ```Swift
  extension SomeType {
    // new functionality to add to SomeType goes here
  }
  ```

  An extension can also extend an existing type to make it adopt one or more protocols.

  ```Swift
  extension SomeType: SomeProtocol, AnotherProtocol {
    // implementation of protocol requirements goes here
  }
  ```

  References:
  <https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/Inheritance.html>
  <https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/Extensions.html>


---

[Go back to README.md](README.md)
