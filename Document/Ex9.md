## Bài 9

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