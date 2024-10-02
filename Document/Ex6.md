## Bài 6

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