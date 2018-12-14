# ITELEC-2C Finals 

## Structural Design Patterns
Concerned with how classes and objects are composed to form larger structures

### Structural Class Patterns
- Use **inheritance** to compose interfaces or implementations

### Structural Object Patterns
- Describe ways to compose objects to realize new functionality

### Decorator Pattern
- It is used to **attach additional responsibilities** to an object dynamically.
- We can add extra attributes or “*decoration*” to objects with a certain interface.
- **Parts**
    - **Component**
        - **interface** for objects that can have responsibilities added to them dynamically.
    - **ConcreteComponent**
        - **object** to which additional responsibilities can be attached.
    - **Decorator**
        - **maintains a reference to a Component** object and defines an interface that conforms to Component’s interface.
    - **ConcreteDecorator**
        - **adds responsibilities** to the component
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
        - **interface** through which flyweights can receive and act on extrinsic state.
    - **ConcreteFlyweight**
        - **implements the Flyweight interface** and adds storage for intrinsic state
    - **UnsharedConcreteFlyweight**
        - Flyweight interface enables sharing, but it **doesn’t enforce it**.
    - **FlyweightFactory**
        - **creates and manages flyweight objects** and ensures that flyweight are shared properly.
    - **Client**
        - **maintains a reference to flyweight(s)**, and computes or stores the extrinsic state of flyweight(s).

### Proxy Pattern
- **Provides a surrogate or placeholder** for another object to control access to it.
- create a representative **object that controls access to another object**, which may be remote, expensive to create or in need of being secured.
- **Parts**
    - **Proxy**
        - **reference** that lets the proxy access the real subject.
    - **Subject**
        - **interface for RealSubject and Proxy** so that a Proxy can be used anywhere a RealSubject is expected.
    - **RealSubject**
        - **real** object that the proxy represents.
- **Variations**
    - **Remote Proxy**
        - **provides a local representative** for an object in a different address space.
    - **Virtual Proxy**
        - creates **expensive objects** on demand.
    - **Protection Proxy**
        - **controls access** to the original object.