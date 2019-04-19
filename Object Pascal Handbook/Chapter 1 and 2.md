1.Hello, world!
- writeln(str);//输出到console界面
- readln;//等待输入，是界面暂停  
- showMessage(str);//窗口显示消息

2. 注释
```
{第一种}
（*第二种*）
// 第三种

```
> 批注快捷键：选中要批注的所有行，Ctrl + /

3. 标识符identifier
- 只能以字母或_开头
- 可由字母、下划线、Unicode字符组成
- 每个首字母都大写pascal-casing，或者驼峰式camel-casing

4. pas是单元文件，dpr是项目文件

5. 换行sLineBreak
> 'Marco' + sLineBreak + 'Cantu'''

6. 变量和赋值
```
// 声明全局变量用=
var
  Value2: Integer = 10;
  Correct2: Boolean = True;

// 声明常数
const
  Thousand = 1000;
  Pi = 3.14;
  AuthorName = 'Marco Cantu';

// 指定常量存储类型
const
  ThousandAgain: Integer = 1000;

// 资源字符串常量
resourcestring
  strAuthorName = 'Marco';
```
> IntToStr() 整型转字符串函数

7. interface和implementation
> 在interface声明的全局变量整个程序都可见
> 在implementation声明的全局变量只在整个单元内可见

8. show过程的定义，这里为什么有个const？
```
-- 声明
procedure Show (const msg: string);

-- ctrl + shift + c 定义
procedure TForm1.Show(const msg: string);
begin
  Memo1.Lines.Add(msg);
end;
```

9. 使用字符型别的函数要
```
uses
  Character;
```

10. 自定义型别
```
// 可以在implementation里定义
type

  Tuppercase = 'A'..'Z';
  TMYColor = (Red, Yellow, Green, Cyan, Blue, Violet);  // 这是列举型别
  TColor = set of TMYColor;  // 集合型别

// 集合型别运算方法，如字体样式 + - Include Exclude
style := style + [fsBold];

Include(style, fsBold);
Exclude(style, fsItalic);
```

11. BoolToStr()
```
  Show (BoolToStr (3 < 30, True));
  Show (BoolToStr (12 = 10, True));
```

12. / 和 div
> / 可以用于实数或整数，但是结果一定是实数
> div用于整数，结果也是整数

13. 时间函数
> 时间类型：TDateTime
>  函数没参数，不需要带括号
> Now  //当前日期时间
> Date
> Time
> DateTimeToStr
> DateToStr
> TimeToStr

```
// 创建unit后会自动引入sysUtils，以便调用时间函数
uses
  System.SysUtils

// 时间函数的使用
var
  StartTime: TDateTime;
begin
  StartTime := Now;
  show(DateTimeToStr(StartTime));
  show(TimeToStr(StartTime));
  show(DateToStr(StartTime));
end;
```

14. Timer控件
```
// 在timer控件内编写对应的操作
procedure TForm1.Timer1Timer(Sender: TObject);
begin
  show(DateTimeToStr(Now));  // 操作
end;

// 启用或关闭Timer
procedure TForm1.Button2Click(Sender: TObject);
begin
  Timer1.Enabled := True;  // 关闭则是False
end;
```










