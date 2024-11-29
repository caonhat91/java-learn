### **Ngày 2: Nền tảng Java cơ bản**  
**Mục tiêu:**  
- Nắm được tư duy lập trình hướng đối tượng (OOP).  
- Hiểu sâu hơn về các đặc điểm của OOP như kế thừa, đa hình, đóng gói.  
- Ứng dụng lý thuyết vào các bài toán thực tế.

---

## **Lý thuyết Ngày 2: Lập trình hướng đối tượng (OOP)**  

### **1. Khái niệm cơ bản về OOP:**  
1. **Class:** Khuôn mẫu để tạo đối tượng (object).  
2. **Object:** Thể hiện của class, có trạng thái (biến) và hành vi (hàm).  
3. **Tính kế thừa:** Cho phép một class kế thừa thuộc tính và phương thức của class khác.  
4. **Tính đa hình:** Thay đổi hành vi phương thức dựa trên ngữ cảnh.  
5. **Tính đóng gói:** Bảo vệ dữ liệu thông qua access modifier (`private`, `protected`, `public`).  

---

### **1.1-1.2. Cách khai báo và sử dụng class:**  
**Khai báo class:**  
```java
public class Person {
    private String name;
    private int age;

    // Constructor
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Getter
    public String getName() {
        return name;
    }

    // Setter
    public void setName(String name) {
        this.name = name;
    }

    // Phương thức
    public void introduce() {
        System.out.println("Tôi là " + name + ", " + age + " tuổi.");
    }
}
```

**Sử dụng class:**  
```java
Person person = new Person("Nhất", 25);
person.introduce();  // Output: Tôi là Nhất, 25 tuổi.
```

---

### **1.3. Tính kế thừa (Inheritance)**  
- **Định nghĩa:** Kế thừa cho phép một lớp (class) con sử dụng lại các thuộc tính và phương thức của lớp cha (superclass).  
- **Cách khai báo:** Dùng từ khoá `extends`.  

**Ví dụ:**  
```java
// Lớp cha
public class Animal {
    protected String name;

    public void eat() {
        System.out.println(name + " đang ăn.");
    }
}

// Lớp con
public class Dog extends Animal {
    public void bark() {
        System.out.println(name + " đang sủa.");
    }
}

// Sử dụng
Dog dog = new Dog();
dog.name = "Rex";
dog.eat();   // Output: Rex đang ăn.
dog.bark();  // Output: Rex đang sủa.
```

---

### **1.4. Tính đa hình (Polymorphism)**  
- **Định nghĩa:** Cho phép một phương thức có thể thực hiện các hành vi khác nhau, tuỳ thuộc vào lớp đối tượng gọi nó.  
- **Loại đa hình:**  
  1. **Đa hình tại runtime (Overriding):**  
     - Khi lớp con ghi đè (override) phương thức của lớp cha.  
  2. **Đa hình tại compile-time (Overloading):**  
     - Khi có nhiều phương thức cùng tên trong cùng một lớp nhưng khác tham số.  

**Ví dụ Overriding:**  
```java
public class Animal {
    public void makeSound() {
        System.out.println("Animal phát ra âm thanh.");
    }
}

public class Cat extends Animal {
    @Override
    public void makeSound() {
        System.out.println("Meo meo.");
    }
}

// Sử dụng
Animal animal = new Cat();
animal.makeSound();  // Output: Meo meo.
```

**Ví dụ Overloading:**  
```java
public class Calculator {
    public int add(int a, int b) {
        return a + b;
    }

    public double add(double a, double b) {
        return a + b;
    }
}

// Sử dụng
Calculator calc = new Calculator();
System.out.println(calc.add(2, 3));        // Output: 5
System.out.println(calc.add(2.5, 3.5));    // Output: 6.0
```

---

### **1.5. Tính đóng gói (Encapsulation)**  
- **Định nghĩa:**  
  - Đóng gói bảo vệ dữ liệu bằng cách ẩn đi (private) và chỉ cho phép truy cập qua các phương thức công khai (getter, setter).  
  - Sử dụng từ khoá `private` để ẩn dữ liệu.  
- **Lợi ích:**  
  - Dữ liệu an toàn, kiểm soát được quyền truy cập và sửa đổi.  

**Ví dụ:**  
```java
public class Account {
    private double balance;

    // Getter
    public double getBalance() {
        return balance;
    }

    // Setter
    public void setBalance(double balance) {
        if (balance >= 0) {
            this.balance = balance;
        } else {
            System.out.println("Số dư không hợp lệ!");
        }
    }
}

// Sử dụng
Account account = new Account();
account.setBalance(1000);
System.out.println(account.getBalance());  // Output: 1000
```

---

### **1.6. Constructor và Overloading Constructor**  
- **Constructor:**  
  - Là phương thức đặc biệt được gọi tự động khi tạo đối tượng.  
  - Dùng để khởi tạo giá trị ban đầu.  
- **Overloading Constructor:**  
  - Một class có thể có nhiều constructor với các tham số khác nhau.  

**Ví dụ:**  
```java
public class Student {
    private String name;
    private int age;

    // Constructor không tham số
    public Student() {
        this.name = "Unknown";
        this.age = 0;
    }

    // Constructor có tham số
    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public void showInfo() {
        System.out.println(name + ", " + age + " tuổi.");
    }
}

// Sử dụng
Student s1 = new Student();
Student s2 = new Student("Nhất", 25);
s1.showInfo();  // Output: Unknown, 0 tuổi.
s2.showInfo();  // Output: Nhất, 25 tuổi.
```

---

## **Bài tập thực hành Ngày 2:**  

### **Bài 1: Quản lý thông tin nhân viên**  
1. Tạo class `Employee` với các thuộc tính: `id`, `name`, `position`.  
2. Viết hàm hiển thị thông tin nhân viên: `showInfo()`.  
3. Tạo 2 đối tượng `Employee` và gọi phương thức `showInfo()`.  

---

### **Bài 2: Tính diện tích hình chữ nhật**  
1. Tạo class `Rectangle` với các thuộc tính: `width`, `height`.  
2. Thêm phương thức `calculateArea()` trả về diện tích.  
3. Viết chương trình sử dụng class `Rectangle` để tính diện tích của một hình chữ nhật.  

**Gợi ý:**  
```java
public class Rectangle {
    private int width;
    private int height;

    public Rectangle(int width, int height) {
        this.width = width;
        this.height = height;
    }

    public int calculateArea() {
        return width * height;
    }
}
```   

### **Bài 3: Quản lý động vật**  
1. Tạo lớp cha `Animal` với thuộc tính `name` và phương thức `makeSound()`.  
2. Tạo các lớp con:  
   - `Dog`: Ghi đè phương thức `makeSound()` để in ra "Gâu gâu".  
   - `Cat`: Ghi đè phương thức `makeSound()` để in ra "Meo meo".  
3. Viết chương trình tạo danh sách các đối tượng `Animal` và gọi `makeSound()` cho từng đối tượng.  

---

### **Bài 4: Quản lý tài khoản ngân hàng**  
1. Tạo lớp `BankAccount` với các thuộc tính:  
   - `accountNumber` (số tài khoản).  
   - `balance` (số dư).  
2. Cung cấp phương thức:  
   - `deposit(double amount)`: Nạp tiền vào tài khoản (nếu số tiền > 0).  
   - `withdraw(double amount)`: Rút tiền (nếu đủ số dư).  
3. Viết chương trình:  
   - Tạo một tài khoản ngân hàng.  
   - Nạp tiền, rút tiền, và hiển thị số dư hiện tại.  

**Gợi ý:**  
```java
public class BankAccount {
    private String accountNumber;
    private double balance;

    public BankAccount(String accountNumber) {
        this.accountNumber = accountNumber;
        this.balance = 0;
    }

    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        } else {
            System.out.println("Số tiền nạp không hợp lệ!");
        }
    }

    public void withdraw(double amount) {
        if (amount > balance) {
            System.out.println("Số dư không đủ!");
        } else {
            balance -= amount;
        }
    }

    public void showBalance() {
        System.out.println("Số dư hiện tại: " + balance);
    }
}
```

---

### **Bài 5: Tính diện tích và chu vi hình tròn**  
1. Tạo lớp `Circle` với thuộc tính `radius` (bán kính).  
2. Cung cấp các phương thức:  
   - `calculateArea()`: Tính diện tích.  
   - `calculatePerimeter()`: Tính chu vi.  
3. Viết chương trình cho phép người dùng nhập bán kính, sau đó in ra diện tích và chu vi.  

**Công thức:**  
- Diện tích = π * r²  
- Chu vi = 2 * π * r  

--- 

Chúc bạn học tốt! 😊