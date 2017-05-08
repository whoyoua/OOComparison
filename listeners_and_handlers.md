# Implementation of listeners and event handlers
[Go back to README.md](README.md)

* JAVA

  There are three steps to implement the listeners and handlers. Here is a example of writting an Action Listener.

  1. Declare an event handler class and specify that the class either implements an listener interface or extends a class that implements an listener interface. For example:

  ```JAVA
    public class MyClass implements ActionListener {
    }
  ```

  2. Register an instance of the event handler class as a listener on one or more components. For example:

  ```JAVA
    someComponent.addActionListener(instanceOfMyClass);
  ```

  3. Include code that implements the methods in listener interface. For example:

  ```JAVA
    public void actionPerformed(ActionEvent e) {
      ...//code that reacts to the action...
    }
  ```

  Here is the whole program. [AL.java](code/AL.java)

  Some listener interfaces contain more than one method.

  For example, the **MouseListen** interface contains five methods: **mousePressed**, **mouseReleased**, **mouseEntered**, **mouseExited**, and **mouseClicked**. Even if you care only about mouse clicks, if your class directly implements **MouseListener**, then you must implement all five MouseListener methods. Methods for those events you do not care about can have empty bodies. Here is an example:

  ```JAVA
  //An example that implements a listener interface directly.
  public class MyClass implements MouseListener {
  ...
      someObject.addMouseListener(this);
  ...
  /* Empty method definition. */
  public void mousePressed(MouseEvent e) {
  }

  /* Empty method definition. */
  public void mouseReleased(MouseEvent e) {
  }

  /* Empty method definition. */
  public void mouseEntered(MouseEvent e) {
  }

  /* Empty method definition. */
  public void mouseExited(MouseEvent e) {
  }

  public void mouseClicked(MouseEvent e) {
      ...//Event listener implementation goes here...
  }
}
  ```

  References:

  <https://docs.oracle.com/javase/tutorial/uiswing/events/generalrules.html>

  <https://docs.oracle.com/javase/tutorial/uiswing/events/actionlistener.html>

---
* Swift

  Unlike the JAVA, Swift uses delegates to set the "listener" and "handler".

  Delegation is a design pattern that enables a class or structure to hand off (or delegate) some of its responsibilities to an instance of another type. This design pattern is implemented by defining a protocol that encapsulates the delegated responsibilities.

  Delegation can be used to respond to a particular action, or to retrieve data from an external source without needing to know the underlying type of that source

  Here is a example :

  ```Swift
    protocol DiceGame {
      var dice: Dice { get }
      func play()
    }

    protocol DiceGameDelegate {
      func gameDidStart(_ game: DiceGame)
      func game(_ game: DiceGame, didStartNewTurnWithDiceRoll diceRoll: Int)
      func gameDidEnd(_ game: DiceGame)
    }

    class SnakesAndLadders: DiceGame {
      let finalSquare = 25
      let dice = Dice(sides: 6, generator: LinearCongruentialGenerator())
      var square = 0
      var board: [Int]
      init() {
        board = Array(repeating: 0, count: finalSquare + 1)
        board[03] = +08; board[06] = +11; board[09] = +09; board[10] = +02
        board[14] = -10; board[19] = -11; board[22] = -02; board[24] = -08
      }
      var delegate: DiceGameDelegate?
      func play() {
        square = 0
        delegate?.gameDidStart(self)
        gameLoop: while square != finalSquare {
            let diceRoll = dice.roll()
            delegate?.game(self, didStartNewTurnWithDiceRoll: diceRoll)
            switch square + diceRoll {
              case finalSquare:
                break gameLoop
              case let newSquare where newSquare > finalSquare:
                continue gameLoop
              default:
                square += diceRoll
                square += board[square]
              }
            }
            delegate?.gameDidEnd(self)
          }
        }

        class DiceGameTracker: DiceGameDelegate {
        var numberOfTurns = 0
        func gameDidStart(_ game: DiceGame) {
            numberOfTurns = 0
            if game is SnakesAndLadders {
                print("Started a new game of Snakes and Ladders")
            }
            print("The game is using a \(game.dice.sides)-sided dice")
        }
        func game(_ game: DiceGame, didStartNewTurnWithDiceRoll diceRoll: Int) {
            numberOfTurns += 1
            print("Rolled a \(diceRoll)")
        }
        func gameDidEnd(_ game: DiceGame) {
            print("The game lasted for \(numberOfTurns) turns")
        }
      }
  ```

    This version is adapted to use a **Dice** instance for its dice-rolls, to adopt the **DiceGame** protocol, and to notify a **DiceGameDelegate** about its progress. Then it shows a class called **DiceGameTracker**, which dopts the **DiceGameDelegate** protocol.

    Here is how to use the **DiceGameTracker**:

    ```Swift
      let tracker = DiceGameTracker()
      let game = SnakesAndLadders()
      game.delegate = tracker
      game.play()
      // Started a new game of Snakes and Ladders
      // The game is using a 6-sided dice
      // Rolled a 3
      // Rolled a 5
      // Rolled a 4
      // Rolled a 5
      // The game lasted for 4 turns

    ```

    References:

    <https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/Protocols.html>

---
[Go back to README.md](README.md)
