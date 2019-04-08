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
  