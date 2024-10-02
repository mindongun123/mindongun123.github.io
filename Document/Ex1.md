### Bài 1


### Sử dụng Git

 - `git init` Khởi tạo một repository Git mới trong thư mục hiện tại.
 - `git clone <url>` Sao chép một repository từ URL.
 - `git add <file>` Thêm file vào vùng staging để chuẩn bị commit.
- `git commit -m "message"` Commit thay đổi với một thông điệp ngắn.
- ` git push` Đẩy commit từ local repository lên remote repository.
 - `git pull` Lấy và hợp nhất thay đổi từ remote repository về local.
 - `git status` Kiểm tra trạng thái của các file trong repository.
- `git log` Xem lịch sử commit.

### Tìm hiểu về Biến

```C#
        int age = 25;
        string name = "John";
        bool isStudent = true;
```

### Tìm hiểu về kiểu dữ liệu

- Kiểu dữ liệu trong C# xác định loại giá trị mà một biến có thể lưu trữ. C# chia kiểu dữ liệu thành hai loại chính: `Value types` và `Reference types`.
        
    + `Value types`: Lưu trữ giá trị trực tiếp. Ví dụ: int, float, bool, char.
    + `Reference types`: Lưu trữ tham chiếu tới một địa chỉ bộ nhớ. Ví dụ: string, array, class.

### Stack Và Heap
 - Trong C#, bộ nhớ chia thành hai vùng: `Stack` và `Heap`.

     + `Stack`: Lưu trữ các biến kiểu giá trị (value types) và có cơ chế quản lý tự động (LIFO - Last In, First Out).
    + `Stack` có kích thước nhỏ và nhanh.
    + `Heap`: Lưu trữ các biến kiểu tham chiếu (reference types) như đối tượng hoặc chuỗi. Khi một đối tượng được tạo, nó nằm trên heap, và hệ thống sẽ quản lý bộ nhớ thông qua cơ chế garbage collection.

### Một số kiểu dữ - liệu dựng sẵn

- C# cung cấp nhiều kiểu dữ liệu sẵn có. Dưới đây là một số kiểu dữ liệu thường dùng:
        
    + `int`: Số nguyên (32-bit), phạm vi từ -2,147,483,648 đến 2,147,483,647.
    + `float`: Số thực dấu phẩy động (32-bit).
    + `double`: Số thực dấu phẩy động độ chính xác gấp đôi (64-bit).
    + `bool`: Biểu diễn giá trị logic true hoặc false.
     + `char`: Một ký tự Unicode (16-bit).
    + `string`: Chuỗi ký tự Unicode.

### Tìm hiểu về toán tử - Toán tử toán học
        
- Toán tử toán học:
    + `+`: Cộng
    + `-`: Trừ
    + `*`: Nhân
    + `/`: Chia
     + `%`: Lấy phần dư

### Toán tử Logic
        
- Toán tử logic được sử dụng để kết hợp các biểu thức điều kiện.

    + `&&`: Phép và (logical AND), trả về true nếu cả hai điều kiện đều đúng.
    + `||`: Phép hoặc (logical OR), trả về true nếu một trong hai điều kiện đúng.
    + `!`: Phép phủ định (logical NOT), đảo ngược giá trị boolean.

### Toán tử quan hệ
- Các toán tử quan hệ được sử dụng để so sánh hai giá trị:

    + `==`: Bằng
    + `!=`: Không bằng
    + `>`: Lớn hơn
    + `<`: Nhỏ hơn
    + `>=`: Lớn hơn hoặc bằng
    + `<=`: Nhỏ hơn hoặc bằng 

### Thứ tự ưu tiên của toán tử 

- Trong C#, thứ tự ưu tiên của toán tử ảnh hưởng đến cách biểu thức được đánh giá. Toán tử có ưu tiên cao sẽ được thực hiện trước. 
- Thứ tự ưu tiên: 
    + Toán tử số học (*, /, %) có ưu tiên cao hơn toán tử cộng/trừ (+, -). 
    + Toán tử quan hệ (<, <=,>, >=) được thực hiện sau toán tử số học.
     + Toán tử logic (&&, ||) có ưu tiên thấp hơn so với toán tử so sánh.
    + Phép gán (=) có ưu tiên thấp nhất.


### Hằng số

- Hằng số là các giá trị không thể thay đổi trong suốt quá trình thực thi chương trình. 
- Trong C#, hằng số được khai báo với từ khóa `const`.

``` C#
const double PI = 3.14159;
const int MAX_VALUE = 100;
```

### Ép Kiểu

- Ép kiểu (type casting) trong C# là việc chuyển đổi một giá trị từ kiểu dữ liệu này sang kiểu dữ liệu khác. C# hỗ trợ hai loại ép kiểu chính: ép kiểu ngầm định và ép kiểu tường minh.

     + Ép kiểu ngầm định: Xảy ra khi không có nguy cơ mất dữ liệu (chuyển từ kiểu nhỏ sang kiểu lớn).
    + Ép kiểu tường minh: Yêu cầu lập trình viên chỉ định rõ (chuyển từ kiểu lớn sang kiểu nhỏ).


Ép kiểu ngầm định
```C#
int a = 10;
double b = a; // int chuyển thành double
``` 


Ép kiểu tường minh
```C#
double c = 9.8;
int d = (int)c; // double chuyển thành int (mất phần thập phân)

```
### Parse và TryParse

- `Parse` và `TryParse` dùng để chuyển đổi chuỗi (string) thành các kiểu dữ liệu số.

    + `Parse`: Chuyển đổi chuỗi sang kiểu dữ liệu khác, nhưng nếu chuỗi không hợp lệ, nó sẽ gây ra ngoại lệ (Exception).
    + `TryParse`: Tương tự Parse, nhưng nó không gây ngoại lệ mà trả về true hoặc false để kiểm tra thành công.

Parse

```C#
string numberString = "123";
int number = int.Parse(numberString); // number = 123
```

TryParse

```C#
string invalidString = "abc";
bool success = int.TryParse(invalidString, out int result); // success = false, result = 0
```

### Convert
- Lớp `Convert` cung cấp các phương thức để chuyển đổi các kiểu dữ liệu khác nhau.

```C#
string numberString = "456";
int number = Convert.ToInt32(numberString); // number = 456
double decimalNumber = 12.34;
int roundedNumber = Convert.ToInt32(decimalNumber); // roundedNumber = 12
```

- `Convert` cũng hỗ trợ chuyển đổi từ kiểu số thành chuỗi và ngược lại, cũng như giữa các kiểu dữ liệu khác.

### Câu lệnh rẽ nhánh If-Else

- Câu lệnh `if-else` cho phép bạn thực thi các đoạn mã khác nhau dựa trên điều kiện.

```C#
int age = 20;

if (age >= 18)
{
    Console.WriteLine("Bạn là người trưởng thành.");
}
else
{
    Console.WriteLine("Bạn chưa đủ tuổi.");
}
```

### Switch-Case

- Switch-case là một câu lệnh điều kiện khác thay thế cho if-else khi bạn cần kiểm tra nhiều giá trị của một biến.

```C#
int day = 3;

switch (day)
{
    case 1:
        Console.WriteLine("Thứ Hai");
        break;
    case 2:
        Console.WriteLine("Thứ Ba");
        break;
    case 3:
        Console.WriteLine("Thứ Tư");
        break;
    default:
        Console.WriteLine("Không hợp lệ");
        break;
}
```

- `Lưu ý`: Mỗi case cần có break để thoát khỏi câu lệnh switch khi một điều kiện thỏa mãn.

### Kiểu dữ liệu Object

- `object` là kiểu dữ liệu gốc của tất cả các kiểu dữ liệu trong C#. Mọi kiểu dữ liệu đều có thể được gán cho biến kiểu `object`.

```C#
object myObject;
myObject = 100;     // int
myObject = "Hello"; // string
myObject = 12.34;   // double
```

- Bạn có thể lưu bất kỳ kiểu dữ liệu nào vào object, nhưng khi truy xuất giá trị, bạn cần thực hiện ép kiểu tường minh về kiểu dữ liệu cụ thể.

### Boxing và Unboxing

- `Boxing`: Chuyển đổi một giá trị kiểu dữ liệu giá trị (value type) thành object.
- `Unboxing`: Chuyển đổi ngược từ object về kiểu giá trị ban đầu.

Boxing
```C#
int number = 123;
object boxed = number; // Boxing: Chuyển int thành object
```
Unboxing

```C#
object obj = 123;
int unboxed = (int)obj; // Unboxing: Chuyển object về int
```


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
