# Interfaces / protocols

[Go back to README.md](README.md)

## What does the language support?
* Java

  JAVA supports the interfaces.

  A common interface is a group of related methods with empty bodies. Implementing an interface allows class to become more formal about the behavior it promises to provide. If a class claims that it implement an interface, all methods defined in the interface must appear in the source code before the class will successfully compile.

  References:
  <https://docs.oracle.com/javase/tutorial/java/concepts/interface.html>

---
* Swift

  Swift supports the protocols.

  A protocols is a blueprint of methods, properties, and other requirements that suit a particular task or piece of functionality. The protocols can be adopted by a class, structure, or enumeration to provide an actual implements of those requirements. Users can also extend a protocol to implement some of these requirements or to implement additional functionality that conforming types can take advantage of.

  References:
  <https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/Protocols.html>


## What abilities does it have?

* Java

  An interface is declared using the JAVA **interface** keyword. It can be declared **public** or **package** scope.

  ```JAVA
  public interface MyInterface {

  public String hello = "Hello";

  public void sayHello();
  }
  ```

  Here is a example of a interface declared in JAVA. A ability that JAVA has is that the variable can be accessed directly from the interface like a static variable, like this:

  ```JAVA
  System.out.println(MyInterface.hello);
  ```
  JAVA interfaces are the ways to achieve [polymorphism](https://en.wikipedia.org/wiki/Polymorphism_(computer_science)). Polymorphism is a concept that takes some practice and thought to master. Basically, polymorphism means that an instance of an class (an object) can be used as if it were of different types.

  References:
  <http://tutorials.jenkov.com/java/interfaces.html>

---

* Swift

  Protocols can specify particular class type properties or instance property. They can also the type or instance property alone rather than specifying whether it is a stored or computed property.

  There are some abilities that Swift protocols have:

  * Initializer Requirements
  Swing allows the user to initialize protocols to follow type conformance similar to that of normal initializers.

    Syntax:

    ```Swift
    protocol SomeProtocol {
      init(someParameter: Int)
    }
  ```

  * Protocol Initializer Requirements
  Designated or convenience initializer allows the user to initialize a protocol to conform its standard by the reserved 'required' keyword.

  * Extension
  Existing type can be adopted and conformed to a new protocol by making use of extensions.

    Here is a example:

    ```Swift
    protocol AgeClasificationProtocol {
   var age: Int { get }
   func agetype() -> String
  }

    class Person {
   let firstname: String
   let lastname: String
   var age: Int
   init(firstname: String, lastname: String) {
      self.firstname = firstname
      self.lastname = lastname
      self.age = 10
   }
}

    extension Person : AgeClasificationProtocol {
    func agetype() -> String {
      //other code
    }
  }
    ```

  4. Composition

    Swift allows multiple protocols to be called at once with the help of protocol composition.

    Syntax:
    ```Swift
    protocol<SomeProtocol, AnotherProtocol>
    ```

  References:
  <http://www.tutorialspoint.com/swift/swift_protocols.htm>


## How is it used?

* Java

  Definition of the JAVA

  ```JAVA
  interface Bicycle {

    void changeCadence(int newValue);

    void changeGear(int newValue);

    void speedUp(int increment);

    void applyBrakes(int decrement);
}
  ```

  To implement the interfaces, in the declaration of a class, the **implements** keyword need to be used.

  ```JAVA
  class ACMEBicycle implements Bicycle {

    int cadence = 0;
    int speed = 0;
    int gear = 1;

   // The compiler will now require that methods
   // changeCadence, changeGear, speedUp, and applyBrakes
   // all be implemented. Compilation will fail if those
   // methods are missing from this class.

    void changeCadence(int newValue) {
         cadence = newValue;
    }

    void changeGear(int newValue) {
         gear = newValue;
    }

    void speedUp(int increment) {
         speed = speed + increment;   
    }

    void applyBrakes(int decrement) {
         speed = speed - decrement;
    }

    void printStates() {
         System.out.println("cadence:" +
             cadence + " speed:" +
             speed + " gear:" + gear);
    }
}

  ```

  References:
  <https://docs.oracle.com/javase/tutorial/java/concepts/interface.html>
---
* Swift

  Definition of the Swift:

  ```Swift
  protocol SomeProtocol {
   // protocol definition
  }
  ```

  Declaration:

  The protocols of Swift are declared after the class, structure or enumeration type names.

  Single and Multiple protocols declarations are both possible. Multiple protocols need to be separated by commas.

  ```Swift

  struct SomeStructure: Protocol1, Protocol2 {
   // structure definition
  }

  // if a superclass uses protocols, in the declaration of the subclass, the protocols also need to follow the superclass name with commas

  class SomeClass: SomeSuperclass, Protocol1, Protocol2 {
   // class definition
  }
  ```

  References:
  <http://www.tutorialspoint.com/swift/swift_protocols.htm>

---
[Go back to README.md](README.md)
