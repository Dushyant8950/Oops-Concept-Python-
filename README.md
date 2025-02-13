**Oops Complete Tutorial**
This code provides an extensive demonstration of Object-Oriented Programming (OOP) concepts in Python. It covers key principles such as:

**1. Classes and Objects**  
   - **Classes** define blueprints for objects.
   - **Objects** are instances of classes.  
   - Example classes include `Dog`, `Calculator`, `Student`, and `BankAccount`.

**2. Inheritance**  
   - A mechanism that allows a class to derive properties and behaviors from another class.
   - Examples include:
     - `Dog` class inheriting from `Animal`
     - `Car` class inheriting from `Vehicle`
     - Multi-level inheritance in `Manager` (derived from `Employee`, which is derived from `Person`)
     - Multiple inheritance in `AmphibiousVehicle` (inherits from both `FlyingVehicle` and `WaterVehicle`)

**3. Encapsulation**  
   - Restricting direct access to an object's internal data using **private (`__`) and protected (`_`) attributes**.
   - Examples:
     - `BankAccount` with a private `__balance` attribute.
     - `Person` with a private `__age` attribute and setter methods to validate input.

**4. Polymorphism**  
   - Allows different classes to share the same method name but implement it differently.
   - Examples:
     - `Dog`, `Cat`, and `Cow` classes each define a `speak()` method differently.
     - `Rectangle`, `Circle`, and `Triangle` all have an `area()` method.
     - `Employee`, `Manager`, `Developer`, and `Designer` implement `work()` differently.

**5. Abstraction**  
   - Hides implementation details and enforces method implementation in derived classes using **Abstract Base Classes (ABC)**.
   - Examples:
     - `Animal` class has an abstract `speak()` method, which must be implemented in derived classes like `Dog` and `Cat`.
     - `Shape` class has an abstract `area()` method, implemented in `Rectangle` and `Circle`.
     - `Payment` class has an abstract `pay()` method, implemented in `CreditCardPayment` and `PayPalPayment`.

**6. Special Methods (Dunder Methods)**  
   - Methods like `__str__`, `__len__`, `__add__`, and `__getitem__` allow customization of built-in behaviors.
   - Examples:
     - `Book` defines `__str__` and `__len__` to return readable output and page count.
     - `Point` overrides `__add__` to allow addition of coordinate points.
     - `CustomList` implements `__len__` and `__getitem__` for list-like behavior.

**Overall Summary**  
This code is a **comprehensive guide to OOP in Python**, demonstrating fundamental principles with practical examples. It emphasizes **reusability, maintainability, and abstraction** to create well-structured, scalable applications.


This code demonstrates **Object-Oriented Programming (OOP) concepts** in Python through different real-life scenarios using **classes and objects**. Let's break down each section:

---

**1. OOP Concepts in Python**
The code highlights fundamental OOP principles:
- **Class**: A blueprint for creating objects.
- **Object**: An instance of a class.
- **Constructor (`__init__`)**: Initializes class attributes.
- **Self keyword**: Refers to the instance of the class.
- **Inheritance, Polymorphism, Data Hiding** (Not fully utilized in the provided examples).

---

**2. `Product` Class (Represents a Product)**
 **Features:**
- Stores product details: **name, price, quantity**.
- Calculates:
  - Total amount (`amt = price × quantity`).
  - 10% discount (`dis = amt × 10 / 100`).
  - Final payable amount (`pmt = amt - dis`).

**Example Output:**
For a **mobile** priced at ₹34,000 with quantity **4**, the output is:
```
your product name: mobile
your prate: 34000
your pqty: 4
amount= 136000
discount= 13600.0
paymount= 122400.0
```

---

**3. `Employee` Class (Salary Calculation)**
**Features:**
- Stores employee **name** and **salary**.
- Deductions:
  - Travel Allowance (**TA**): 5% of salary.
  - Dearness Allowance (**DA**): 10% of salary.
  - House Rent Allowance (**HRA**): 15% of salary.
  - **Net salary** = salary - (TA + DA + HRA).

*Example Output:**
For **Vivek** with a salary of **₹1,400,000**:
```
Total TA= 70000.0
Total DA= 140000.0
Total HRA= 210000.0
Total Salary is= 980000.0
```

---

**4. `Bank` Class (Basic Banking Operations)**
 **Features:**
- Stores **client name** and **balance**.
- **Deposit**: Adds amount to balance.
- **Withdraw**: Deducts amount from balance.
- **Check balance**: Displays current balance.

**Example Process:**
- Initial balance: **₹50,000**
- Withdraw **₹3,400** → New balance: **₹46,600**
- Withdraw **₹5,000** → New balance: **₹41,600**
- Check balance → Shows: **₹41,600**
- Deposit **₹1,200** → New balance: **₹42,800**

---

**5. `Person` Class (Age Calculation)**
**Features:**
- Stores **name, country, date of birth**.
- Calculates **age** using `date` module.

**Age Calculation Logic:**
```python
age = today.year - birthDate.year - ((today.month, today.day) < (birthDate.month, birthDate.day))
```
This ensures the age is correctly calculated by checking if the **birthday has passed** in the current year.

 **Example Output:**
For **DOB: 1997-02-03**, the output is:
```
27 years
```

---

**Conclusion**
- The code effectively demonstrates **OOP concepts** by implementing **real-life examples**.
- Could be improved by:
  - Adding **error handling** (e.g., negative deposits in `Bank` class).
  - Using **inheritance** to avoid redundancy (e.g., a base `Person` class for `Employee`).
  - Improving variable names (`pmt → payment`, `prate → price`, etc.).


Encapsulation is a fundamental concept in object-oriented programming (OOP) that involves bundling related data and the methods that operate on that data within a single unit, typically a class. This approach restricts direct access to certain components of an object, promoting modularity, maintainability, and data integrity. In Python, encapsulation is implemented using access modifiers to control the visibility of class members.

**Access Modifiers in Python:**

1. **Public Members:** Accessible from anywhere; defined without any leading underscores.
2. **Protected Members:** Intended for internal use within the class and its subclasses; indicated by a single leading underscore (`_`).
3. **Private Members:** Restricted to the class in which they are defined; denoted by a double leading underscore (`__`).

**Example 1:**

In this example, we define a `Test` class with private attributes for a person's name, email, and city. We provide public getter and setter methods to access and modify these private attributes, ensuring controlled access.

```python
class Test:
    def __init__(self):
        self.__pname = ""
        self.__email = ""
        self.__city = ""

    def get_pname(self):
        return self.__pname

    def set_pname(self, pname):
        self.__pname = pname

    def get_email(self):
        return self.__email

    def set_email(self, email):
        self.__email = email

    def get_city(self):
        return self.__city

    def set_city(self, city):
        self.__city = city

# Usage
t = Test()
t.set_pname("Ankur")
print(t.get_pname())  # Output: Ankur
t.set_email("abc@gmail.com")
print(t.get_email())  # Output: abc@gmail.com
t.set_city("Delhi")
print(t.get_city())   # Output: Delhi
```

**Explanation:**

- The `Test` class has private attributes: `__pname`, `__email`, and `__city`.
- Public methods (`get_pname`, `set_pname`, etc.) are provided to access and modify these private attributes.
- This encapsulation ensures that the internal state of the object is not directly accessible from outside the class, promoting data integrity.

**Example 2:**

Here, we define a `Data` class to encapsulate an employee's details, including name, email, phone number, city, and salary. Private attributes are used, with public getter and setter methods to manage access.

```python
class Data:
    def __init__(self):
        self.__empname = ""
        self.__email = ""
        self.__phone = ""
        self.__city = ""
        self.__salary = 0

    def get_empname(self):
        return self.__empname

    def set_empname(self, employeename):
        self.__empname = employeename

    def get_email(self):
        return self.__email

    def set_email(self, email):
        self.__email = email

    def get_phone(self):
        return self.__phone

    def set_phone(self, phone_number):
        self.__phone = phone_number

    def get_city(self):
        return self.__city

    def set_city(self, city):
        self.__city = city

    def get_salary(self):
        return self.__salary

    def set_salary(self, salary):
        self.__salary = salary

# Usage
data = Data()
data.set_empname("Employee name is: Dushyant Sharma")
print(data.get_empname())  # Output: Employee name is: Dushyant Sharma
data.set_email("Email Address of Employee is: sharma.d8950@gmail.com")
print(data.get_email())    # Output: Email Address of Employee is: sharma.d8950@gmail.com
data.set_phone(8950576564)
print(f"Phone number of Employee is: {data.get_phone()}")  # Output: Phone number of Employee is: 8950576564
data.set_city("City of Address of Employee is: Palwal")
print(data.get_city())     # Output: City of Address of Employee is: Palwal
data.set_salary(3600000)
print(f"Salary of Employee is: {data.get_salary()}")  # Output: Salary of Employee is: 3600000
```

**Explanation:**

- The `Data` class encapsulates employee details with private attributes.
- Public getter and setter methods are provided for controlled access to these attributes.
- This design ensures that the internal state of the `Data` object is protected from unauthorized access and modification.

**Benefits of Encapsulation:**

- **Data Hiding:** Prevents external code from accessing internal object data directly, reducing the risk of unintended interference.
- **Modularity:** Encourages a modular approach, making code more manageable and maintainable.
- **Controlled Access:** Allows controlled access to class attributes through methods, ensuring data integrity.
- **Flexibility:** Enables changes to the internal implementation without affecting external code, as long as the interface remains consistent.

By implementing encapsulation, developers can create robust and secure code structures that safeguard data and promote clear interfaces for interaction. 


In Python, **method overloading** and **method overriding** are two fundamental concepts in object-oriented programming that facilitate polymorphism, allowing methods to behave differently based on context.

**Method Overloading**:
Method overloading refers to defining multiple methods within the same class that share the same name but differ in the number or type of parameters. However, Python does not support traditional method overloading as seen in some other languages. If multiple methods with the same name are defined, the most recently defined method will override the previous ones. To achieve similar functionality, Python developers often use default parameter values or variable-length arguments (`*args` and `**kwargs`).

*Example*:
```python
class A:
    def sum(self, a, b, c=0):
        s = a + b + c
        print("sum =", s)

result = A()
result.sum(20, 39)      # Output: sum = 59
result.sum(20, 39, 23)  # Output: sum = 82
```
In this example, the `sum` method can handle both two and three arguments by providing a default value for the third parameter.

**Method Overriding**:
Method overriding occurs when a subclass provides a specific implementation for a method that is already defined in its superclass. This allows the subclass to offer a tailored behavior while retaining the same method signature.

*Example*:
```python
class A:
    def display(self):
        print("Display method in class A")

class B(A):
    def display(self):
        print("Display method in class B")

a = A()
b = B()

a.display()  # Output: Display method in class A
b.display()  # Output: Display method in class B
```
Here, class `B` overrides the `display` method of class `A`. When `display` is called on an instance of `B`, the overridden method in `B` is executed.

**Key Differences**:
- **Definition**:
  - *Method Overloading*: Defining multiple methods with the same name but different parameters within the same class.
  - *Method Overriding*: Defining a method in a subclass with the same name and parameters as in its superclass.

- **Purpose**:
  - *Method Overloading*: To allow methods to handle different types or numbers of inputs.
  - *Method Overriding*: To provide a specific implementation of a method in a subclass.

- **Inheritance**:
  - *Method Overloading*: Occurs within a single class.
  - *Method Overriding*: Requires at least one superclass and one subclass.

Understanding these concepts is crucial for implementing polymorphism and designing flexible, maintainable code in Python. 
