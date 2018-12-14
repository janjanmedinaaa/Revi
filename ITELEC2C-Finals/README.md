# ITELEC-2C Finals 

## Structural Design Patterns
Concerned with how classes and objects are composed to form larger structures

### Structural Class Patterns
- Use **Inheritance** to compose interfaces or implementations

### Structural Object Patterns
- Describe ways to compose objects to realize new functionality

### Decorator Pattern
- It is used to **attach additional responsibilities** to an object dynamically.
- We can add extra attributes or “*decoration*” to objects with a certain interface.
- **Parts**
    - **Component**
        - **Interface** for objects that can have responsibilities added to them dynamically.
    - **ConcreteComponent**
        - **Object** to which additional responsibilities can be attached.
    - **Decorator**
        - **Maintains a reference to a Component** object and defines an interface that conforms to Component’s interface.
    - **ConcreteDecorator**
        - **Adds responsibilities** to the component
- **Usage**
    - add responsibilities to individual objects dynamically and transparently without affecting other objects.

### Flyweight Pattern
- This pattern uses sharing to **support large numbers of fine-grained objects** efficiently.
- **Intrinsic State**
    - stored in the flyweight
    - it consists of information that’s independent of the flyweight’s context, thereby making it sharable. 
- **Extrinsic State**
    - depends on and varies with the flyweight’s context and therefore can’t be shared.
- **Parts**
    - **Flyweight**
        - **Interface** through which flyweights can receive and act on extrinsic state.
    - **ConcreteFlyweight**
        - **Implements the Flyweight interface** and adds storage for intrinsic state
    - **UnsharedConcreteFlyweight**
        - Flyweight interface enables sharing, but it **doesn’t enforce it**.
    - **FlyweightFactory**
        - **Creates and manages flyweight objects** and ensures that flyweight are shared properly.
    - **Client**
        - **Maintains a reference to flyweight(s)**, and computes or stores the extrinsic state of flyweight(s).

### Proxy Pattern
- **Provides a surrogate or placeholder** for another object to control access to it.
- create a representative **object that controls access to another object**, which may be remote, expensive to create or in need of being secured.
- **Parts**
    - **Proxy**
        - **Reference** that lets the proxy access the real subject.
    - **Subject**
        - **Interface for RealSubject and Proxy** so that a Proxy can be used anywhere a RealSubject is expected.
    - **RealSubject**
        - **REAL** object that the proxy represents.
- **Variations**
    - **Remote Proxy**
        - **Provides a local representative** for an object in a different address space.
    - **Virtual Proxy**
        - creates **expensive objects** on demand.
    - **Protection Proxy**
        - **Controls access** to the original object.

## Behavioral Design Patterns
Patterns that deal with encapsulating behavior with objects, assigning responsibility, and managing object cooperation when achieving common tasks.

### Iterator Design Pattern
- provides a standardized way for **accessing and traversing objects** in a collection data structure.
- Provide a way to **access the elements of an aggregate object sequentially** without exposing its underlying representation.

### Observer Design Pattern
- **standardizes the operations between objects** that interoperate using a one-to-many relationship.
- **Define a one-to-many dependency between objects** so that when one object changes state, all its dependents are notified and updated automatically.

### Chain of Responsibility
- A Group of objects is **chained together** in a sequence and a responsibility (*a request*) is provided in order to be handled by the group. 
- **Parts**
    - **Handler**
        - **Interface** for handling requests.
    - **ConcreteHandler**
        - **Handles requests** it is responsible for.
    - **Client**
        - **Initiates the request** to a ConcreteHandler object on the chain.

### Interpreter Design Pattern
- It’s all about putting together your own **programming language**, or handling an existing one, by creating an interpreter for that language.
- **Parts**
    - **AbstractExpression**
        - **Abstract Interpret operation that is common to all nodes** in the abstract syntax tree.
    - **TerminalExpression**
        - Implements an Interpret operation associated with **terminal symbols** in the grammar.
    - **NonterminalExpression**
        - Implements an Interpret operation for **non terminal symbols** in the grammar.
    - **Context**
        - Contains information that’s global to the interpreter.
    - **Client**
        - **Builds an abstract syntax tree** representing a particular sentence in the language that the grammar defines.

### Memento Design Pattern
- used to accomplish this without exposing the object’s internal structure.
- to **capture and externalize** an object’s internal state so that the object can be restored to this state later.
- **Parts**
    - **Originator**
        - **Creates a memento** containing a snapshot of its current internal state.
    - **Caretaker**
        - Responsible for the **memento’s safekeeping**.

### Strategy Design Pattern
- defines a **family of algorithms**, encapsulating each one, and making them interchangeable.
- **simplest** of all design patterns, yet it provides **great flexibility** to your code.
- lets the algorithm vary **independently from the clients** that use it.
- **Parts**
    - **Strategy**
        - **Declares an interface** common to all supported algorithms.
    - **ConcreteStrategy**
        - **Implements the algorithm** using the Strategy interface.
    - **Context**
        - Maintains a **reference** to a Strategy object.

### Command Design Pattern
- Encapsulate a request as an object, thereby letting the developer to parameterize  clients with different requests, queue or log requests, and support undoable operations.
- **Parts**
    - **Command**
        - interface for executing an operation.
    - **ConcreteCommand**
        - binding between a Receiver object and an action.
    - **Client**
        - Creates a ConcreteCommand object and sets its receiver.
    - **Invoker**
        - Asks the command to carry out the request.
    - **Receiver**
        - Knows how to perform the operations associated with carrying out a request

### State Design Pattern
- Allows an object to **alter its behavior** when its internal state changes.
- **Parts**
    - **Context**
        - Defines the **interface of interest to clients**.
    - **State**
        - Defines an **interface for encapsulating the behavior** associated with a particular state of the Context.
    - **ConcreteState Subclasses**
        - Each subclass **implements a behavior associated with a state** of the Context.

### Visitor Design Pattern
- **Provides a way to add new operations** on the objects without changing the classes of the elements, especially when the operations change quite often.
- Represent an operation to be performed on the elements of an object structure.
- **Parts**
    - **Visitor**
        - **Declares a Visit operation** for each class of ConcreteElement in the object structure.
    - **ConcreteVisitor**
        - Implements each operation declared by Visitor. 
        - Each operation **implements a fragment of the algorithm** defined for the corresponding class of object in the structure.
    - **Element**
        - **Defines** an Accept operation that **takes a visitor as an argument**.
    - **ConcreteElement**
        - **Implements** an Accept operation that **takes a visitor as an argument**.
    - **ObjectStructure**
        - **Provide a high-level interface** to allow the visitor to visit its elements