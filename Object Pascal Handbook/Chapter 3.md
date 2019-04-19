1. 如何使用范例代码
- 仔细阅读范例代码，看运行结果是否与预测的相同
- 随意改写和测试范例代码
- 自己编写类似的代码

2. IsChecked
```
  if CheckBox1.IsChecked then
    show('你选中了！')  // delphi中的字符串只能用单引号！
  else
    show('你什么都没选哦！');
```

3. If...else
```
var
  age: Integer;
begin
  age := StrToInt(Edit1.text);
  if age > 60 then
    show('你是老年人了！')
  else if age > 40 then     // 注意else前面不能有分号
       show ('你是中年人了！')
  else if age > 20 then
       show('你是青年人了！')
  else show('你还小，快快长大哦！');

end;
```

4. case
```
  if Edit1.Text.Length > 0 then
  begin
    aChar := Edit1.Text.Chars[0];

    case aChar of
      '+' : aText := 'Plus sign';
      '-' : aText := 'Minus sign';
      '*', '/': aText := 'Multiplication or division';
      '0'..'9': aText := 'Number';
      'a'..'z': aText := 'Lowercase character';
      'A'..'Z': aText := 'Uppercase character';
      #12032..#12255: aText := 'Kangxi Radical';
    else
      aText := 'Other character: ' + aChar;
    end;
```

