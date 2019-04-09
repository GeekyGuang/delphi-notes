1. 
```
 Form1.Caption := '系统说明';
 memo1.Lines.LoadFromFile('D:\test.txt');  // LoadFromFile读取文件内容
                                           // SaveToFile写入文件
```

2. memo指定行显示内容
```
  Memo1.Lines.Strings[0] := '姓名： ' + edit1.Text;
  Memo1.Lines.Strings[1] := '生日： ' + MaskEdit1.Text;
  Memo1.Lines.Strings[2] := '电话： ' + MaskEdit2.Text;
  Memo1.Lines.Strings[3] := '住址： ' + edit2.Text;
```

3. 
```
  s := format('球的表面积是：%12.4f',[f]);  //格式化输出
  ShowMessage(s);
  ShowMessageFmt('球的体积是： %12.4f' + #13 + s, [v]);  // #13是换行
```
4. inputBox
```
  c := StrToFloat(InputBox('摄氏转华氏', '请输入摄氏温度：', '0')); // 标题，输入提示，默认值
  f := 32 + 9*c/5;
  label1.caption := format('摄氏%7.2f度 = 华氏%7.2f度',[c, f]);
  ```
5. 鸡兔同笼
```
var
  h, f, x, y: Integer;
  s: string;
begin
  h := StrToInt(InputBox('请输入', '鸡和兔的总头数','0'));
  s := Format('鸡和兔的总脚数(大于%d的偶数)', [2*h]);
  f := StrToInt(InputBox('请输入', s, '0'));
  x := (4 * h - f) div 2;
  y := (f - 2 * h) div 2;
  Label2.Caption := Format('设笼中鸡和兔的总头数为%d, 总脚数为%d.', [h, f]);
  Label3.Caption := Format('则笼中鸡有%d只，兔有%d只。', [x, y]);
end;
```

6. 
```
begin
  Edit1.CharCase := ecNormal;  // 大小写类型
  Edit1.SetFocus;              // 光标选中
  Edit1.selstart := Edit1.Tag;  //selstart是光标选中位置
end;

begin
  Edit1.Tag := Edit1.SelStart;  //tag存储当前焦点位置
end;
```

7. 清空输入的两种方法
```

  Edit1.Text := '';     // 清空

  Edit1.clear;    // 清空
  MaskEdit2.Clear;
  Memo1.Lines.Clear;

```

8. spinedit控件的使用
```

begin
  label3.Caption := '您的名字叫' + Edit1.Text + ';' + Chr(13) + Chr(10)
                    + '您' + spinedit1.text + '岁了！';
  // chr(13) + chr(10)换行

  SpinEdit1.Value := 0;  //设置spinedit的值
```
9. memo控件
```

  Memo1.Lines.Add(Edit1.text);       // 添加

  Memo1.Alignment := taLeftJustify;      // 左对齐

  Memo1.Alignment := taCenter;         // 居中

  Memo1.Alignment := taRightJustify;    // 右对齐


  Memo1.Lines.Clear;              // 清空
  Edit1.Clear;
```

10. 声明全局变量的位置
```
interface

uses
  Winapi.Windows, Winapi.Messages, System.SysUtils, System.Variants, System.Classes, Vcl.Graphics,
  Vcl.Controls, Vcl.Forms, Vcl.Dialogs, Vcl.StdCtrls, Vcl.ExtCtrls;

type
  TForm1 = class(TForm)
    Image1: TImage;
    Label1: TLabel;
    Button1: TButton;
    Button2: TButton;
    procedure Button1Click(Sender: TObject);
    procedure FormCreate(Sender: TObject);
    procedure Button2Click(Sender: TObject);
  private
    { Private declarations }
  public
    { Public declarations }
  end;

var
  Form1: TForm1;
  i : Integer = 1;     // 声明全局变量的位置
```

11. image控件
```
image1.picture.loadfromfile('D:\素材' + inttostr(i) + '.jpg');
```

12. button的禁用和启用
```
    button1.enabled := False;
    button2.enabled := True;
```

13. datetimepicker获取Date
```
label1.Caption := DateToStr(DateTimePicker1.date);
```

14. x平方： sqr(x)
```
  if x > 0 then y := Sqr(x) + 2 * x + 3
  else y := 2 - 4 * x;
```

15. Tedit密码显示，PasswordChar的 #0 改成 *

16. 嵌套if...else 
```
if then
  begin
  end //else前的end不能有分号
else
 begin
 end;
```

17. case 
```
case e1 of
   x1: 语句1；
   x2: begin
       ...
       end;
    .
    .
    .
   xn: 语句n;
   [else 可选;]
End; 
```

18. 设置字体属性
```
  label1.Font.Name
  label1.Font.Size
  label1.Font.Color
  label1.Font.Alignment
```
19. radiogroup组件，itemindex的值表示选中哪个

20. copy()函数
```
copy(m, 1, 3) //从m的字符串的第1位开始拷贝3位

copy(strmsg,1,Length(strmsg)-1);//去掉字符串末尾逗号
```

21. checkbox
```
if CheckBox1.Checked then strmsg := strmsg + CheckBox1.Caption + ',';
CheckBox1.Checked := False;
```

22. 三个scrollbar事件相同，只需要写其中一个事件，其他的在onchange关联这个事件
```
begin
  Panel1.Color := RGB(ScrollBar1.Position, ScrollBar2.Position, ScrollBar3.position);

  label1.caption := '红色值：' + inttostr(ScrollBar1.Position);
  label2.caption := '绿色值：' + inttostr(ScrollBar2.Position);
  label3.caption := '蓝色值：' + inttostr(ScrollBar3.Position);
end
```

23. 时间转字符串
```
DateToStr(DateTimePicker1.Date)
```

24. oncreate事件写了setfocus会提示"cannot focus a disabled or invisible windows"

25. 三种循环
```
  //求a到b的奇偶数和
  for i := a to b do
    begin
      if (i mod 2 = 0) then sum1 := sum1 + i  //如果是i是偶数则加到偶数上
      else sum2 := sum2 + i;            //如果i是奇数则加到奇数上
    end;

while e1 do begin ... end;

repeat ... until e1; //不需要begin end
```





