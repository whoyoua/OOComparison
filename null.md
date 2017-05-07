# [Null/nil references](null.md)

[Go back to README.md](README.md)
## Which does the language use? (null/nil/etc)

* JAVA

  JAVA use **null** is a special type. The **null** reference is the only possible value of an expression of **null** type.The **null** reference can always be cast to any reference type.

  In addition, null is not a valid object instance. As a result, there is no memory allocated for it. It is simply a value that indicates that the object reference is not currently referring to an object.

  References:

  <http://stackoverflow.com/questions/2707322/what-is-null-in-java>

  <http://www.programcreek.com/2013/12/what-exactly-is-null-in-java/>
---

* Swift

  Swift use **nil**. In swift,  **nil** is a pointer, which is the absence of a value of a certain type. As a result, optionals of any type can be set to the **nil**.

  References:
  
  <http://stackoverflow.com/questions/24043589/null-nil-in-swift-language>

## Does the language have features for handling null/nil references?

* JAVA

  User can simply use **==** operator to determine whether a variable or a instance is null.

  There is also a exception called **NullPointerException**, which will be triggered when accessing the fields or calling the methods of a null references.

  References:

  <http://stackoverflow.com/questions/21950542/java-null-handling>

  <http://stackoverflow.com/questions/218384/what-is-a-nullpointerexception-and-how-do-i-fix-it>

---

* Swift

  Swift has two ways to handling the nil references.

  The first one is optionals chaining, which is a process for querying and calling properties or methods which might be **nil**. If a optional is **nil** or one of links in the chain is **nil**, the call will both return **nil**.

  The second one is using guard statement. If users unwrap the input values with guard, it will handle the **nil** the references and users do not have to deal with the **nil** values.

  References:

  <http://stackoverflow.com/questions/33276346/handling-nil-exceptions-in-swift-2-0>

  <https://thatthinginswift.com/guard-statement-swift/>

---
[Go back to README.md](README.md)
