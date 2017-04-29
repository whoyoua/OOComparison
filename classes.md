# Classes

[Go back to README.md](README.md)


## Defining

* JAVA

  The introduction to object-oriented concepts in the lesson titled Object-oriented Programming Concepts used a bicycle class as an example, with racing bikes, mountain bikes, and tandem bikes as subclasses. Here is sample code for a possible implementation of a Bicycle class.

```JAVA
    public class Bicycle {

    // the Bicycle class has
    // three fields
    public int cadence;
    public int gear;
    public int speed;

    // the Bicycle class has
    // one constructor
    public Bicycle(int startCadence, int startSpeed, int startGear) {
        gear = startGear;
        cadence = startCadence;
        speed = startSpeed;
    }

    // the Bicycle class has
    // four methods
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

  A class named MountainBike, which is a subclass of Bicycle like this:

  ```JAVA
    public class MountainBike extends Bicycle {

    // the MountainBike subclass has
    // one field
    public int seatHeight;

    // the MountainBike subclass has
    // one constructor
    public MountainBike(int startHeight, int startCadence,
                        int startSpeed, int startGear) {
        super(startCadence, startSpeed, startGear);
        seatHeight = startHeight;
    }   

    // the MountainBike subclass has
    // one method
    public void setHeight(int newValue) {
        seatHeight = newValue;
    }   

}
```

   The following are four parts of defining a class in JAVA:

   1. Declaring Classes

   ```Java
   class MyClass {
       // field, constructor, and
       // method declarations
   }
   ```

   This is a class declaration. The class body (the area between the braces) contains all the code that provides for the life cycle of the objects created from the class: constructors for initializing new objects, declarations for the fields that provide the state of the class and its objects, and methods to implement the behavior of the class and its objects.

   The MyClass' declaration is a minimal one. It contains only those components of a class declaration that are required.

   However,you can provide more information about the class, such as the name of its superclass, whether it implements any interfaces, and so on, at the start of the class declaration. For example,

   ```JAVA
   class MyClass extends MySuperClass implements YourInterface {
       // field, constructor, and
       // method declarations
   }
   ```

   The new MyClass is the subclass of the MySuperClass and implements the YourInterface interface.

   The modifiers like public or private also can be added to class declarations to determine what other classes can access MyClass.

   In general, class declarations can include these components, in order:

    * Modifiers such as public, private, and a number of others that you will encounter later.
    * The class name, with the initial letter capitalized by convention.
    * The name of the class's parent (superclass), if any, preceded by the keyword extends. A class can only extend (subclass) one parent.
    * A comma-separated list of interfaces implemented by the class, if any, preceded by the keyword implements. A class can implement more than one interface.
    * The class body, surrounded by braces, {}.

   References:
   <https://docs.oracle.com/javase/tutorial/java/javaOO/classdecl.html>

   2. Declaring Member Variables

   To defining a class, there are three kings of variables can be used:

    * Member variables in a class—these are called fields.
    * Variables in a method or block of code—these are called local variables.
    * Variables in method declarations—these are called parameters.

    The Field declarations are composed of three components, in order:

    1. Zero or more modifiers, such as public or private.
    2. The field's type.
    3. The field's name.

    References:
    <https://docs.oracle.com/javase/tutorial/java/javaOO/variables.html>

  3. Defining Methods

  Here is a example of defining a method:

  ```JAVA
  public double calculateAnswer(double wingSpan, int numberOfEngines,double length, double grossTons) {
    //do the calculation here
}
  ```

  The only required elements of a method declaration are the method's **return type**, **name**, a pair of **parentheses**, **()**, and a **body between braces**, **{}**.

  More generally, method declarations have six components, in order:

    1. Modifiers—such as public, private, and others you will learn about later.
    2. The return type—the data type of the value returned by the method, or void if the method does not return a value.
    3. The method name—the rules for field names apply to method names as well, but the convention is a little different.
    4. The parameter list in parenthesis—a comma-delimited list of input parameters, preceded by their data types, enclosed by parentheses, (). If there are no parameters, you must use empty parentheses.
    5. An exception list-used to throw exceptions when catch them.
    6. The method body, enclosed between braces—the method's code, including the declaration of local variables, goes here.

  References:
  <https://docs.oracle.com/javase/tutorial/java/javaOO/methods.html>

  4. Providing Constructors for Your Classes

  A class contains constructors that are invoked to create objects from the class blueprint. Constructor declarations look like method declarations—except that they use the name of the class and have no return type. For example, Bicycle has one constructor:

  ```JAVA
  public Bicycle(int startCadence, int startSpeed, int startGear) {
    gear = startGear;
    cadence = startCadence;
    speed = startSpeed;
  }
  ```


  References:
  <https://docs.oracle.com/javase/tutorial/java/javaOO/constructors.html>

---

* Swift

  Classes in Swift are building blocks of flexible constructs. Similar to constants, variables and functions the user can define class properties and methods. Swift provides the functionality that while declaring classes the users need not create interfaces or implementation files. Swift allows to create classes as a single file and the external interfaces will be created by default once the classes are initialized.

  Common Characteristics of Classes and structures
  * Properties are defined to store values
  * Subscripts are defined for providing access to values
  * Methods are initialized to improve functionality
  * Initial state are defined by initializers
  * Functionality are expanded beyond default values
  * Confirming protocol functionality standards

  Here is a simple definition of a class in Swift:

  ```Swift
  class student {
   var studname: String
   var mark: Int
   var mark2: Int
  }
  ```

  In Swift, a class is also a blueprint defining the data and behavior of a type. An object is an instance of a class created dynamically with a block of memory allocated. Properties, Methods, Fields are the members of a class.

  ```Swift
  //Class Definition
  class Employee
  {
    //Property
    //Similar to a var but declared in a class.
    var name: String

    //Property with getter and setter
    var employeeName : String {
        get {
            return name
        }
        set {
            name = newValue
        }
    }

    //Initializer or Constructor
    init(name: String) {
        //self is similar to 'this' in C#
        self.name = name
    }

    //Method
    func getEmployee() -> String {
    return employeeName
    }

    //DeInitializer
    deinit
    {

    }

  }
  //Instance Creation - Object
  var employee = Employee(name: "Jones")
  var employeeName = employee.getEmployee()
  print("Employee is \(employeeName)")
  ```

  References:
  <http://www.tutorialspoint.com/swift/swift_classes.htm>
  <https://developer.ibm.com/swift/2016/02/25/swift-for-c-developers/>


## Creating new instances

* JAVA

  A class provides the blueprint for objects; you create an object from a class. Each of the following statements taken from the [CreateObjectDemo](code/CreateObjectDemo.java) program creates an object and assigns it to a variable:

  ```JAVA
  Point originOne = new Point(23, 94);
  Rectangle rectOne = new Rectangle(originOne, 100, 200);
  Rectangle rectTwo = new Rectangle(50, 100);
  ```

  The first line creates an object of the Point class, and the second and third lines each create an object of the Rectangle class.

  In general, each of these statements has three parts (discussed in detail below):

  1. Declaration: The code set in bold are all variable declarations that associate a variable name with an object type.
  2. Instantiation: The new keyword is a Java operator that creates the object.
  3. Initialization: The new operator is followed by a call to a constructor, which initializes the new object.

---
* Swift

  Here’s an example of a class definition:

  ```Swift
  class VideoMode {
    var resolution = Resolution()
    var interlaced = false
    var frameRate = 0.0
    var name: String?
  }
  ```
  The VideoMode class definition only describe what a VideoMode will look like. They themselves do not describe a specific resolution or video mode.

  To do that, users need to create an instance of the structure or class.

  let someVideoMode = VideoMode()

  Classes use initializer syntax for new instances. The simplest form of initializer syntax uses the type name of the class or structure followed by empty parentheses, such as VideoMode(). This creates a new instance of the class or structure, with any properties initialized to their default values.

  References:
  <https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/ClassesAndStructures.html#//apple_ref/doc/uid/TP40014097-CH13-ID82>


## Constructing/initializing

* JAVA

  The way of the constructors can be seen in the first part, ***Defining***.

  To create a new Bicycle object called myBike, a constructor is called by the new operator:

  ```JAVA
  Bicycle myBike = new Bicycle(30, 0, 8);
  ```

  new Bicycle(30, 0, 8) creates space in memory for the object and initializes its fields.

  Although Bicycle only has one constructor, it could have others, including a no-argument constructor:

  ```JAVA
  public Bicycle() {
  gear = 1;
  cadence = 10;
  speed = 0;
  }
  ```

  Bicycle yourBike = new Bicycle(); invokes the no-argument constructor to create a new Bicycle object called yourBike.

  Both constructors could have been declared in Bicycle because they have different argument lists. As with methods, the Java platform differentiates constructors on the basis of the number of arguments in the list and their types. Users cannot write two constructors that have the same number and type of arguments for the same class, because the platform would not be able to tell them apart. Doing so causes a compile-time error.

  Users can use a superclass constructor. The MountainBike class at ***Defining*** did just that. Users can also use access modifiers in a constructor's declaration to control which other classes can call the constructor.

  References:
  <https://docs.oracle.com/javase/tutorial/java/javaOO/constructors.html>

---

* Swift

  Initialization is the process of preparing an instance of a class, structure, or enumeration for use. This process involves setting an initial value for each stored property on that instance and performing any other setup or initialization that is required before the new instance is ready for use.

  Users implement this initialization process by defining initializers, which are like special methods that can be called to create a new instance of a particular type. Unlike Objective-C initializers, Swift initializers do not return a value. Their primary role is to ensure that new instances of a type are correctly initialized before they are used for the first time.

  Classes and structures must set all of their stored properties to an appropriate initial value by the time an instance of that class or structure is created. Stored properties cannot be left in an indeterminate state.

  Users can set an initial value for a stored property within an initializer, or by assigning a default property value as part of the property’s definition. These actions are described in the following sections.

  Initializers are called to create a new instance of a particular type. In its simplest form, an initializer is like an instance method with no parameters, written using the **init** keyword:

  ```Swift
  init() {
    // perform some initialization here
  }
  ```
  * Customizing Initialization

    Users can customize the initialization process with input parameters and optional property types, or by assigning constant properties during initialization, as described in the following sections.

    * Initialization Parameters

    Users can provide initialization parameters as part of an initializer’s definition, to define the types and names of values that customize the initialization process. Initialization parameters have the same capabilities and syntax as function and method parameters.

    The following example defines a structure called **Celsius**, which stores temperatures expressed in degrees Celsius. The **Celsius** structure implements two custom initializers called **init(fromFahrenheit:)** and **init(fromKelvin:)**, which initialize a new instance of the structure with a value from a different temperature scale:

    ```Swift
    struct Celsius {
    var temperatureInCelsius: Double
    init(fromFahrenheit fahrenheit: Double) {
        temperatureInCelsius = (fahrenheit - 32.0) / 1.8
    }
    init(fromKelvin kelvin: Double) {
        temperatureInCelsius = kelvin - 273.15
    }
    }
    let boilingPointOfWater = Celsius(fromFahrenheit: 212.0)
    // boilingPointOfWater.temperatureInCelsius is 100.0
    let freezingPointOfWater = Celsius(fromKelvin: 273.15)
    // freezingPointOfWater.temperatureInCelsius is 0.0
    ```

    * Parameter Names and Argument Labels

    As with function and method parameters, initialization parameters can have both a parameter name for use within the initializer’s body and an argument label for use when calling the initializer.

    However, initializers do not have an identifying function name before their parentheses in the way that functions and methods do. Therefore, the names and types of an initializer’s parameters play a particularly important role in identifying which initializer should be called. Because of this, Swift provides an automatic argument label for every parameter in an initializer if you don’t provide one.

    The following example defines a structure called Color, with three constant properties called red, green, and blue. These properties store a value between 0.0 and 1.0 to indicate the amount of red, green, and blue in the color.

    Color provides an initializer with three appropriately named parameters of type Double for its red, green, and blue components. Color also provides a second initializer with a single white parameter, which is used to provide the same value for all three color components.

    ```Swift
    struct Color {
    let red, green, blue: Double
    init(red: Double, green: Double, blue: Double) {
        self.red   = red
        self.green = green
        self.blue  = blue
    }
    init(white: Double) {
        red   = white
        green = white
        blue  = white
    }
    }
    ```

    Both initializers can be used to create a new Color instance, by providing named values for each initializer parameter:

    ```Swift
    let magenta = Color(red: 1.0, green: 0.0, blue: 1.0)
    let halfGray = Color(white: 0.5)
    ```


    * Initializer Parameters Without Argument Labels

    If users do not want to use an argument label for an initializer parameter, write an underscore **_** instead of an explicit argument label for that parameter to override the default behavior.

    ```Swift
    init(_ celsius: Double) {
        temperatureInCelsius = celsius
    }
    ```
    * Optional Property Types

    If users custom type has a stored property that is logically allowed to have “no value”—perhaps because its value cannot be set during initialization, or because it is allowed to have “no value” at some later point—declare the property with an optional type. Properties of optional type are automatically initialized with a value of **nil**, indicating that the property is deliberately intended to have “no value yet” during initialization.

    The following example defines a class called **SurveyQuestion**, with an optional String property called **response**:

    ```Swift
    class SurveyQuestion {
    var text: String
    var response: String?
    init(text: String) {
        self.text = text
    }
    func ask() {
        print(text)
    }
    }
    let cheeseQuestion = SurveyQuestion(text: "Do you like cheese?")
    cheeseQuestion.ask()
    // Prints "Do you like cheese?"
    cheeseQuestion.response = "Yes, I do like cheese."
    ```

    The response to a survey question cannot be known until it is asked, and so the **response** property is declared with a type of **String?**, or “optional **String**”. It is automatically assigned a default value of **nil**, meaning “no string yet”, when a new instance of **SurveyQuestion** is initialized.

  * Default Initializers

    Swift provides a default initializer for any structure or class that provides default values for all of its properties and does not provide at least one initializer itself. The default initializer simply creates a new instance with all of its properties set to their default values.

    This example defines a class called *ShoppingListItem*, which encapsulates the name, quantity, and purchase state of an item in a shopping list:

    ```Swift
    class ShoppingListItem {
    var name: String?
    var quantity = 1
    var purchased = false
    }
    var item = ShoppingListItem()
    ```

    Because all properties of the **ShoppingListItem** class have default values, and because it is a base class with no superclass, **ShoppingListItem** automatically gains a default initializer implementation that creates a new instance with all of its properties set to their default values. (The name property is an optional **String** property, and so it automatically receives a default value of **nil**, even though this value is not written in the code.) The example above uses the default initializer for the **ShoppingListItem** class to create a new instance of the class with initializer syntax, written as **ShoppingListItem()**, and assigns this new instance to a variable called item.

    References:
    <https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/Initialization.html#//apple_ref/doc/uid/TP40014097-CH18-ID203>




## Destructing/de-initializing

* JAVA

  Java is garbage-collected, so users do not need destructing.

  There is a **finalize** method, but the VM specification does allow for VM implementations to never call them. Generally speaking the code in the finalize() method of any object can be called by the VM before the object is garbage collected, but as this is not mandatory.

  The following are some introduction of **finalize** method.

  ```JAVA
  protected void finalize() throws Throwable
  ```

  Called by the garbage collector on an object when garbage collection determines that there are no more references to the object. A subclass overrides the **finalize** method to dispose of system resources or to perform other cleanup.

  The general contract of finalize is that it is invoked if and when the JavaTM virtual machine has determined that there is no longer any means by which this object can be accessed by any thread that has not yet died, except as a result of an action taken by the finalization of some other object or class which is ready to be finalized. The finalize method may take any action, including making this object available again to other threads; the usual purpose of finalize, however, is to perform cleanup actions before the object is irrevocably discarded. For example, the finalize method for an object that represents an input/output connection might perform explicit I/O transactions to break the connection before the object is permanently discarded.

  The Java programming language does not guarantee which thread will invoke the finalize method for any given object. It is guaranteed, however, that the thread that invokes finalize will not be holding any user-visible synchronization locks when finalize is invoked. If an uncaught exception is thrown by the finalize method, the exception is ignored and finalization of that object terminates.

  After the finalize method has been invoked for an object, no further action is taken until the Java virtual machine has again determined that there is no longer any means by which this object can be accessed by any thread that has not yet died, including possible actions by other objects or classes which are ready to be finalized, at which point the object may be discarded.

  References:
  <https://docs.oracle.com/javase/7/docs/api/java/lang/Object.html#finalize()>

---

* Swift

  Swift automatically deallocates your instances when they are no longer needed, to free up resources. Swift handles the memory management of instances through automatic reference counting (ARC), as described in [Automatic Reference Counting](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/AutomaticReferenceCounting.html#//apple_ref/doc/uid/TP40014097-CH20-ID48).

  Typically you don’t need to perform manual cleanup when your instances are deallocated. However, when you are working with your own resources, you might need to perform some additional cleanup yourself. For example, if you create a custom class to open a file and write some data to it, you might need to close the file before the class instance is deallocated.

  Class definitions can have at most one deinitializer per class. The deinitializer does not take any parameters and is written without parentheses:

  ```Swift
  deinit {
    // perform the deinitialization
  }
  ```

  Deinitializers are called automatically, just before instance deallocation takes place. You are not allowed to call a deinitializer yourself. Superclass deinitializers are inherited by their subclasses, and the superclass deinitializer is called automatically at the end of a subclass deinitializer implementation. Superclass deinitializers are always called, even if a subclass does not provide its own deinitializer.

  Because an instance is not deallocated until after its deinitializer is called, a deinitializer can access all properties of the instance it is called on and can modify its behavior based on those properties (such as looking up the name of a file that needs to be closed).

  * Deinitializers in Action

  Here’s an example of a deinitializer in action. This example defines two new types, **Bank** and **Player**, for a simple game. The **Bank** class manages a made-up currency, which can never have more than 10,000 coins in circulation. There can only ever be one Bank in the game, and so the Bank is implemented as a class with type properties and methods to store and manage its current state:

  ```Swift
  class Bank {
    static var coinsInBank = 10_000
    static func distribute(coins numberOfCoinsRequested: Int) -> Int {
        let numberOfCoinsToVend = min(numberOfCoinsRequested, coinsInBank)
        coinsInBank -= numberOfCoinsToVend
        return numberOfCoinsToVend
    }
    static func receive(coins: Int) {
        coinsInBank += coins
    }
  }
  ```

  Bank keeps track of the current number of coins it holds with its **coinsInBank** property. It also offers two methods—**distribute(coins:)** and **eceive(coins:)**—to handle the distribution and collection of coins.

  The **distribute(coins:)** method checks that there are enough coins in the bank before distributing them. If there are not enough coins, Bank returns a smaller number than the number that was requested (and returns zero if no coins are left in the bank). It returns an integer value to indicate the actual number of coins that were provided.

  The **receive(coins:)** method simply adds the received number of coins back into the bank’s coin store.

  The **Player** class describes a player in the game. Each player has a certain number of coins stored in their purse at any time. This is represented by the player’s **coinsInPurse** property:

  ```Swift
  class Player {
    var coinsInPurse: Int
    init(coins: Int) {
        coinsInPurse = Bank.distribute(coins: coins)
    }
    func win(coins: Int) {
        coinsInPurse += Bank.distribute(coins: coins)
    }
    deinit {
        Bank.receive(coins: coinsInPurse)
    }
  }
  ```

  Each Player instance is initialized with a starting allowance of a specified number of coins from the bank during initialization, although a Player instance may receive fewer than that number if not enough coins are available.

  The Player class defines a win(coins:) method, which retrieves a certain number of coins from the bank and adds them to the player’s purse. The Player class also implements a deinitializer, which is called just before a Player instance is deallocated. Here, the deinitializer simply returns all of the player’s coins to the bank:

  ```Swift
  var playerOne: Player? = Player(coins: 100)
  print("A new player has joined the game with \(playerOne!.coinsInPurse) coins")
  // Prints "A new player has joined the game with 100 coins"
  print("There are now \(Bank.coinsInBank) coins left in the bank")
  // Prints "There are now 9900 coins left in the bank"
  ```

  A new Player instance is created, with a request for 100 coins if they are available. This Player instance is stored in an optional Player variable called playerOne. An optional variable is used here, because players can leave the game at any point. The optional lets you track whether there is currently a player in the game.

  Because playerOne is an optional, it is qualified with an exclamation mark (!) when its coinsInPurse property is accessed to print its default number of coins, and whenever its win(coins:) method is called:

  ```Swift
  playerOne!.win(coins: 2_000)
  print("PlayerOne won 2000 coins & now has \(playerOne!.coinsInPurse) coins")
  // Prints "PlayerOne won 2000 coins & now has 2100 coins"
  print("The bank now only has \(Bank.coinsInBank) coins left")
  // Prints "The bank now only has 7900 coins left"
  ```

  Here, the player has won 2,000 coins. The player’s purse now contains 2,100 coins, and the bank has only 7,900 coins left.

  ```Swift
  playerOne = nil
  print("PlayerOne has left the game")
  // Prints "PlayerOne has left the game"
  print("The bank now has \(Bank.coinsInBank) coins")
  // Prints "The bank now has 10000 coins"
  ```

  The player has now left the game. This is indicated by setting the optional playerOne variable to nil, meaning “no Player instance.” At the point that this happens, the playerOne variable’s reference to the Player instance is broken. No other properties or variables are still referring to the Player instance, and so it is deallocated in order to free up its memory. Just before this happens, its deinitializer is called automatically, and its coins are returned to the bank.

  References:
  <https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/Deinitialization.html#//apple_ref/doc/uid/TP40014097-CH19-ID142>

---

[Go back to README.md](README.md)
