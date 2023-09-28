# Design Patterns

## Background

### Definition:
- **Design Patterns** are typical solutions to common problems in software design. They're like templates devised to help solve problems more efficiently.

### History:
- Originated from a book titled **"Design Patterns: Elements of Reusable Object-Oriented Software"** by four authors (known as the Gang of Four): Erich Gamma, Richard Helm, Ralph Johnson, and John Vlissides, back in 1994.

### Purpose:
- They help in:
  1. **Solving problems**: By providing tested, proven development paradigms.
  2. **Maintaining code**: Making the software easier to understand and debug.
  3. **Communication**: Offering a common language for developers to discuss and document solutions.

### Literature:
1. **Original Gang of Four Book**: Essential for anyone serious about design patterns.
2. **"Head First Design Patterns"** by Eric Freeman and Elisabeth Robson: A more accessible entry with a visual, intuitive approach.
3. **"Design Patterns Explained"** by Alan Shalloway and James Trott: Provides a simple, non-technical introduction to design patterns.

## Core Concepts

### **Creational Patterns**:
- Deal with object creation and initialization.

#### 1. **Abstract Factory**: 
- Provides an interface for creating families of related or dependent objects without specifying their concrete classes.

#### 2. **Builder**:
- Allows the creation of complex objects step by step.

#### 3. **Factory Method**:
- Defines an interface for creating an object, but leaves the choice of its type to the subclasses.

#### 4. **Prototype**:
- Creates new objects by copying an existing object, known as a prototype.

#### 5. **Singleton**:
- Ensures a class has only one instance and provides a global point to this instance.

### **Structural Patterns**:
- Concerned with how classes and objects are composed to form larger structures.

#### 1. **Adapter**: 
- Allows incompatible interfaces to work together.

#### 2. **Bridge**:
- Separates an object's abstraction from its implementation so the two can vary independently.

#### 3. **Composite**: 
- Allows individual objects and composites of objects to be treated uniformly.

#### 4. **Decorator**: 
- Adds new functionality to an object without altering its structure.

#### 5. **Facade**: 
- Provides a simplified interface to a complex subsystem, making the subsystem easier to use and understand. It hides the complexities and exposes only necessary parts to the client.

#### 6. **Flyweight**: 
- Minimizes memory usage or computational expenses by sharing as much as possible.

#### 7. **Proxy**:
- Provides a placeholder for another object to control access to it.

### **Behavioral Patterns**:
- Concerned with communication between objects.

#### 1. **Chain of Responsibility**:
- Allows passing requests along a chain of handlers, with each handler deciding to process the request or pass it along the chain.

#### 2. **Command**:
- Turns a request into a standalone object, containing information about the request, making it parameterizable.

#### 3. **Interpreter**:
- Provides a way to evaluate language grammar or expressions for particular languages.

#### 4. **Iterator**:
- Provides a way to access the elements of a collection object in a sequential manner without exposing the underlying representation.

#### 5. **Mediator**:
- Reduces connections between multiple classes or objects by centralizing external communications through a mediator.

#### 6. **Memento**:
- Lets you save and restore the previous state of an object without revealing the details of its implementation.

#### 7. **Observer**:
- Defines a subscription mechanism to allow multiple objects to listen and react to events or changes in other objects.

#### 8. **State**:
- Lets an object alter its behavior when its internal state changes.

#### 9. **Strategy**:
- Defines a family of algorithms, encapsulates each one of them, and makes them interchangeable.

#### 10. **Template Method**:
- Defines the skeleton of an algorithm in the base class but lets subclasses override specific steps of the algorithm without changing its structure.

#### 11. **Visitor**:
- Lets you add further operations to objects without having to modify them.

## Creational Patterns use cases (pizza example)

#### 1. **Singleton**:
- **Oven Management**: In a pizza restaurant, there could be a single oven that is used to bake all pizzas. The Singleton pattern ensures that there's only one oven instance, preventing the creation of multiple ovens and ensuring all pizzas go through the same baking process.

#### 2. **Factory Method**:
- **Pizza Creation**: The Factory Method could be used to create different types of pizzas (e.g., Margherita, Pepperoni, Veggie) based on the order, encapsulating the pizza creation process.

#### 3. **Abstract Factory**:
- **Pizza Ingredient Families**: The Abstract Factory pattern is well-suited for managing the creation of different families of related objects, like the different sets of ingredients needed for different types of pizzas.
- You could have an abstract factory interface `PizzaIngredientFactory` that declares methods for creating various types of ingredients like dough, sauce, cheese, and toppings.
- Then, for each specific type of pizza, you could implement a concrete factory that produces the appropriate ingredients for that type of pizza. For example, `MargheritaIngredientFactory`, `PepperoniIngredientFactory`, and `VeggieIngredientFactory` could each provide the particular ingredients needed for Margherita, Pepperoni, and Veggie pizzas, respectively.
- When it's time to make a pizza, you would use the corresponding ingredient factory to get the ingredients. This way, the details of ingredient creation are encapsulated in the concrete factories, and the pizza preparation code can remain focused on assembling and baking the pizza.

#### 4. **Builder**:
- **Custom Pizza Order**: The Builder pattern could be used for creating custom pizzas where customers can choose their base, sauce, cheese, and toppings, specifying various options in a fluent ordering process.

#### 5. **Prototype**:
- **Cloning Pre-defined Pizzas**: If a pizzeria offers a few standard pizzas, a Prototype pattern can be used to clone a predefined pizza prototype rather than creating each pizza from scratch, ensuring consistency and speeding up the preparation process.

## Structural Patterns use cases (pizza example)

### 1. **Adapter**:
- **Recipe Conversion**: Suppose the pizza restaurant gets some recipes from an Italian chef, but the measurement units are different. An adapter could be used to convert the measurement units from metric to imperial or vice versa.

### 2. **Bridge**:
- **Online Ordering Systems**: If the pizza restaurant has an online ordering system, the Bridge pattern could be used to separate the abstraction of the order from the implementation which could vary (e.g., web-based ordering, mobile app ordering).

### 3. **Composite**:
- **Menu Representation**: The menu of the pizza restaurant can be represented as a composite of items where each item could be a single pizza or a combo meal (which in turn could contain multiple pizzas and sides).

### 4. **Decorator**:
- **Pizza Customization**: A Decorator pattern could be used for adding toppings to a basic pizza, where each topping is a decorator that adds features (like extra cost and ingredients) to the pizza.

### 5. **Facade**:
- **Order Simplification**: The Facade pattern can simplify the process of ordering a pizza by providing a simple interface to the client, which internally manages the complex process of order creation, payment processing, and order tracking.

### 6. **Flyweight**:
- **Ingredient Sharing**: Imagine you're running a very large pizza restaurant with hundreds of outlets. Each outlet serves many types of pizzas, and each pizza has a recipe. Now, if we were to create an object for each pizza in each outlet with its own copy of the recipe, we'd end up with a lot of duplicate recipe data, wasting a lot of memory. This is where the Flyweight Pattern comes into play. Instead of each pizza object storing its own recipe, we store each unique recipe in a shared location. Each pizza object then just keeps a reference to its recipe. This way, no matter how many pizza objects we create, there's only one copy of each unique recipe, saving a significant amount of memory.

### 7. **Proxy**:
- **Order Authorization**: Before processing an order, a proxy could be used to check whether the customer has sufficient balance in their account or if their payment information is valid.

## Behavioural Design patterns use cases (pizza example)

### 1. **Chain of Responsibility**:
- **Order Handling**: Different stations (order taking, pizza making, baking, and serving) in a pizza restaurant may form a chain of responsibility. Each station can handle a part of the process, passing along the order to the next station until the order is completed and served.

### 2. **Command**:
- **Order Processing**: When an order is placed, a command representing the order can be created. This command object encapsulates all the details of the order and can be passed around to different systems (like order preparation, billing) that process the order.

### 3. **Interpreter**:
- **Pizza Recipe Parsing**: If the pizza recipes are stored in a specialized language, an interpreter could be used to parse and execute the recipes to prepare pizzas accordingly.

### 4. **Iterator**:
- **Menu Traversal**: A pizza restaurant's menu can have an iterator that allows customers or staff to traverse through the different pizza options and other menu items sequentially.

### 5. **Mediator**:
- **Kitchen Management**: A mediator could coordinate between different stations in the kitchen, ensuring that pizzas are prepared, baked, and served in the correct order and efficiently.

### 6. **Memento**:
- **Order History**: Customers could have the ability to view their past orders, and reorder a past selection. The memento pattern could capture the state of an order allowing it to be restored later.

### 7. **Observer**:
- **Order Status Updates**: An observer pattern could be used to notify customers or staff about the status of pizza orders as they move through preparation, baking, and serving stages.

### 8. **State**:
- **Order State Management**: The state pattern could be used to manage the different states an order goes through - such as received, preparing, baking, ready for pickup, and completed.

### 9. **Strategy**:
- **Discount Strategies**: The pizza restaurant might have different discount strategies (e.g., weekday discounts, member discounts) which can be applied to orders based on certain criteria.

### 10. **Template Method**:
- **Pizza Preparation Process**: The general steps for preparing a pizza could be defined in a template method, with the specific preparation details for different types of pizzas being filled in by subclasses.

### 11. **Visitor**:
- **Ingredient Inventory Management**: A visitor pattern could be used to traverse through different types of ingredients, performing operations like checking inventory levels or reordering supplies.
