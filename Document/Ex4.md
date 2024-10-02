## Bài 4

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
