### **Ngày 1-2: Nền tảng Java cơ bản**  
**Mục tiêu:**  
- Hiểu các khái niệm cơ bản của Java như biến, kiểu dữ liệu, vòng lặp, và hàm.  

---

## **Lý thuyết Ngày 1: Cơ bản về Java**  

### **1. Tổng quan về Java:**  
- Java là ngôn ngữ lập trình hướng đối tượng, đa nền tảng (WORA - Write Once, Run Anywhere).  
- Các đặc điểm chính:  
  - Đơn giản, bảo mật.  
  - Quản lý bộ nhớ tự động (Garbage Collection).  

---

### **2. Các khái niệm cơ bản trong Java:**  

#### **2.1 Biến và kiểu dữ liệu:**  
- **Biến:** Dùng để lưu trữ dữ liệu, khai báo với kiểu dữ liệu cụ thể.  
- **Các kiểu dữ liệu:**  
  - Nguyên thuỷ: `int`, `float`, `double`, `char`, `boolean`, v.v.  
  - Tham chiếu: `String`, `Array`, `Class`.  

**Ví dụ:**  
```java
int age = 25;           // Kiểu nguyên thuỷ
String name = "Nhất";    // Kiểu tham chiếu
```

---

#### **2.2. Các kiểu dữ liệu nguyên thuỷ trong Java**

Java hỗ trợ 8 kiểu dữ liệu nguyên thuỷ, được chia thành 4 nhóm chính:  

| **Nhóm**            | **Kiểu dữ liệu** | **Kích thước** | **Phạm vi giá trị**                           |
|----------------------|------------------|----------------|-----------------------------------------------|
| Số nguyên           | `byte`          | 1 byte         | -128 đến 127                                  |
|                     | `short`         | 2 bytes        | -32,768 đến 32,767                            |
|                     | `int`           | 4 bytes        | -2,147,483,648 đến 2,147,483,647              |
|                     | `long`          | 8 bytes        | -9,223,372,036,854,775,808 đến 9,223,372,036,854,775,807 |
| Số thực (dấu phẩy động) | `float`         | 4 bytes        | ~ ±3.4E-38 đến ±3.4E+38 (7 chữ số thập phân)  |
|                     | `double`        | 8 bytes        | ~ ±1.7E-308 đến ±1.7E+308 (15 chữ số thập phân) |
| Ký tự               | `char`          | 2 bytes        | 0 đến 65,535 (theo mã Unicode)                |
| Giá trị logic       | `boolean`       | 1 bit          | `true` hoặc `false`                           |

---

#### **2.3. Chi tiết các kiểu dữ liệu**  

##### **Số nguyên**
- **`byte:`** Kiểu số nguyên nhỏ nhất, thường dùng trong các ứng dụng cần tiết kiệm bộ nhớ.  
  ```java
  byte b = 100;  // Giá trị hợp lệ
  byte c = 128;  // Lỗi: Giá trị vượt quá phạm vi
  ```

- **`short:`** Thường dùng cho các hệ thống nhúng hoặc khi cần xử lý số nhỏ hơn `int`.  

- **`int:`** Kiểu dữ liệu số nguyên thông dụng nhất.  

- **`long:`** Dùng khi cần lưu trữ số nguyên lớn, thêm hậu tố `L` khi khai báo.  
  ```java
  long x = 10000000000L;
  ```

##### **Số thực**
- **`float:`** Dùng cho số thực nhỏ, yêu cầu hậu tố `f` hoặc `F`.  
  ```java
  float pi = 3.14f;
  ```

- **`double:`** Mặc định của số thực, độ chính xác cao hơn `float`.  

##### **Ký tự**
- **`char:`** Lưu một ký tự Unicode trong phạm vi 16-bit.  

##### **Giá trị logic**
- **`boolean:`** Chỉ có hai giá trị `true` hoặc `false`.  

---

#### **2.4. Bài tập thực hành**  

##### **Bài 1: Xác định kích thước và phạm vi**
Viết chương trình in kích thước và phạm vi của từng kiểu dữ liệu nguyên thuỷ trong Java.  

**Gợi ý:**  
```java
public class DataTypeInfo {
    public static void main(String[] args) {
        System.out.println("Kích thước và phạm vi của các kiểu dữ liệu nguyên thuỷ:");
        System.out.println("byte: " + Byte.BYTES + " byte, phạm vi: " + Byte.MIN_VALUE + " đến " + Byte.MAX_VALUE);
        System.out.println("short: " + Short.BYTES + " bytes, phạm vi: " + Short.MIN_VALUE + " đến " + Short.MAX_VALUE);
        System.out.println("int: " + Integer.BYTES + " bytes, phạm vi: " + Integer.MIN_VALUE + " đến " + Integer.MAX_VALUE);
        System.out.println("long: " + Long.BYTES + " bytes, phạm vi: " + Long.MIN_VALUE + " đến " + Long.MAX_VALUE);
        System.out.println("float: " + Float.BYTES + " bytes, phạm vi: " + Float.MIN_VALUE + " đến " + Float.MAX_VALUE);
        System.out.println("double: " + Double.BYTES + " bytes, phạm vi: " + Double.MIN_VALUE + " đến " + Double.MAX_VALUE);
        System.out.println("char: " + Character.BYTES + " bytes, phạm vi: " + (int) Character.MIN_VALUE + " đến " + (int) Character.MAX_VALUE);
    }
}
```

##### **Bài 2: So sánh kiểu dữ liệu**
1. Khởi tạo các biến với các kiểu dữ liệu: `byte`, `short`, `int`, `long`, `float`, `double`.  
2. Thực hiện phép tính cộng, trừ, nhân, chia và in kết quả.  
3. Quan sát xem kiểu dữ liệu nào phù hợp nhất cho mỗi loại bài toán.  

**Gợi ý:**  
```java
public class DataTypeComparison {
    public static void main(String[] args) {
        byte a = 10;
        short b = 30000;
        int c = 1_000_000;
        long d = 1_000_000_000L;
        float e = 3.14f;
        double f = 2.718281828459045;

        System.out.println("Phép toán với các kiểu dữ liệu:");
        System.out.println("byte + short: " + (a + b));
        System.out.println("int * long: " + (c * d));
        System.out.println("float / double: " + (e / f));
    }
}
```

---

#### **2.5. Ép kiểu trong Java**  

Ép kiểu (type casting) là quá trình chuyển đổi dữ liệu từ kiểu này sang kiểu khác.  

---

#### **2.6. Loại ép kiểu**  

##### **a. Ép kiểu ngầm định (Implicit Casting)**  
- Java tự động thực hiện khi chuyển đổi từ kiểu dữ liệu **nhỏ hơn** sang kiểu **lớn hơn** (widening conversion).  
- Không làm mất dữ liệu.  

**Thứ tự kích thước kiểu dữ liệu:**
`byte → short → int → long → float → double`

**Ví dụ:**  
```java
public class Main {
    public static void main(String[] args) {
        int intValue = 100;
        long longValue = intValue;  // Ép kiểu ngầm định
        double doubleValue = longValue;  // Ép kiểu ngầm định

        System.out.println("Giá trị long: " + longValue);    // Output: 100
        System.out.println("Giá trị double: " + doubleValue); // Output: 100.0
    }
}
```

---

##### **b. Ép kiểu tường minh (Explicit Casting)**  
- Cần chỉ định rõ kiểu dữ liệu mới khi chuyển từ kiểu **lớn hơn** sang kiểu **nhỏ hơn** (narrowing conversion).  
- Có thể gây **mất dữ liệu** hoặc **mất độ chính xác**.  

**Ví dụ:**  
```java
public class Main {
    public static void main(String[] args) {
        double doubleValue = 9.78;
        int intValue = (int) doubleValue;  // Ép kiểu tường minh
        System.out.println("Giá trị int: " + intValue);  // Output: 9
    }
}
```

**Giải thích:**  
- Phần thập phân bị loại bỏ khi ép từ `double` sang `int`.

---

#### **2.7. Ép kiểu giữa kiểu dữ liệu nguyên thuỷ và đối tượng**

##### **a. Tự động (Autoboxing và Unboxing)**  
- **Autoboxing:** Chuyển kiểu dữ liệu nguyên thuỷ thành đối tượng (`int → Integer`).  
- **Unboxing:** Chuyển đối tượng thành kiểu nguyên thuỷ (`Integer → int`).  

**Ví dụ:**  
```java
public class Main {
    public static void main(String[] args) {
        int num = 10;

        // Autoboxing
        Integer boxedNum = num;

        // Unboxing
        int unboxedNum = boxedNum;

        System.out.println("Autoboxing: " + boxedNum);  // Output: 10
        System.out.println("Unboxing: " + unboxedNum);  // Output: 10
    }
}
```

---

#### **2.8. Bài tập thực hành**

##### **Bài 1: Ép kiểu ngầm định**  
1. Khai báo một biến `int`.  
2. Chuyển đổi giá trị biến đó thành `long` và `double`.  
3. In kết quả ra màn hình.

**Gợi ý:**  
```java
public class ImplicitCasting {
    public static void main(String[] args) {
        int intValue = 50;
        long longValue = intValue;
        double doubleValue = longValue;

        System.out.println("Giá trị int: " + intValue);
        System.out.println("Giá trị long: " + longValue);
        System.out.println("Giá trị double: " + doubleValue);
    }
}
```

---

##### **Bài 2: Ép kiểu tường minh**  
1. Khai báo một biến `double`.  
2. Chuyển đổi giá trị biến đó thành `int`.  
3. Quan sát kết quả khi số thập phân bị loại bỏ.

**Gợi ý:**  
```java
public class ExplicitCasting {
    public static void main(String[] args) {
        double doubleValue = 123.456;
        int intValue = (int) doubleValue;

        System.out.println("Giá trị gốc (double): " + doubleValue);
        System.out.println("Giá trị sau khi ép kiểu (int): " + intValue);
    }
}
```

---

##### **Bài 3: Autoboxing và Unboxing**  
1. Tạo một danh sách (`ArrayList`) kiểu `Integer`.  
2. Thêm các số nguyên vào danh sách bằng kiểu `int`.  
3. Tính tổng các giá trị trong danh sách bằng cách sử dụng unboxing.

**Gợi ý:**  
```java
import java.util.ArrayList;

public class AutoboxingUnboxing {
    public static void main(String[] args) {
        ArrayList<Integer> numbers = new ArrayList<>();
        numbers.add(10);  // Autoboxing
        numbers.add(20);
        numbers.add(30);

        int sum = 0;
        for (Integer num : numbers) {
            sum += num;  // Unboxing
        }

        System.out.println("Tổng: " + sum);  // Output: 60
    }
}
```

---

### **3. Tham trị và tham chiếu trong Java**  

#### **3.1. Định nghĩa:**  
- **Tham trị (Pass by Value):**  
  - Java chỉ truyền giá trị của biến vào phương thức, không thay đổi giá trị thực sự của biến ngoài phương thức.  
  - Áp dụng cho kiểu dữ liệu nguyên thuỷ (`int`, `double`, `boolean`, v.v.).  

- **Tham chiếu (Pass by Reference):**  
  - Java không hỗ trợ hoàn toàn tham chiếu, nhưng với các đối tượng, nó truyền giá trị tham chiếu (địa chỉ trong bộ nhớ).  
  - Khi thay đổi thuộc tính của đối tượng trong phương thức, thay đổi này phản ánh bên ngoài.

---

#### **3.2. Ví dụ về tham trị:**  
```java
public class Main {
    public static void main(String[] args) {
        int x = 5;
        changeValue(x);
        System.out.println("Giá trị sau khi gọi hàm: " + x);  // Output: 5
    }

    public static void changeValue(int number) {
        number = 10;
    }
}
```

**Giải thích:**  
- `x` được truyền vào hàm `changeValue` theo giá trị.  
- Thay đổi trong `changeValue` không ảnh hưởng đến `x` trong hàm `main`.

---

#### **3.3. Ví dụ về tham chiếu:**  
```java
class Person {
    String name;
}

public class Main {
    public static void main(String[] args) {
        Person person = new Person();
        person.name = "Nhất";
        changeName(person);
        System.out.println("Tên sau khi gọi hàm: " + person.name);  // Output: Nick
    }

    public static void changeName(Person p) {
        p.name = "Nick";
    }
}
```

**Giải thích:**  
- Đối tượng `person` được truyền vào hàm `changeName` theo tham chiếu.  
- Khi thay đổi `name` trong hàm `changeName`, thay đổi này ảnh hưởng đến đối tượng bên ngoài.

---

### **4. Câu lệnh điều kiện (if-else):**  
- Dùng để kiểm tra và thực hiện hành động theo điều kiện.  

**Ví dụ:**  
```java
if (age >= 18) {
    System.out.println("Bạn đã đủ tuổi trưởng thành.");
} else {
    System.out.println("Bạn chưa đủ tuổi trưởng thành.");
}
```

---

### **5. Câu lệnh điều kiện (switch-case):**  
- Câu lệnh `switch-case` trong Java dùng để kiểm tra giá trị của một biểu thức và thực thi một nhánh tương ứng. Nó thường được sử dụng thay thế cho chuỗi các câu lệnh `if-else if` khi kiểm tra nhiều giá trị của một biến.

#### **5.1. Cấu trúc của `switch-case`**

```java
switch (biểu_thức) {
    case giá_trị_1:
        // Mã lệnh cho giá trị 1
        break;  // Thoát khỏi khối switch
    case giá_trị_2:
        // Mã lệnh cho giá trị 2
        break;
    // ...
    default:
        // Mã lệnh mặc định nếu không có case nào khớp
}
```

**Chi tiết:**
- **`biểu_thức`**: Một giá trị hoặc biểu thức (phải là kiểu `byte`, `short`, `int`, `char`, `String`, hoặc `enum` từ Java 7 trở lên).  
- **`case`**: Kiểm tra giá trị cụ thể, nếu khớp sẽ thực thi các lệnh trong nhánh đó.  
- **`break`**: Kết thúc câu lệnh `switch` để tránh thực thi các nhánh khác.  
- **`default`**: (Không bắt buộc) Được thực thi nếu không có nhánh nào khớp.  

---

##### **Ví dụ 1: Sử dụng `switch` với số nguyên**
```java
public class Main {
    public static void main(String[] args) {
        int day = 3;  // Giá trị ngày
        switch (day) {
            case 1:
                System.out.println("Thứ Hai");
                break;
            case 2:
                System.out.println("Thứ Ba");
                break;
            case 3:
                System.out.println("Thứ Tư");
                break;
            default:
                System.out.println("Không phải ngày hợp lệ");
        }
    }
}
```

**Kết quả:**
```
Thứ Tư
```

---

##### **Ví dụ 2: Sử dụng `switch` với chuỗi**
```java
public class Main {
    public static void main(String[] args) {
        String role = "admin";
        switch (role) {
            case "admin":
                System.out.println("Quản trị viên");
                break;
            case "user":
                System.out.println("Người dùng");
                break;
            case "guest":
                System.out.println("Khách");
                break;
            default:
                System.out.println("Không xác định vai trò");
        }
    }
}
```

**Kết quả:**
```
Quản trị viên
```

---

#### **5.2. Lưu ý khi sử dụng `switch-case`**

1. **Cần sử dụng `break` để tránh "fall-through":**
   Nếu không có `break`, các câu lệnh trong nhánh tiếp theo sẽ được thực thi.

   **Ví dụ:**
   ```java
   int number = 2;
   switch (number) {
       case 1:
           System.out.println("Một");
       case 2:
           System.out.println("Hai");
       case 3:
           System.out.println("Ba");
       default:
           System.out.println("Mặc định");
   }
   ```
   **Kết quả:**
   ```
   Hai
   Ba
   Mặc định
   ```

2. **`default` không bắt buộc, nhưng nên có:**
   - Nếu không có `default`, chương trình sẽ không thực hiện gì khi không có `case` nào khớp.  

3. **Không được sử dụng các kiểu dữ liệu phức tạp:**  
   Biểu thức trong `switch` phải là `byte`, `short`, `int`, `char`, `String`, hoặc `enum`.  

---

#### **5.3. Bài tập thực hành**

##### **Bài 1: Kiểm tra ngày trong tuần**
Viết chương trình kiểm tra ngày trong tuần dựa vào số từ 1 đến 7.  
- `1`: Thứ Hai  
- `2`: Thứ Ba  
- ...  
- `7`: Chủ Nhật  
- Số khác: "Không hợp lệ".

**Gợi ý:**
```java
public class DayOfWeek {
    public static void main(String[] args) {
        int day = 5;  // Thay đổi giá trị này để kiểm tra
        switch (day) {
            case 1:
                System.out.println("Thứ Hai");
                break;
            case 2:
                System.out.println("Thứ Ba");
                break;
            case 3:
                System.out.println("Thứ Tư");
                break;
            case 4:
                System.out.println("Thứ Năm");
                break;
            case 5:
                System.out.println("Thứ Sáu");
                break;
            case 6:
                System.out.println("Thứ Bảy");
                break;
            case 7:
                System.out.println("Chủ Nhật");
                break;
            default:
                System.out.println("Không hợp lệ");
        }
    }
}
```

---

##### **Bài 2: Xác định tháng theo mùa**
Viết chương trình xác định mùa dựa vào số tháng (1-12).  
- `1, 2, 3`: Mùa Xuân  
- `4, 5, 6`: Mùa Hạ  
- `7, 8, 9`: Mùa Thu  
- `10, 11, 12`: Mùa Đông  
- Khác: "Không hợp lệ".

**Gợi ý:**
```java
public class SeasonCheck {
    public static void main(String[] args) {
        int month = 9;  // Thay đổi giá trị để kiểm tra
        switch (month) {
            case 1: case 2: case 3:
                System.out.println("Mùa Xuân");
                break;
            case 4: case 5: case 6:
                System.out.println("Mùa Hạ");
                break;
            case 7: case 8: case 9:
                System.out.println("Mùa Thu");
                break;
            case 10: case 11: case 12:
                System.out.println("Mùa Đông");
                break;
            default:
                System.out.println("Không hợp lệ");
        }
    }
}
```

---

### **6 Vòng lặp (for, while, do-while):**  
- **for:** Lặp với số lần xác định.  
- **while:** Lặp khi điều kiện còn đúng.  
- **do-while:** Lặp ít nhất một lần, kiểm tra điều kiện sau.  

**Ví dụ:**  
```java
for (int i = 0; i < 5; i++) {
    System.out.println("Lần lặp: " + i);
}
```

#### **6.1 Cấu trúc cơ bản**:

##### **a. Vòng lặp `for`**
```java
for (khởi_tạo; điều_kiện; cập_nhật) {
    // Các câu lệnh thực thi
}
```

- **Khởi tạo**: Khai báo và khởi tạo biến đếm (thường là `int`).
- **Điều kiện**: Điều kiện kiểm tra, vòng lặp sẽ tiếp tục nếu điều kiện là `true`.
- **Cập nhật**: Cập nhật giá trị của biến đếm sau mỗi lần lặp (thường là tăng hoặc giảm).

**Ví dụ:**  
```java
public class Main {
    public static void main(String[] args) {
        for (int i = 1; i <= 5; i++) {
            System.out.println("Giá trị của i: " + i);
        }
    }
}
```

**Kết quả:**
```
Giá trị của i: 1
Giá trị của i: 2
Giá trị của i: 3
Giá trị của i: 4
Giá trị của i: 5
```

##### **b. Vòng lặp `while`**
```java
while (điều_kiện) {
    // Các câu lệnh thực thi
}
```

- **Điều kiện**: Câu lệnh kiểm tra điều kiện trước khi bắt đầu vòng lặp. Nếu điều kiện là `true`, vòng lặp sẽ tiếp tục.

**Ví dụ:**  
```java
public class Main {
    public static void main(String[] args) {
        int i = 1;
        while (i <= 5) {
            System.out.println("Giá trị của i: " + i);
            i++;  // Tăng giá trị của i
        }
    }
}
```

**Kết quả:**
```
Giá trị của i: 1
Giá trị của i: 2
Giá trị của i: 3
Giá trị của i: 4
Giá trị của i: 5
```

##### **c. Vòng lặp `do-while`**
```java
do {
    // Các câu lệnh thực thi
} while (điều_kiện);
```

- **Điều kiện**: Câu lệnh kiểm tra điều kiện sau khi thực hiện các câu lệnh trong khối `do`. Nếu điều kiện là `true`, vòng lặp sẽ tiếp tục.

**Ví dụ:**  
```java
public class Main {
    public static void main(String[] args) {
        int i = 1;
        do {
            System.out.println("Giá trị của i: " + i);
            i++;
        } while (i <= 5);
    }
}
```

**Kết quả:**
```
Giá trị của i: 1
Giá trị của i: 2
Giá trị của i: 3
Giá trị của i: 4
Giá trị của i: 5
```

#### **6.2 Chuyển đổi giữa các vòng lặp**  

**Cách chuyển đổi:**  
- Mọi vòng lặp có thể được viết lại bằng các loại vòng lặp khác nhau bằng cách thay đổi cấu trúc lặp.

---

**Ví dụ 1: Từ `for` sang `while`:**  
```java
// Dùng for
for (int i = 0; i < 5; i++) {
    System.out.println("Lần lặp: " + i);
}

// Chuyển sang while
int i = 0;
while (i < 5) {
    System.out.println("Lần lặp: " + i);
    i++;
}
```

---

**Ví dụ 2: Từ `while` sang `do-while`:**  
```java
// Dùng while
int i = 0;
while (i < 5) {
    System.out.println("Lần lặp: " + i);
    i++;
}

// Chuyển sang do-while
int j = 0;
do {
    System.out.println("Lần lặp: " + j);
    j++;
} while (j < 5);
```

---

#### **6.3. Bài tập thực hành:**  
1. **Chuyển đổi vòng lặp:**  
   Viết một vòng lặp `for` tính tổng các số từ 1 đến 10 và chuyển nó sang `while` và `do-while`.  

2. **In bảng cửu chương:**  
   Sử dụng `while` để in bảng cửu chương từ 2 đến 9, sau đó chuyển đổi sang `for`.  

---

### **7. Hàm trong Java:**  
- Hàm (method) giúp chia nhỏ chương trình thành các khối mã tái sử dụng.  
- Cấu trúc hàm:  
  ```java
  <kiểu_trả_về> <tên_hàm>(<tham_số>) {
      // Nội dung hàm
      return giá_trị; // (tuỳ chọn)
  }
  ```

**Ví dụ:**  
```java
public static int sum(int a, int b) {
    return a + b;
}
```

---

### **8. Mảng và Mảng Đa Chiều**
#### **8.1. Mảng trong Java**

Mảng là một cấu trúc dữ liệu dùng để lưu trữ nhiều giá trị của cùng một kiểu dữ liệu. Mảng có kích thước cố định khi được khởi tạo, nghĩa là bạn không thể thay đổi số lượng phần tử của mảng sau khi đã tạo.

---

##### **8.1.1. Các cách khởi tạo mảng**

###### **a. Khởi tạo mảng với kích thước cố định**
Khi khởi tạo mảng với kích thước cố định, bạn phải chỉ định số lượng phần tử khi khai báo mảng. Các giá trị trong mảng sẽ được khởi tạo theo kiểu mặc định (ví dụ: `0` cho số nguyên, `null` cho đối tượng).

```java
int[] numbers = new int[5];  // Khởi tạo mảng số nguyên có 5 phần tử
```

- **Ví dụ:** 
```java
public class Main {
    public static void main(String[] args) {
        int[] numbers = new int[5];  // Mảng 5 phần tử, giá trị mặc định là 0

        for (int i = 0; i < numbers.length; i++) {
            System.out.println("Giá trị tại index " + i + ": " + numbers[i]);
        }
    }
}
```

**Kết quả:**
```
Giá trị tại index 0: 0
Giá trị tại index 1: 0
Giá trị tại index 2: 0
Giá trị tại index 3: 0
Giá trị tại index 4: 0
```

---

###### **b. Khởi tạo mảng và khởi tạo trực tiếp giá trị**

Khi bạn biết trước các giá trị của mảng, bạn có thể khởi tạo mảng bằng cách cung cấp các giá trị ngay khi khai báo.

```java
int[] numbers = {10, 20, 30, 40, 50};  // Khởi tạo mảng với giá trị cụ thể
```

- **Ví dụ:** 
```java
public class Main {
    public static void main(String[] args) {
        int[] numbers = {10, 20, 30, 40, 50};

        for (int i = 0; i < numbers.length; i++) {
            System.out.println("Giá trị tại index " + i + ": " + numbers[i]);
        }
    }
}
```

**Kết quả:**
```
Giá trị tại index 0: 10
Giá trị tại index 1: 20
Giá trị tại index 2: 30
Giá trị tại index 3: 40
Giá trị tại index 4: 50
```

---

###### **c. Khởi tạo mảng đa chiều**

Mảng đa chiều là mảng có nhiều chiều, ví dụ mảng 2 chiều là mảng của các mảng (bảng). Trong Java, mảng đa chiều thường được sử dụng để đại diện cho các bảng dữ liệu hoặc ma trận.

#### **8.2. Mảng 2 chiều (Ma trận)**

Để khai báo và khởi tạo mảng 2 chiều, bạn có thể sử dụng cú pháp sau:

```java
type[][] arrayName = new type[row][column];
```

Hoặc khởi tạo trực tiếp giá trị:

```java
int[][] matrix = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```

- **Ví dụ 1: Mảng 2 chiều**  
```java
public class Main {
    public static void main(String[] args) {
        int[][] matrix = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };

        // In các phần tử của mảng 2 chiều
        for (int i = 0; i < matrix.length; i++) {
            for (int j = 0; j < matrix[i].length; j++) {
                System.out.print(matrix[i][j] + " ");
            }
            System.out.println();  // Xuống dòng sau mỗi hàng
        }
    }
}
```

**Kết quả:**
```
1 2 3 
4 5 6 
7 8 9 
```

---

#### **8.3. Mảng 3 chiều**

Mảng 3 chiều có thể được hình dung như một bảng với nhiều lớp. Bạn có thể khai báo mảng 3 chiều như sau:

```java
int[][][] array = new int[2][3][4];  // Mảng 3 chiều với 2 lớp, 3 hàng, 4 cột
```

Hoặc khởi tạo trực tiếp giá trị:

```java
int[][][] array = {
    {
        {1, 2, 3, 4},
        {5, 6, 7, 8},
        {9, 10, 11, 12}
    },
    {
        {13, 14, 15, 16},
        {17, 18, 19, 20},
        {21, 22, 23, 24}
    }
};
```

- **Ví dụ 2: Mảng 3 chiều**  
```java
public class Main {
    public static void main(String[] args) {
        int[][][] array = {
            {
                {1, 2, 3, 4},
                {5, 6, 7, 8},
                {9, 10, 11, 12}
            },
            {
                {13, 14, 15, 16},
                {17, 18, 19, 20},
                {21, 22, 23, 24}
            }
        };

        // In các phần tử của mảng 3 chiều
        for (int i = 0; i < array.length; i++) {
            for (int j = 0; j < array[i].length; j++) {
                for (int k = 0; k < array[i][j].length; k++) {
                    System.out.print(array[i][j][k] + " ");
                }
                System.out.println();  // Xuống dòng sau mỗi hàng
            }
            System.out.println();  // Xuống dòng sau mỗi lớp
        }
    }
}
```

**Kết quả:**
```
1 2 3 4 
5 6 7 8 
9 10 11 12 

13 14 15 16 
17 18 19 20 
21 22 23 24 
```

---

#### **8.4. Các thao tác với mảng**

- **Truy cập phần tử của mảng**: Bạn có thể truy cập các phần tử trong mảng bằng cách sử dụng chỉ số (index). Chỉ số trong Java bắt đầu từ 0.
    ```java
    int value = array[0];  // Truy cập phần tử đầu tiên
    ```

- **Sửa giá trị của phần tử**: Bạn có thể thay đổi giá trị của phần tử trong mảng bằng cách gán lại giá trị.
    ```java
    array[0] = 10;  // Thay đổi giá trị của phần tử đầu tiên thành 10
    ```

- **Đếm số phần tử trong mảng**: Bạn có thể sử dụng thuộc tính `length` của mảng để lấy số lượng phần tử trong mảng.
    ```java
    int size = array.length;  // Đếm số phần tử trong mảng
    ```

---

#### **8.5. Bài tập thực hành**

##### **Bài 1: Mảng 1 chiều**
1. Khởi tạo một mảng số nguyên có 6 phần tử và gán giá trị vào mảng đó. Sau đó, sử dụng vòng lặp `for` để in ra các phần tử trong mảng.

**Gợi ý:**
```java
public class ArrayOneDim {
    public static void main(String[] args) {
        int[] numbers = {5, 10, 15, 20, 25, 30};

        for (int i = 0; i < numbers.length; i++) {
            System.out.println("Phần tử tại index " + i + ": " + numbers[i]);
        }
    }
}
```

##### **Bài 2: Mảng 2 chiều**
1. Khởi tạo một mảng 2 chiều có 3 hàng và 4 cột, sau đó gán giá trị vào từng phần tử của mảng và in mảng ra màn hình.

**Gợi ý:**
```java
public class ArrayTwoDim {
    public static void main(String[] args) {
        int[][] matrix = {
            {1, 2, 3, 4},
            {5, 6, 7, 8},
            {9, 10, 11, 12}
        };

        for (int i = 0; i < matrix.length; i++) {
            for (int j = 0; j < matrix[i].length; j++) {
                System.out.print(matrix[i][j] + " ");
            }
            System.out.println();
        }
    }
}
```

---

## **Bài tập thực hành Ngày 1:**  

### **Bài 1: Tính toán tuổi trưởng thành**  
Viết chương trình nhập tuổi từ người dùng, kiểm tra và in ra kết quả:  
- Nếu >= 18: "Bạn đã đủ tuổi trưởng thành."  
- Nếu < 18: "Bạn chưa đủ tuổi trưởng thành."  

**Gợi ý:**  
Sử dụng `Scanner` để nhập dữ liệu:  
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Nhập tuổi của bạn: ");
        int age = scanner.nextInt();

        if (age >= 18) {
            System.out.println("Bạn đã đủ tuổi trưởng thành.");
        } else {
            System.out.println("Bạn chưa đủ tuổi trưởng thành.");
        }
    }
}
```

---

### **Bài 2: Tính tổng các số chẵn từ 1 đến n**  
Viết chương trình nhập một số nguyên `n` từ người dùng và tính tổng các số chẵn từ 1 đến `n`.  

**Gợi ý:**  
Sử dụng vòng lặp `for`.  

**Ví dụ:**  
Input: `n = 10`  
Output: `Tổng = 30`  

---

### **Bài 3: Tham trị**  
Viết chương trình:  
1. Khai báo một biến `int x = 10`.  
2. Tạo hàm `modifyValue(int number)` thay đổi `number = 50`.  
3. Gọi hàm từ `main()` và kiểm tra giá trị `x` sau khi gọi hàm.  

---

### **Bài 4: Tham chiếu**  
Viết chương trình:  
1. Tạo lớp `Rectangle` với thuộc tính `width`, `height`.  
2. Tạo hàm `updateDimensions(Rectangle r)` để thay đổi `width` và `height`.  
3. Khởi tạo một đối tượng `Rectangle`, gọi hàm `updateDimensions()` và kiểm tra kết quả.  

**Gợi ý:**  
```java
class Rectangle {
    int width;
    int height;
}

public class Main {
    public static void main(String[] args) {
        Rectangle rect = new Rectangle();
        rect.width = 5;
        rect.height = 10;

        updateDimensions(rect);
        System.out.println("Chiều rộng: " + rect.width + ", Chiều cao: " + rect.height); // Output: 20, 40
    }

    public static void updateDimensions(Rectangle r) {
        r.width = 20;
        r.height = 40;
    }
}
```

---

Chúc bạn học tốt! 😊