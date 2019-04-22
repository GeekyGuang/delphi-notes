1. 静态数组
```
// 自定义数组类型
type
  TDayTemperatures = array [1..24] of Integer;

var
  DayTemp1: TDayTemperatures;

// 也可以直接声明
//var
//  DayTemp1: array[1..24] of Integer;

procedure TForm1.Button1Click(Sender: TObject);
begin
  DayTemp1 [1] := 54;
  DayTemp1 [2] := 52;
  // 此处省略 3-23
  DayTemp1 [24] := 53;
  // The following line causes: E1012 Constant expression violates subrange bounds
  // DayTemp1 [25] := 67;
end;
```
> 静态数组会立即占用大量内存空间

2. Low和High函数确定下限和上限，Length函数确定长度
```
type
  Alp = array[1..26] of Char;  // 注意是用=号

var
 a: Alp;

procedure TForm1.Button1Click(Sender: TObject);
begin
  Show('Low: ' + IntToStr(Low(a)));     // 下限是1
  Show('High: ' + IntToStr(High(a)));   // 上限是26
  show('Length: ' + IntToStr(Length(a)));    // 长度是26
end;
```

3. 动态数组, SetLength(数组名, 长度)
```
var
  Array1: array of Integer; // 声明不指定长度
begin
  // would cause a runtime Range Check error
  // Array1 [1] := 100;
  SetLength (Array1, 10);
  Array1 [1] := 100; // this is OK
  Show (Array1 [1].ToString);
end;
```
```
var
  i: Integer;
  b: array of Integer;
begin
  SetLength(b, 10);
  for i := Low(b) to High(b) do
     b[i] := i;

  for i := Low(b) to High(b) do
     show(b[i].toString);
end;
```

4. copy函数
```
var
  IntArray2: TIntegersArray;
  IntArray3: TIntegersArray;
begin
  // alias
  IntArray2 := IntArray1;  //把1的地址给了2

  // separate copy  //新建了一个完全独立的新数组
  IntArray3 := Copy (IntArray1, Low(IntArray1), Length(IntArray1));

  // modify items
  IntArray2 [1] := 100; //数组1和2同时改变，因为他们存储在同一个空间
  IntArray3 [2] := 100; //只有数组3改变
```

5. 开放数组参数
```
// 数组作为函数参数
function Sum (const A: array of Integer): Integer;
var
  I: Integer;
begin
  Result := 0;
  for I := Low(A) to High(A) do
    Result := Result + A[I];
end;

// format
var
  N: Integer;
  S: string;
begin
  N := 20;
  S := 'Total:';
  Show (Format ('Total: %d', [N]));
  Show (Format ('Int: %d, Float: %f', [N, 12.4]));
  Show (Format ('%s %d', [S, N * 2]));
end;

```

6. 记录record，类似C语言的结构体
```
// 定义
type
  TMyDate = packed record  // packed不是必须的，意思是使用最小的内存空间，即使存取速度会慢
    Year: Integer;
    Month: Byte;
    Day: Byte;
  end;

// 调用
var
  BirthDay: TMyDate;
begin
  BirthDay.Year := 1997;
  BirthDay.Month := 2;
  BirthDay.Day := 14;

  Show ('Born in year ' + BirthDay.Year.ToString);
  Show ('Record size is ' + SizeOf (BirthDay).ToString);
end;
```

```
function ShowMyDate( Mydate: TMyDate): string;  // 注意每个声明都以分号结尾
begin
  Result := Mydate.year.ToString + '.' +
            Mydate.month.ToString + '.' +
            Mydate.day.ToString;
end;
```

7. 使用with语句可能导致隐藏的错误，谨慎使用

8. 




