1. procedure和function的区别
> function会返回函数值

2. stack overflow堆栈溢出

3. procedure或function可以直接在implementation里定义(无需声明)
   如果还没来得及定义就要调用则可以提前声明，用forward
```
procedure DoubleHello; forward;
```

4. MessageDlg
```
if MessageDlg('Welcome to my Delphi application. Exit now?', 
mtConfirmation, [mbYes, mbNo], 0) = mrYes then
begin
  Close; 
end;
```

5. Method
> 方法：指属于特定类别的函数或程序
```
-- 这就是一个Method
procedure TForm1.Button1Click(Sender: TObject);
begin
  Hello;
end;
```

6. 引用参数var
```
procedure DoubleTheValue (var Value: Integer);  // 用var引用参数，实参的值会被修改
begin
  Value := Value * 2;
end;
```

7. 常数参数const
```
function DoubleTheValue2 (const Value: Integer): Integer;  // const常数参数，在子程序里不能被更改
begin
  Value := Value * 2;      // compiler error
  Result := Value;
end;
```

8. overload：函数名相同但是参数数量或类型或顺序不同的标志
```
procedure ShowMsg (str: string); overload;
begin
  Show ('Message: ' + str);
end;

procedure ShowMsg (FormatStr: string;
  Params: array of const); overload;
begin
  Show ('Message: ' + Format (FormatStr, Params));
end;

procedure ShowMsg (I: Integer; Str: string); overload;
begin
  ShowMsg (I.ToString + ' ' + Str);
end;
```

9. 预设参数
```
procedure NewMessage (Msg: string;
  Caption: string = 'Message';
  Separator: string = ': '); overload;
begin
  Show (Caption + Separator + Msg);
end;

// 调用，参数只能从最后一个往前省略
  NewMessage ('Something wrong here!');
  NewMessage ('Something wrong here!', 'Attention');
  NewMessage ('Hello', 'Message', '--');
```

10. 内嵌函数 inline
> {$INLINE OFF}
> {$INLINE ON}


