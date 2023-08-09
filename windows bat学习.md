# windows bat学习

```
rem 给变量赋值
set a=3
set /a b=%a%-1
rem /a 表示进行数值运算
```



for循环

/l(L)表示for循环是数字序列

for /l %%i in (0,1,10) do (echo %%i)

在文件中写for循环时要用两个%，直接在bat窗口中写，只需要一个%


