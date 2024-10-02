## Bài 8

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

