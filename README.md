# FullStackInterviewMaterial
Full stack interview materials

## Angular key notes
# Angular Concepts Revision



## Module

- **Definition:** A module groups components, services, pipes, and directives.

- **Command:** `ng g module student`

- **Default Arrays in Module:**

  - **Declarations:** Register components, directives, and pipes.

  - **Imports:** Import other modules.

  - **Providers:** Register services.

  - **Bootstrap:** Defines the root component to bootstrap.



## Decorator

- **Definition:** Metadata added to classes, properties, methods, or parameters for additional functionality.

- **Examples:** @Component, @Input, @Output



## Component

- **Definition:** A fundamental unit with a template, TypeScript class, and CSS.

- **Data Binding:** Connects component data with view.

  - **Interpolation:** `{{title}}`

  - **Property Binding:** `[innerHTML] = 'FirstName'`

  - **Attribute Binding:** `[attr.colspan] = 'value'`

  - **Class Binding:** `[class.some-class] = 'condition'`

  - **Style Binding:** `[style.font-weight] = "isBold ? 'bold' : 'normal'"`



## Data Binding Types

- **Interpolation:** Display component properties in HTML `({{property}})`.

- **Property Binding:** Bind component properties to HTML attributes `([property] = 'value')`.

- **Attribute Binding:** Set attributes in HTML `([attr.attribute] = 'value')`.

- **Class Binding:** Add or remove classes `([class.class-name] = 'condition')`.

- **Style Binding:** Set styles dynamically `([style.property] = 'value')`.

- **Two-Way Binding:** Use `[(ngModel)]` for bidirectional data binding; `import FormsModule from @angular/forms`.



## Directives

- **Definition:** Modify the behavior, appearance, or layout of DOM elements.

- **Types:**

  - **Structural Directives:** Change DOM structure (`*ngFor`, `*ngIf`, `*ngSwitch`).

  - **Attribute Directives:** Modify behavior (`NgStyle`, `NgClass`).



## Pipe

- **Definition:** Transforms raw data into a desired format.

- **Example:** `{{student.ID | uppercase}}`



## Routing

- **Definition:** Mechanism for navigating between pages and displaying components.

- **Example Link:** `<a [routerLink]="['/studentLink']">Student</a>`

- **Route Configuration:** `path: 'studentLink', component: StudentComponent`



## Services

- **Definition:** Code or logic used to perform specific tasks, injected via dependency injection.

- **Command:** `ng g s serviceName`



## Dependency Injection (DI)

- **Definition:** A design pattern where classes receive dependencies from external sources instead of creating them internally.



## Forms

- **Types:**

  - **Template-Driven Forms**

  - **Reactive Forms**


## Other materials:
## .NET Core

### OOPS

#### Encapsulation  
- **Definition:** Mechanism to bind methods and data members in a single unit (e.g., a class). Prevents unauthorized access to the data from outside.  
- **Example:**  
  ```csharp
  class Employee {
      private string name;
      public string Name {
          get { return name; }
          set { name = value; }
      }
  }
  var emp = new Employee();
  emp.Name = "John";
  Console.WriteLine(emp.Name); // Output: John
  ```

---

#### Inheritance  
- **Definition:** Mechanism where one class inherits the properties and behaviors of another class.  
- **Types:** Single, Multilevel, Hierarchical.  
- **Example:**  
  ```csharp
  class Animal {
      public void Eat() => Console.WriteLine("Eating...");
  }
  class Dog : Animal {
      public void Bark() => Console.WriteLine("Barking...");
  }
  var dog = new Dog();
  dog.Eat();  // Output: Eating...
  dog.Bark(); // Output: Barking...
  ```

---

#### Polymorphism  
- **Definition:** Allows multiple implementations of methods with the same name.  
  - **Static/Compile-Time Polymorphism:** Achieved using method overloading.  
  - **Dynamic/Runtime Polymorphism:** Achieved using method overriding with inheritance.  

- **Example (Compile-Time):**  
  ```csharp
  class Calculator {
      public int Add(int a, int b) => a + b;
      public double Add(double a, double b) => a + b;
  }
  var calc = new Calculator();
  Console.WriteLine(calc.Add(2, 3));       // Output: 5
  Console.WriteLine(calc.Add(2.5, 3.5)); // Output: 6.0
  ```

- **Example (Runtime):**  
  ```csharp
  class Animal {
      public virtual void Speak() => Console.WriteLine("Animal speaks...");
  }
  class Dog : Animal {
      public override void Speak() => Console.WriteLine("Dog barks...");
  }
  Animal animal = new Dog();
  animal.Speak(); // Output: Dog barks...
  ```

---

#### Abstraction  
- **Definition:** Represents essential features while hiding the background details. Achieved through abstract classes and interfaces.  
- **Example (Abstract Class):**  
  ```csharp
  abstract class Shape {
      public abstract void Draw();
  }
  class Circle : Shape {
      public override void Draw() => Console.WriteLine("Drawing Circle...");
  }
  var shape = new Circle();
  shape.Draw(); // Output: Drawing Circle...
  ```

---

#### Interface  
- **Definition:** Contains only method declarations without any implementation.  
- **Example:**  
  ```csharp
  interface IAnimal {
      void Speak();
  }
  class Dog : IAnimal {
      public void Speak() => Console.WriteLine("Dog barks...");
  }
  var dog = new Dog();
  dog.Speak(); // Output: Dog barks...
  ```

---

#### **Interface vs Abstract Class**  
| Feature              | Abstract Class                           | Interface                                |  
|----------------------|------------------------------------------|-----------------------------------------|  
| **Access Specifiers** | Supports all access specifiers           | Only `public`                           |  
| **Implementation**   | Can have method implementations          | No method implementation                |  
| **Constructors**     | Allowed                                  | Not allowed                             |  
| **Inheritance**      | Supports single inheritance              | Supports multiple inheritance           |  

- **Example (Abstract Class Constructor):**  
  ```csharp
  abstract class Animal {
      public Animal() { Console.WriteLine("Animal Constructor"); }
      public abstract void Speak();
  }
  class Dog : Animal {
      public override void Speak() => Console.WriteLine("Dog barks...");
  }
  var dog = new Dog(); // Output: Animal Constructor  
  ```
---
### Basic C#

#### Common Language Runtime (CLR)
- **Definition:** Provides runtime environment for thread management, type safety, and memory management.  
- **Example:**  
  ```csharp
  // CLR handles memory allocation for this object.
  object obj = new object();
  ```

---

#### Enum
- **Definition:** A value type that assigns string values to integers.  
- **Example:**  
  ```csharp
  enum Days { Sunday, Monday, Tuesday }
  Console.WriteLine((int)Days.Monday); // Output: 1
  ```

---

#### `ref`
- **Definition:** Pass arguments by reference.  
- **Example:**  
  ```csharp
  void UpdateValue(ref int number) { number = 10; }
  int num = 5;
  UpdateValue(ref num);
  Console.WriteLine(num); // Output: 10
  ```

---

#### `out`
- **Definition:** Used to return values from a method.  
- **Example:**  
  ```csharp
  void GetValues(out int a, out int b) { a = 5; b = 10; }
  GetValues(out int x, out int y);
  Console.WriteLine(x + y); // Output: 15
  ```

---

#### Properties
- **Definition:** Used to read or set private fields.  
- **Example:**  
  ```csharp
  class Person {
      private string name;
      public string Name {
          get { return name; }
          set { name = value; }
      }
  }
  var person = new Person();
  person.Name = "John";
  Console.WriteLine(person.Name); // Output: John
  ```

---

#### `is` Operator
- **Definition:** Checks if an object is of a specific type.  
- **Example:**  
  ```csharp
  object obj = "Hello";
  if (obj is string) Console.WriteLine("It is a string."); // Output: It is a string.
  ```

---

#### `as` Operator
- **Definition:** Safely casts an object to a specific type.  
- **Example:**  
  ```csharp
  object obj = "Hello";
  string str = obj as string;
  Console.WriteLine(str); // Output: Hello
  ```

---

#### Namespace
- **Definition:** Groups related classes.  
- **Example:**  
  ```csharp
  namespace MyNamespace {
      class MyClass { }
  }
  ```

---

#### Garbage Collection
- **Definition:** Automatically manages memory for unused objects.  
- **Example:**  
  ```csharp
  object obj = new object();
  obj = null; // Garbage Collector will free memory.
  ```

---

#### Extension Methods
- **Definition:** Add methods to existing classes without modifying them.  
- **Example:**  
  ```csharp
  public static class StringExtensions {
      public static bool IsEmpty(this string str) => string.IsNullOrEmpty(str);
  }
  Console.WriteLine("".IsEmpty()); // Output: True
  ```

---

#### Partial Class
- **Definition:** Splits a class across multiple files.  
- **Example:**  
  ```csharp
  partial class MyClass { void Method1() {} }
  partial class MyClass { void Method2() {} }
  ```

---

#### Method Overloading
- **Definition:** Methods with the same name but different signatures.  
- **Example:**  
  ```csharp
  void Print(int num) => Console.WriteLine(num);
  void Print(string str) => Console.WriteLine(str);
  Print(5);       // Output: 5
  Print("Hello"); // Output: Hello
  ```

---

#### Managed Code
- **Definition:** Executed by the .NET runtime.  
- **Example:**  
  ```csharp
  Console.WriteLine("Managed Code!");
  ```

---

#### Unmanaged Code
- **Definition:** Directly executed by the OS.  
- **Example:** Code written in C or C++ compiled as a DLL used in .NET.

---

#### Multithreading
- **Definition:** Multiple threads in a single process.  
- **Example:**  
  ```csharp
  Thread thread = new Thread(() => Console.WriteLine("Thread running"));
  thread.Start();
  ```

---

#### Delegate
- **Definition:** Refers to a method.  
- **Example:**  
  ```csharp
  delegate void PrintDelegate(string message);
  void Print(string message) => Console.WriteLine(message);
  PrintDelegate pd = Print;
  pd("Hello"); // Output: Hello
  ```

---

#### Sealed Class
- **Definition:** Prevents inheritance.  
- **Example:**  
  ```csharp
  sealed class MyClass { }
  ```

---

#### Generics
- **Definition:** Allows type parameters in methods, classes, or interfaces.  
- **Example:**  
  ```csharp
  class Box<T> { public T Value; }
  var box = new Box<int> { Value = 10 };
  Console.WriteLine(box.Value); // Output: 10
  ```

---

#### Boxing
- **Definition:** Converts value type to reference type.  
- **Example:**  
  ```csharp
  int num = 10;
  object obj = num; // Boxing
  ```

---

#### Unboxing
- **Definition:** Converts reference type to value type.  
- **Example:**  
  ```csharp
  object obj = 10;
  int num = (int)obj; // Unboxing
  ```

---

#### Interface
- **Definition:** A contract with no implementation.  
- **Example:**  
  ```csharp
  interface IAnimal { void Speak(); }
  class Dog : IAnimal { public void Speak() => Console.WriteLine("Bark"); }
  ```

---

#### Static
- **Definition:** Members shared across all instances.  
- **Example:**  
  ```csharp
  class MyClass {
      public static int Count = 0;
  }
  ```

---

#### Dependency Injection
- **Definition:** Inject dependencies at runtime.  

---

#### Middleware
- **Definition:** Software components in the request pipeline.  
- **Example:**  Authentication, logging, routing


---

#### **Dependency Lifecycle**  
1. **Transient**  
   - **Definition:** A new instance is created every time it is requested.  
   - **Example:**  
     ```csharp
     services.AddTransient<IService, ServiceImplementation>();
     ```

2. **Scoped**  
   - **Definition:** The same instance is provided throughout a single request's scope.  
   - **Example:**  
     ```csharp
     services.AddScoped<IService, ServiceImplementation>();
     ```

3. **Singleton**  
   - **Definition:** A single instance is created and shared across the application's lifetime.  
   - **Example:**  
     ```csharp
     services.AddSingleton<IService, ServiceImplementation>();
     ```

---

#### **Routing in API**  
1. **Conventional Routing**  
   - **Definition:** Route patterns are defined in the `Program.cs`.  
   - **Example:**  
     ```csharp
     app.MapControllerRoute(
         name: "default",
         pattern: "{controller=Home}/{action=Index}/{id?}");
     ```

2. **Attribute Routing**  
   - **Definition:** Routes are defined using attributes directly in controllers.  
   - **Example:**  
     ```csharp
     [Route("api/[controller]")]
     public class UsersController : ControllerBase {
         [HttpGet("{id}")]
         public IActionResult GetUser(int id) => Ok($"User {id}");
     }
     ```

---

#### **Return Types in API**  
1. **User-defined Types**  
   - **Example:**  
     ```csharp
     public string GetGreeting() => "Hello, World!";
     ```

2. **Models**  
   - **Example:**  
     ```csharp
     public User GetUser() => new User { Id = 1, Name = "John" };
     ```

3. **`ActionResult`**  
   - **Example:**  
     ```csharp
     public ActionResult GetResponse() => Ok("Success");
     ```

---

#### **Entity Framework (EF)**  
1. **Definition:** ORM framework to work with databases using .NET objects.  

2. **Core Concepts:**  
   - **DbContext:** Represents a session with the database, used to perform CRUD operations.  
     ```csharp
     public class AppDbContext : DbContext {
         public DbSet<User> Users { get; set; }
     }
     ```

   - **DbSet:** Represents a collection of entities corresponding to a table in the database.  
     ```csharp
     public class User {
         public int Id { get; set; }
         public string Name { get; set; }
     }
     ```

   - **Entities:** C# classes mapped to database tables.  

---

#### **Common API Status Codes**  
1. **2xx (Success)**  
   - **200:** OK (Request succeeded).  
   - **201:** Created (Resource successfully created).  
   - **204:** No Content (Request succeeded, but no content to return).  

2. **3xx (Redirection)**  
   - **301:** Moved Permanently (Resource has been moved).  

3. **4xx (Client Errors)**  
   - **400:** Bad Request (Invalid request).  
   - **401:** Unauthorized (Authentication required).  
   - **404:** Not Found (Resource not found).  
   - **405:** Method Not Allowed (HTTP method not allowed).  

4. **5xx (Server Errors)**  
   - **500:** Internal Server Error (Generic server error).  
   - **503:** Service Unavailable (Server is unavailable).  


#### **HTTP Status Codes in API**  
| **Code** | **Description**                 |  
|----------|---------------------------------|  
| **200**  | Success                         |  
| **201**  | Created (Resource successfully created). |  
| **204**  | No Content                      |  
| **301**  | Redirect                        |  
| **400**  | Bad Request                     |  
| **401**  | Unauthorized                    |  
| **404**  | Not Found                       |  
| **405**  | Method Not Allowed              |  
| **500**  | Internal Server Error           |  
| **503**  | Service Unavailable             |  

--- 

### Sample API Example  

```csharp
[Route("api/[controller]")]
public class UsersController : ControllerBase {
    [HttpGet("{id}")]
    public IActionResult GetUser(int id) {
        if (id <= 0) return BadRequest("Invalid ID");
        return Ok(new { Id = id, Name = "John Doe" }); // 200 OK
    }

    [HttpPost]
    public IActionResult CreateUser([FromBody] User user) {
        if (user == null) return BadRequest();
        return Created($"api/users/{user.Id}", user); // 201 Created
    }

    [HttpDelete("{id}")]
    public IActionResult DeleteUser(int id) {
        return NoContent(); // 204 No Content
    }
}
```
---

### SOLID Principles in C# with Examples  

#### S - Single Responsibility Principle (SRP)  
- **Definition:** A class should have only one reason to change; it should perform a single responsibility.  
- **Example:**  
  ```csharp
  // Violating SRP: Handling both data and logging in the same class
  class Employee {
      public void Save() => Console.WriteLine("Employee Saved.");
      public void Log() => Console.WriteLine("Log: Employee Saved.");
  }

  // Correct SRP implementation
  class Employee {
      public void Save() => Console.WriteLine("Employee Saved.");
  }
  class Logger {
      public void Log(string message) => Console.WriteLine($"Log: {message}");
  }
  ```

---

#### O - Open/Closed Principle (OCP)  
- **Definition:** A class should be open for extension but closed for modification.  
- **Example:**  
  ```csharp
  // Violating OCP
  class Discount {
      public double CalculateDiscount(string customerType) {
          if (customerType == "Regular") return 0.1;
          if (customerType == "Premium") return 0.2;
          return 0.0;
      }
  }

  // Correct OCP implementation
  abstract class Discount {
      public abstract double GetDiscount();
  }
  class RegularDiscount : Discount {
      public override double GetDiscount() => 0.1;
  }
  class PremiumDiscount : Discount {
      public override double GetDiscount() => 0.2;
  }
  ```

---

#### L - Liskov Substitution Principle (LSP)  
- **Definition:** Subclasses should be replaceable for their base classes without altering the program's correctness.  
- **Example:**  
  ```csharp
  // Violating LSP
  class Rectangle {
      public virtual int Width { get; set; }
      public virtual int Height { get; set; }
  }
  class Square : Rectangle {
      public override int Width { 
          set { base.Width = base.Height = value; } 
      }
      public override int Height { 
          set { base.Width = base.Height = value; } 
      }
  }

  // Correct LSP implementation
  interface IShape {
      int Area();
  }
  class Rectangle : IShape {
      public int Width { get; set; }
      public int Height { get; set; }
      public int Area() => Width * Height;
  }
  class Square : IShape {
      public int Side { get; set; }
      public int Area() => Side * Side;
  }
  ```

---

#### I - Interface Segregation Principle (ISP)  
- **Definition:** Clients should not be forced to depend on interfaces they do not use.  
- **Example:**  
  ```csharp
  // Violating ISP
  interface IWorker {
      void Work();
      void Eat();
  }
  class Robot : IWorker {
      public void Work() => Console.WriteLine("Robot working.");
      public void Eat() => throw new NotImplementedException(); // Robot doesn't eat
  }

  // Correct ISP implementation
  interface IWorker {
      void Work();
  }
  interface IEater {
      void Eat();
  }
  class Human : IWorker, IEater {
      public void Work() => Console.WriteLine("Human working.");
      public void Eat() => Console.WriteLine("Human eating.");
  }
  class Robot : IWorker {
      public void Work() => Console.WriteLine("Robot working.");
  }
  ```

---

#### D - Dependency Inversion Principle (DIP)  
- **Definition:** High-level modules should not depend on low-level modules; both should depend on abstractions.  
- **Example:**  
  ```csharp
  // Violating DIP
  class FileStorage {
      public void Store(string data) => Console.WriteLine($"Stored: {data}");
  }
  class Report {
      private FileStorage storage = new FileStorage();
      public void Generate(string content) => storage.Store(content);
  }

  // Correct DIP implementation
  interface IStorage {
      void Store(string data);
  }
  class FileStorage : IStorage {
      public void Store(string data) => Console.WriteLine($"Stored: {data}");
  }
  class Report {
      private IStorage storage;
      public Report(IStorage storage) => this.storage = storage;
      public void Generate(string content) => storage.Store(content);
  }
  ```
---
## Database SQL Server

#### Database  
- **Definition:** Organized collection of data for easy access, management, and updating.  

---

#### View  
- **Definition:** A virtual table based on a query.  
- **Example:**  
  ```sql
  CREATE VIEW view_name AS  
  SELECT name, age FROM Students WHERE age > 18;
  SELECT * FROM view_name;
  ```

---

#### Constraints  
- **Definition:** Rules applied to a table to restrict the type of data.  
- **Common Types:**  
  - **PRIMARY KEY:** Ensures unique values in a column.  
  - **FOREIGN KEY:** Links two tables.  
  - **NOT NULL:** Ensures a column cannot have NULL values.  
  - **UNIQUE:** Ensures all values in a column are different.  
  - **CHECK:** Ensures values meet a condition.  
  - **DEFAULT:** Assigns a default value if no value is provided.  

---

#### Aggregate Functions  
- **Definition:** Operations performed on a column to return a single value.  
- **Examples:**  
  ```sql
  SELECT AVG(salary) FROM Employees; -- Average salary  
  SELECT COUNT(*) FROM Employees;    -- Total number of employees  
  SELECT SUM(salary) FROM Employees; -- Total salary  
  ```

---

#### Scalar Functions  
- **Definition:** Operates on user input and returns a single value.  
- **Examples:**  
  ```sql
  SELECT UCASE('hello'); -- Output: HELLO  
  SELECT LENGTH('hello'); -- Output: 5  
  ```

---

#### Index  
- **Definition:** Data structure to speed up data retrieval.  
- **Example:**  
  ```sql
  CREATE INDEX idx_name ON Employees (name);
  DROP INDEX idx_name;
  ```

---

#### Trigger  
- **Definition:** A set of SQL statements executed automatically when a specified database event occurs (e.g., INSERT, UPDATE, DELETE).  
- **Example:**  
  ```sql
  CREATE TRIGGER after_insert_students  
  AFTER INSERT ON Students  
  FOR EACH ROW  
  BEGIN  
      INSERT INTO Logs(message) VALUES ('New student added');  
  END;
  ```

---

#### ACID Properties  
- **Definition:** Ensures reliable transactions in a database.  
  - **Atomicity:** Transactions are "all or nothing."  
  - **Consistency:** Ensures data integrity.  
  - **Isolation:** Transactions occur independently.  
  - **Durability:** Changes persist even after a failure.  

---

#### Procedure  
- **Definition:** A stored set of SQL statements.  
- **Example:**  
  ```sql
  CREATE PROCEDURE SelectAll  
  AS  
  SELECT * FROM Students;  
  EXEC SelectAll;  
  ```

---

#### Basic SQL Operations  

1. **Create Table**  
   ```sql
   CREATE TABLE Users (  
       ID INT PRIMARY KEY,  
       Name VARCHAR(50)  
   );  
   ```

2. **Alter Table**  
   ```sql
   ALTER TABLE Users ADD Address VARCHAR(100);  
   ```

3. **Drop Table**  
   ```sql
   DROP TABLE Users;  
   ```

4. **Rename Table**  
   ```sql
   ALTER TABLE Users RENAME TO Customers;  
   ```
   
## Q&A
https://github.com/StefanTheCode/dotnet_interview_questions

## Angular
https://github.com/sudheerj/angular-interview-questions
