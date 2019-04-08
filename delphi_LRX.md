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