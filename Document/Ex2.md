## Bài 2

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


### Collection
- `Collections` trong C# là một nhóm các lớp và giao diện được sử dụng để lưu trữ và quản lý một tập hợp các đối tượng. Các `collection` cung cấp nhiều phương thức để thêm, xóa, tìm kiếm và truy cập các phần tử trong tập hợp. Các `collection` thường được sử dụng thay cho mảng khi bạn cần khả năng linh hoạt hơn trong việc quản lý dữ liệu.

- Một số loại collection phổ biến trong C# bao gồm:

   + `ArrayList`
    + `HashTable`
   +  `List<T>`
    + `Dictionary<TKey, TValue>`
    + `SortedList<TKey, TValue>`

### ArrayList

- `ArrayList` là một collection có khả năng thay đổi kích thước, cho phép bạn thêm và xóa các phần tử mà không cần phải xác định kích thước trước. `ArrayList` có thể chứa các đối tượng của bất kỳ kiểu dữ liệu nào.

```C#
ArrayList arrayList = new ArrayList();
arrayList.Add("Hello");
arrayList.Add(10);
arrayList.Add(3.14);
```
```C#
using System;
using System.Collections;

class Program
{
    static void Main()
    {
        ArrayList arrayList = new ArrayList();
        arrayList.Add("Apple");
        arrayList.Add("Banana");
        arrayList.Add("Cherry");

        Console.WriteLine("ArrayList elements:");
        foreach (var item in arrayList)
        {
            Console.WriteLine(item);
        }

        // Xóa một phần tử
        arrayList.Remove("Banana");

        Console.WriteLine("After removing Banana:");
        foreach (var item in arrayList)
        {
            Console.WriteLine(item);
        }
    }
}
```

### Phương thức Sort

- `Sort` là một phương thức có sẵn trong nhiều collection để sắp xếp các phần tử. Khi sử dụng `Sort` trên `ArrayList`, các phần tử sẽ được sắp xếp theo thứ tự tăng dần.

```C#

using System;
using System.Collections;

class Program
{
    static void Main()
    {
        ArrayList arrayList = new ArrayList() { 5, 2, 8, 1, 3 };

        Console.WriteLine("Before sorting:");
        foreach (var item in arrayList)
        {
            Console.WriteLine(item);
        }

        // Sắp xếp ArrayList
        arrayList.Sort();

        Console.WriteLine("After sorting:");
        foreach (var item in arrayList)
        {
            Console.WriteLine(item);
        }
    }
}
```

### HashTable
- `HashTable` là một `collection` lưu trữ các cặp `key-value` (khóa-giá trị), cho phép truy cập nhanh chóng dựa trên khóa. Mỗi khóa trong `HashTable` là duy nhất và không thể trùng lặp.

```C#

Hashtable hashtable = new Hashtable();
hashtable.Add("key1", "value1");
hashtable.Add("key2", "value2");

```
```C#

using System;
using System.Collections;

class Program
{
    static void Main()
    {
        Hashtable hashtable = new Hashtable();
        hashtable.Add("A", 1);
        hashtable.Add("B", 2);
        hashtable.Add("C", 3);

        Console.WriteLine("Hashtable elements:");
        foreach (DictionaryEntry entry in hashtable)
        {
            Console.WriteLine($"Key: {entry.Key}, Value: {entry.Value}");
        }

        // Truy cập giá trị theo khóa
        Console.WriteLine($"Value for key 'B': {hashtable["B"]}");
    }
}

```
### SortedList

-` SortedList` là một `collection` kết hợp giữa `ArrayList` và `HashTable`. Nó lưu trữ các cặp `key-value`, nhưng các phần tử được sắp xếp theo thứ tự tăng dần của khóa. `SortedList` cho phép bạn truy cập các phần tử thông qua khóa và có hiệu suất tốt trong việc truy cập dữ liệu.

```C#

SortedList sortedList = new SortedList();
sortedList.Add("B", 2);
sortedList.Add("A", 1);
sortedList.Add("C", 3);

```

```C#
using System;
using System.Collections;

class Program
{
    static void Main()
    {
        SortedList sortedList = new SortedList();
        sortedList.Add("C", 3);
        sortedList.Add("A", 1);
        sortedList.Add("B", 2);

        Console.WriteLine("SortedList elements:");
        foreach (DictionaryEntry entry in sortedList)
        {
            Console.WriteLine($"Key: {entry.Key}, Value: {entry.Value}");
        }

        // Truy cập giá trị theo khóa
        Console.WriteLine($"Value for key 'A': {sortedList["A"]}");
    }
}
```



### Stack
- `Stack` là một cấu trúc dữ liệu theo nguyên tắc LIFO (Last In, First Out), tức là phần tử được thêm vào sau cùng sẽ được lấy ra trước tiên. Bạn có thể sử dụng `Stack` để quản lý các đối tượng mà bạn muốn truy cập theo thứ tự ngược lại.

```C#

using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        Stack<int> stack = new Stack<int>();
        
        // Thêm phần tử vào stack
        stack.Push(1);
        stack.Push(2);
        stack.Push(3);

        Console.WriteLine("Stack elements:");
        foreach (var item in stack)
        {
            Console.WriteLine(item);
        }

        // Lấy phần tử ra khỏi stack
        Console.WriteLine($"Pop: {stack.Pop()}"); // Lấy ra 3
        Console.WriteLine($"Peek: {stack.Peek()}"); // Xem phần tử trên cùng (2)
    }
}
```



### Queue

- `Queue` là một cấu trúc dữ liệu theo nguyên tắc FIFO (First In, First Out), tức là phần tử được thêm vào đầu tiên sẽ được lấy ra đầu tiên. `Queue` thường được sử dụng trong các ứng dụng như xử lý sự kiện hoặc các tác vụ cần quản lý theo thứ tự.

```C#

using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        Queue<string> queue = new Queue<string>();
        
        // Thêm phần tử vào queue
        queue.Enqueue("Apple");
        queue.Enqueue("Banana");
        queue.Enqueue("Cherry");

        Console.WriteLine("Queue elements:");
        foreach (var item in queue)
        {
            Console.WriteLine(item);
        }

        // Lấy phần tử ra khỏi queue
        Console.WriteLine($"Dequeue: {queue.Dequeue()}"); // Lấy ra Apple
        Console.WriteLine($"Peek: {queue.Peek()}"); // Xem phần tử đầu tiên (Banana)
    }
}
```

### Generic

- `Generic` cho phép bạn định nghĩa các lớp, phương thức, và cấu trúc mà không cần chỉ định kiểu dữ liệu cụ thể. Điều này giúp tăng tính linh hoạt và tái sử dụng mã.

```C#

using System;

class GenericClass<T>
{
    public T GenericMethod(T param)
    {
        return param;
    }
}

class Program
{
    static void Main()
    {
        GenericClass<int> intObj = new GenericClass<int>();
        Console.WriteLine(intObj.GenericMethod(5)); // 5

        GenericClass<string> stringObj = new GenericClass<string>();
        Console.WriteLine(stringObj.GenericMethod("Hello")); // Hello
    }
}
```

### List

- `List<T>` là một `collection` có khả năng thay đổi kích thước, tương tự như `ArrayList`, nhưng chỉ có thể chứa các đối tượng cùng kiểu `T`. Điều này giúp bảo vệ dữ liệu và cải thiện hiệu suất.

```C#
using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        List<string> list = new List<string> { "Apple", "Banana", "Cherry" };

        Console.WriteLine("List elements:");
        foreach (var item in list)
        {
            Console.WriteLine(item);
        }

        // Thêm phần tử
        list.Add("Date");

        // Xóa phần tử
        list.Remove("Banana");

        Console.WriteLine("After modification:");
        foreach (var item in list)
        {
            Console.WriteLine(item);
        }
    }
}
```

### Dictionary

- `Dictionary<TKey, TValue>` là một `collection` lưu trữ các cặp `key-value`, cho phép truy cập nhanh chóng theo khóa. Các khóa là duy nhất và không thể trùng lặp.

```C#
using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        Dictionary<string, int> dictionary = new Dictionary<string, int>
        {
            { "Apple", 1 },
            { "Banana", 2 },
            { "Cherry", 3 }
        };

        Console.WriteLine("Dictionary elements:");
        foreach (var kvp in dictionary)
        {
            Console.WriteLine($"Key: {kvp.Key}, Value: {kvp.Value}");
        }

        // Truy cập giá trị theo khóa
        Console.WriteLine($"Value for key 'Banana': {dictionary["Banana"]}");
    }
}
```

### Delegate

- `Delegate` là một kiểu dữ liệu cho phép bạn lưu trữ tham chiếu đến các phương thức. Bạn có thể sử dụng `delegate` để gọi phương thức một cách gián tiếp, làm cho việc xử lý sự kiện trở nên dễ dàng hơn.

```C#
using System;

delegate void DisplayMessage(string message);

class Program
{
    static void Main()
    {
        DisplayMessage msg = ShowMessage;
        msg("Hello, World!");
    }

    static void ShowMessage(string message)
    {
        Console.WriteLine(message);
    }
}
```

### Event

- `Sự kiện (Event)` trong C# được sử dụng để xử lý thông báo khi một hành động xảy ra. Sự kiện thường kết hợp với `delegate` để cho phép một lớp thông báo cho các lớp khác về các hành động cụ thể.

```C#

using System;

class Publisher
{
    public event Action<string> Notify;

    public void RaiseEvent(string message)
    {
        Notify?.Invoke(message);
    }
}

class Subscriber
{
    public void Subscribe(Publisher publisher)
    {
        publisher.Notify += OnNotify;
    }

    private void OnNotify(string message)
    {
        Console.WriteLine($"Received message: {message}");
    }
}

class Program
{
    static void Main()
    {
        Publisher publisher = new Publisher();
        Subscriber subscriber = new Subscriber();

        subscriber.Subscribe(publisher);
        publisher.RaiseEvent("Hello, Event!");
    }
}
```

### Lambda

- `Lambda expressions` là một cách ngắn gọn để định nghĩa các phương thức ẩn danh. Chúng thường được sử dụng với `delegate` và các phương thức `LINQ`.

```C#

using System;

class Program
{
    static void Main()
    {
        Func<int, int> square = x => x * x;
        Console.WriteLine($"Square of 5: {square(5)}");
    }
}

```
### Linq

- `LINQ` (Language Integrated Query) cho phép bạn sử dụng cú pháp truy vấn trực tiếp trong C#. Nó hỗ trợ việc truy xuất dữ liệu từ các nguồn khác nhau như mảng, danh sách, cơ sở dữ liệu, v.v.

```C#

using System;
using System.Collections.Generic;
using System.Linq;

class Program
{
    static void Main()
    {
        List<int> numbers = new List<int> { 1, 2, 3, 4, 5, 6 };

        // Sử dụng LINQ để lọc các số chẵn
        var evenNumbers = from n in numbers
                          where n % 2 == 0
                          select n;

        Console.WriteLine("Even numbers:");
        foreach (var number in evenNumbers)
        {
            Console.WriteLine(number);
        }
    }
}
```