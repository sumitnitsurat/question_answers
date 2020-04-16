1. Explain Solid Principles.

```
S.O.L.I.D Stands for 

    S - Single responsibility principle
    O - Open closed principle 
    L - Liskov substitution principle
    I - Interface segregation principle
    D - Dependency Inversion Principle

** - Single Responsibility Principle**

    A class should have one and only one reason to change, meaning that a class should have only one job.

** - Open-Closed Principle**

    Objects or entities should be open for extension, but closed for modification. You should be able to add more functionality by extending the class not by modifying itself.

** - Liskov substituion principle**

    Functions that use pointers or references to base classes must be able to use objects of derived classes without knowing it.

    Substitutability is a principle in object-oriented programming stating that, in a computer program, if S is a subtype of T, then objects of type T may be replaced with objects of type S

    ```
    let's do a simple example in Java:

    Bad example
    public class Bird{
        public void fly(){}
    }
    public class Duck extends Bird{}
    The duck can fly because of it is a bird, But what about this:

    public class Ostrich extends Bird{}
    Ostrich is a bird, But it can't fly, Ostrich class is a subtype of class Bird, But it can't use the fly method, that means that we are breaking LSP principle.

    Good example
    public class Bird{
    }
    public class FlyingBirds extends Bird{
        public void fly(){}
    }
    public class Duck extends FlyingBirds{}
    public class Ostrich extends Bird{} 
    ```

** - Interface segregation principle**

    A client should never be forced to implement an interface that it doesn't use or clients shouldn't be forced to depend on methods they do not use.

    ```
    interface ShapeInterface {
    public function area();
    public function volume();
    }
    ```

    square shape doesnt require volumen as its a flat shape. Segregate interfaec to two different interfaces.

** - Dependency Inversion principle**

    Entities must depend on abstractions not on concretions. It states that the high level module must not depend on the low level module, but they should depend on abstractions.

    ```
    class PasswordReminder {
    private $dbConnection;

    public function __construct(MySQLConnection $dbConnection) {
        $this->dbConnection = $dbConnection;
    }
    }
    ```

    class depending on MySQLConnection directly. any change in DB will result in change to this class. rather use code "to interface". and create interface DBConnection with connect method and use that directly. 
```