1.
- writeln(str);输出到console界面
- readln;等待输入，是界面暂停
- showMessage(str);窗口显示消息

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

4. pas是单元文件，dpr是项目文件

5. 换行sLineBreak
> 'Marco' + sLineBreak + 'Cantu'''

6. 变量和赋值
```
// 声明全局变量
var
  Value2: Integer = 10;
  Correct2: Boolean = True;

// 声明常数
const
  Thousand = 1000;
  Pi = 3.14;
  AuthorName = 'Marco Cantu';

// 指定存储类型
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

8. 

