## Bài 7

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