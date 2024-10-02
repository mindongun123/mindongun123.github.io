## Bài 2


### Từ Khóa Var

- Từ khóa var cho phép trình biên dịch suy ra kiểu của biến dựa trên giá trị được gán cho nó. Nó chỉ có thể được sử dụng khi giá trị gán cho biến đã xác định rõ kiểu

```C#
var number = 10;  // Kiểu của number là int
var text = "Hello";  // Kiểu của text là string
```
- `Lưu ý`: Khi sử dụng var, kiểu dữ liệu của biến được xác định tại thời điểm biên dịch và không thể thay đổi sau đó.


### Từ khóa Dynamic
- Từ khóa dynamic cho phép một biến thay đổi kiểu dữ liệu trong quá trình thực thi (runtime). Không giống var, kiểu của dynamic không được xác định tại thời điểm biên dịch mà chỉ tại thời gian chạy.

```C#
dynamic data = 10;
Console.WriteLine(data);  // In ra 10 (kiểu int)
data = "Hello";
Console.WriteLine(data);  // In ra Hello (kiểu string)
```

- `Lưu ý`: Sử dụng dynamic có thể dẫn đến lỗi chỉ được phát hiện tại thời gian chạy, vì vậy cần thận trọng khi dùng.

### Vòng lặp
- Vòng lặp cho phép thực thi một đoạn mã nhiều lần dựa trên điều kiện nhất định.

### Vòng lặp for
- Vòng lặp for thường được sử dụng khi bạn biết trước số lần lặp. Cấu trúc của vòng lặp for bao gồm 3 phần: khởi tạo biến, điều kiện lặp, và thay đổi biến sau mỗi lần lặp.

```C#
for (int i = 0; i < 5; i++)
{
    Console.WriteLine(i);  // In ra 0, 1, 2, 3, 4
}
```

### Vòng lặp while
- Vòng lặp while thực hiện một đoạn mã khi điều kiện kiểm tra là true. Nếu điều kiện không thỏa mãn ngay từ đầu, vòng lặp sẽ không thực hiện lần nào.

```C#
int i = 0;
while (i < 5)
{
    Console.WriteLine(i);  // In ra 0, 1, 2, 3, 4
    i++;
}
```
### Vòng lặp do-while

- Vòng lặp do-while luôn thực hiện ít nhất một lần, sau đó mới kiểm tra điều kiện. Nếu điều kiện đúng, vòng lặp tiếp tục; nếu sai, vòng lặp kết thúc.

```C#
int i = 0;
do
{
    Console.WriteLine(i);  // In ra 0, 1, 2, 3, 4
    i++;
} while (i < 5);
```
### Tìm hiểu về Hàm
- Hàm (hay phương thức) là một khối mã thực hiện một chức năng cụ thể. Hàm có thể nhận các tham số và trả về giá trị (hoặc không).

```C#
int AddNumbers(int a, int b)
{
    return a + b;
}

// Gọi hàm
int result = AddNumbers(5, 10);  // result = 15
```


### Biến toàn cục, biến cục bộ

- `Biến cục bộ`: Chỉ có thể truy cập trong một phạm vi nhất định như trong một hàm, vòng lặp hoặc khối mã.
- `Biến toàn cục`: Là biến khai báo trong phạm vi lớp, có thể được truy cập từ bất kỳ phương thức nào trong lớp.

```C#
class Program
{
    // Biến toàn cục
    static int globalVar = 100;

    static void Main(string[] args)
    {
        int localVar = 10;  // Biến cục bộ
        Console.WriteLine(globalVar);  // Truy cập biến toàn cục
        Console.WriteLine(localVar);   // Truy cập biến cục bộ
    }
}
```
### Từ khóa ref và out

- `ref`: Dùng để truyền tham chiếu đến biến, cho phép hàm thay đổi giá trị của biến đó.
- `out`: Cũng truyền tham chiếu, nhưng biến được yêu cầu phải được gán giá trị bên trong hàm trước khi trả về.

Ref
```C#
void Increase(ref int number)
{
    number += 10;
}

int value = 5;
Increase(ref value);
Console.WriteLine(value);  // In ra 15
```



Out
```C#
void GetValues(out int x, out int y)
{
    x = 5;
    y = 10;
}

int a, b;
GetValues(out a, out b);
Console.WriteLine(a);  // In ra 5
Console.WriteLine(b);  // In ra 10
```

-`Lưu ý`: Sử dụng từ khóa `ref` và `out` giúp truyền giá trị tham chiếu thay vì giá trị, có thể làm việc hiệu quả hơn khi xử lý dữ liệu lớn hoặc cần trả về nhiều giá trị từ hàm.



### Mảng một chiều



- `Mảng một chiều` là tập hợp các phần tử có cùng kiểu dữ liệu, được lưu trữ liên tiếp trong bộ nhớ và được truy cập bằng chỉ số (index).

```C#
int[] numbers = new int[5];  // Mảng có 5 phần tử
numbers[0] = 10;
numbers[1] = 20;
numbers[2] = 30;
numbers[3] = 40;
numbers[4] = 50;

// In các phần tử của mảng
for (int i = 0; i < numbers.Length; i++)
{
    Console.WriteLine(numbers[i]);
}
```


### Mảng 2 Chiều

- `Mảng hai chiều` trong C# là một bảng các giá trị được tổ chức dưới dạng hàng và cột. Nó thường được sử dụng để biểu diễn ma trận hoặc bảng.

```C#
int[,] matrix = new int[3, 3];  // Mảng 3x3
matrix[0, 0] = 1;
matrix[0, 1] = 2;
matrix[0, 2] = 3;
matrix[1, 0] = 4;
matrix[1, 1] = 5;
matrix[1, 2] = 6;
matrix[2, 0] = 7;
matrix[2, 1] = 8;
matrix[2, 2] = 9;

// In các phần tử của mảng
for (int i = 0; i < matrix.GetLength(0); i++)
{
    for (int j = 0; j < matrix.GetLength(1); j++)
    {
        Console.Write(matrix[i, j] + " ");
    }
    Console.WriteLine();
}
```

### Foreach

- Câu lệnh foreach được sử dụng để duyệt qua tất cả các phần tử trong một mảng hoặc bất kỳ cấu trúc dữ liệu nào triển khai `IEnumerable` mà không cần sử dụng chỉ số.

```C#
int[] numbers = { 10, 20, 30, 40, 50 };

foreach (int number in numbers)
{
    Console.WriteLine(number);
}
```


### Lớp String

- Lớp String trong C# đại diện cho một chuỗi ký tự bất biến, tức là không thể thay đổi nội dung của nó sau khi được khởi tạo

```C#
string greeting = "Hello";
string name = "John";

// Nối chuỗi
string message = greeting + " " + name + "!";
Console.WriteLine(message);  // Output: Hello John!

// Một số phương thức của String
Console.WriteLine(name.Length);  // Output: 4
Console.WriteLine(name.ToUpper());  // Output: JOHN
Console.WriteLine(name.ToLower());  // Output: john
Console.WriteLine(greeting.Contains("Hel"));  // Output: True
```

- `Lưu ý`: Do `String` là bất biến, khi bạn thao tác với chuỗi (như nối chuỗi, thay thế, cắt chuỗi), thực ra chuỗi mới sẽ được tạo ra, và chuỗi cũ không thay đổi. Điều này có thể gây ra hao phí bộ nhớ nếu thao tác với chuỗi lớn hoặc lặp lại nhiều lần.



### Lớp StringBuilder
- Lớp `StringBuilder` được sử dụng khi bạn cần thực hiện nhiều thao tác với chuỗi mà không muốn tạo nhiều đối tượng `String` mới. `StringBuilder` có thể thay đổi nội dung mà không tạo ra chuỗi mới.

```C#

StringBuilder sb = new StringBuilder("Hello");

// Thêm chuỗi vào StringBuilder
sb.Append(" ");
sb.Append("John");
sb.Append("!");

Console.WriteLine(sb.ToString());  // Output: Hello John!
```

- `Lợi ích`: `StringBuilder` hiệu quả hơn so với `String` khi cần nối, thay thế hoặc thao tác nhiều lần trên chuỗi, vì nó không tạo ra nhiều đối tượng mới trong bộ nhớ như `String` làm.


### Kiểu liệt kê Enum

- `Enum` là kiểu dữ liệu đặc biệt trong C# được sử dụng để định nghĩa một tập hợp các hằng số với tên dễ hiểu, giúp code dễ đọc và dễ bảo trì hơn.

```C#

enum DayOfWeek
{
    Sunday,
    Monday,
    Tuesday,
    Wednesday,
    Thursday,
    Friday,
    Saturday
}
```

- `Lợi ích`: `Enum` giúp code dễ hiểu hơn khi làm việc với các tập hợp giá trị xác định sẵn, ví dụ như các ngày trong tuần, trạng thái của một đối tượng (`on/off, success/failure`), hoặc mức độ ưu tiên.


### OOP

- `OOP` (Object-Oriented Programming) là một phương pháp lập trình dựa trên việc sử dụng đối tượng và lớp. Nó giúp chia nhỏ các vấn đề phức tạp thành các phần nhỏ hơn, dễ quản lý và phát triển hơn. `OOP` có 4 đặc trưng chính:

    + `Tính đóng gói (Encapsulation)`: Dữ liệu và các phương thức liên quan được đóng gói trong một đối tượng. Chỉ các thành phần bên trong đối tượng đó mới có thể truy cập được.
    + `Tính kế thừa (Inheritance)`: Một lớp có thể kế thừa các thuộc tính và phương thức của lớp khác.
    + `Tính đa hình (Polymorphism)`: Cho phép một phương thức hoặc thuộc tính có nhiều cách sử dụng khác nhau (thông qua `overload` hoặc `override`).
    + `Tính trừu tượng (Abstraction)`: Giấu đi các chi tiết thực thi phức tạp, chỉ cung cấp cho người dùng những thông tin cần thiết.

### Class
- Lớp là một khuôn mẫu để tạo ra các đối tượng (`object`). Nó chứa các thuộc tính (dữ liệu) và phương thức (hành động) để mô tả hành vi và trạng thái của đối tượng

```C#

public class Car
{
    // Thuộc tính
    public string brand;
    public string model;
    public int year;

    // Phương thức
    public void Start()
    {
        Console.WriteLine("The car is starting.");
    }
}

//Sử dụng:
Car myCar = new Car();
myCar.brand = "Toyota";
myCar.model = "Corolla";
myCar.year = 2020;

Console.WriteLine(myCar.brand);  // Output: Toyota
myCar.Start();  // Output: The car is starting.

```

### Phương thức khởi tạo (Constructor)
- `Constructor` là một phương thức đặc biệt được gọi khi một đối tượng của lớp được tạo. Nó thường dùng để khởi tạo giá trị ban đầu cho các thuộc tính của đối tượng.

- Tên của `constructor` phải trùng với tên của lớp.
`Constructor` không có kiểu trả về (không cần `void` hay `int`)

```C#

public class Car
{
    public string brand;
    public string model;
    public int year;

    // Constructor
    public Car(string brand, string model, int year)
    {
        this.brand = brand;
        this.model = model;
        this.year = year;
    }

    public void Start()
    {
        Console.WriteLine($"{brand} {model} is starting.");
    }
}

class Program
{
    static void Main()
    {
        // Tạo một đối tượng Car và truyền giá trị cho constructor
        Car myCar = new Car("Honda", "Civic", 2021);
        myCar.Start();  // Output: Honda Civic is starting.
    }
}
```


- `Constructor` mặc định: Nếu bạn không định nghĩa `constructor`, C# sẽ cung cấp một `constructor` mặc định không tham số.

### Phương thức hủy bỏ (Destructor)

- `Destructor` là phương thức được gọi khi đối tượng bị hủy để giải phóng tài nguyên. Trong C#, `destructor` hiếm khi được sử dụng vì hệ thống quản lý bộ nhớ tự động (`garbage collector`) sẽ quản lý việc giải phóng tài nguyên. `Destructor` thường được dùng khi cần giải phóng tài nguyên không quản lý bởi bộ nhớ (ví dụ: tài nguyên hệ thống, file, kết nối cơ sở dữ liệu).

- `Destructor` có cùng tên với lớp, nhưng có dấu ~ ở trước.
- `Destructor` không có tham số và không thể `overload`

```C#

public class Car
{
    public string brand;

    // Constructor
    public Car(string brand)
    {
        this.brand = brand;
        Console.WriteLine($"{brand} is created.");
    }

    // Destructor
    ~Car()
    {
        Console.WriteLine($"{brand} is destroyed.");
    }
}

class Program
{
    static void Main()
    {
        Car myCar = new Car("Ford");
        // Destructor sẽ tự động được gọi khi đối tượng bị hủy (khi chương trình kết thúc).
    }
}
```

- `Lưu ý`: `Destructor` được gọi tự động bởi `garbage collector` khi đối tượng không còn được sử dụng


### Kế thừa (Inheritance)
- `Kế thừa` là một trong những đặc trưng của `OOP` cho phép một lớp (gọi là lớp con) kế thừa các thuộc tính và phương thức từ một lớp khác (gọi là lớp cha). Điều này giúp tái sử dụng mã và tạo ra cấu trúc phân cấp.

```C#

public class ParentClass
{
    public void Display()
    {
        Console.WriteLine("This is a method from the Parent Class.");
    }
}

public class ChildClass : ParentClass
{
    public void Show()
    {
        Console.WriteLine("This is a method from the Child Class.");
    }
}

class Program
{
    static void Main()
    {
        ChildClass child = new ChildClass();
        child.Display();  // Output: This is a method from the Parent Class.
        child.Show();     // Output: This is a method from the Child Class.
    }
}
```

- `Lưu ý`: Trong C#, một lớp chỉ có thể kế thừa từ một lớp cha (kế thừa đơn). Tuy nhiên, một lớp có thể thực hiện nhiều giao diện.

### Đa Hình
- `Đa hình` cho phép các phương thức có cùng tên nhưng hành vi khác nhau tùy theo ngữ cảnh. 
- Có hai loại đa hình:
    + đa hình biên dịch (`compile-time`)
    + đa hình thời gian chạy (`runtime`).

- Đa hình biên dịch (`Method Overloading`): Nạp chồng phương thức cho phép định nghĩa nhiều phương thức có cùng tên nhưng khác tham số (số lượng hoặc kiểu tham số).

```C#

public class Calculator
{
    // Nạp chồng phương thức
    public int Add(int a, int b)
    {
        return a + b;
    }

    public double Add(double a, double b)
    {
        return a + b;
    }

    public int Add(int a, int b, int c)
    {
        return a + b + c;
    }
}

class Program
{
    static void Main()
    {
        Calculator calc = new Calculator();
        Console.WriteLine(calc.Add(5, 10));         // Output: 15
        Console.WriteLine(calc.Add(5.5, 10.2));     // Output: 15.7
        Console.WriteLine(calc.Add(1, 2, 3));        // Output: 6
    }
}
```

- Đa hình thời gian chạy (`Method Overriding`): Khi một lớp con định nghĩa lại phương thức đã được định nghĩa trong lớp cha.

```C#

public class Animal
{
    public virtual void Speak()
    {
        Console.WriteLine("Animal speaks");
    }
}

public class Dog : Animal
{
    public override void Speak()
    {
        Console.WriteLine("Dog barks");
    }
}

class Program
{
    static void Main()
    {
        Animal myDog = new Dog();
        myDog.Speak();  // Output: Dog barks
    }
}
```


### Interface

- `Interface` định nghĩa một tập hợp các phương thức mà lớp thực thi phải triển khai. `Interface` không thể chứa các thuộc tính, phương thức, hoặc `constructor` mà không có thân phương thức (body).

```C#

public interface IAnimal
{
    void Speak();
}

public class Cat : IAnimal
{
    public void Speak()
    {
        Console.WriteLine("Cat meows");
    }
}

public class Dog : IAnimal
{
    public void Speak()
    {
        Console.WriteLine("Dog barks");
    }
}



class Program
{
    static void Main()
    {
        IAnimal myCat = new Cat();
        IAnimal myDog = new Dog();

        myCat.Speak();  // Output: Cat meows
        myDog.Speak();  // Output: Dog barks
    }
}
```


- `Lợi ích`: `Interfaces` giúp đạt được tính đa hình và tách biệt giữa các phương thức đã định nghĩa và cách chúng được triển khai, cho phép xây dựng các hệ thống linh hoạt hơn.


### Nạp chồng (Overload)

- `Nạp chồng` (`overloading`) cho phép bạn định nghĩa nhiều phương thức hoặc toán tử với cùng tên nhưng khác nhau về số lượng hoặc kiểu tham số. Điều này giúp cải thiện khả năng đọc và sử dụng mã.

- Nạp chồng phương thức: Được thực hiện khi có cùng tên nhưng khác số lượng hoặc kiểu tham số.


```C#

public class Display
{
    public void Show(int number)
    {
        Console.WriteLine("Number: " + number);
    }

    public void Show(string text)
    {
        Console.WriteLine("Text: " + text);
    }
}

class Program
{
    static void Main()
    {
        Display display = new Display();
        display.Show(5);          // Output: Number: 5
        display.Show("Hello");    // Output: Text: Hello
    }
}
```


- Nạp chồng toán tử: Trong C#, bạn cũng có thể nạp chồng các toán tử, cho phép bạn định nghĩa cách các toán tử hoạt động với các kiểu dữ liệu tùy chỉnh.

```C#
public class Point
{
    public int X { get; set; }
    public int Y { get; set; }

    public static Point operator +(Point p1, Point p2)
    {
        return new Point { X = p1.X + p2.X, Y = p1.Y + p2.Y };
    }
}

class Program
{
    static void Main()
    {
        Point p1 = new Point { X = 5, Y = 10 };
        Point p2 = new Point { X = 3, Y = 7 };
        Point result = p1 + p2;

        Console.WriteLine($"Result: X = {result.X}, Y = {result.Y}");  // Output: Result: X = 8, Y = 17
    }
}
```

