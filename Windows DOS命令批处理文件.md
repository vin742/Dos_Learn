##  Windows DOS命令/批处理文件

### 基本操作

批处理程序：Batch file programing是微软系统自带原生的开发语言，不需要任何环境就可以执行的脚本。

使用任何文本编辑器都可以编辑批处理程序

批处理程序可以使用一系列内置命令进行i自动化操作，例如：匹配规则是删除文件、新建文件、日志等，甚至可以批量创建计算机病毒

###### 几个基础的批处理文件

@echo off  关闭
Echo "hello world"
pause

###### 命令分类

内部命令：如ipconfig cls

外部命令：Java python



##### 算术运算

**运用set /a 运算符**

 例如：

@echo off
set /a var=90-23
Echo %var%
pause

**改变优先级使用()**

###### 重定向运算

> ">"数据存储到对应的结果位置，会覆盖原有内容，左边到右边
> echo "hello world" > a.txt
> ”>>“同上 单不会覆盖原有的内容，进行内容追加
> type a.txt  进行查看
> "<" "<<" 右边到左边

###### 多命令运算符

&&  具有短路，第一个命令错误不会执行第二个命令
||  短路，第一个命令成功执行，不执行第二个

###### 管道运算

windows使用后缀名进行区分，Linux没有

管道符号：”|“
dir | find ".txt"  查找目录下的txt后缀
netstat -an | find "ESTABLISHED"  找已经建立连接的端口

## 批处理基本命令

###### 命令格式：

命令 子命令 参数 操作 选项

命令帮助信息查看： /?  /help  获取详细的帮助信息

例如：

>>net    可以看到其命令语法
>>net /?
>>net user
>>net user /?
>>net user test test /add  添加用户 但会添加不成功
>>net user /help

###### 批处理文件参数传递

.bat文件接受参数使用%num

例如：

@echo off
echo %1  参数1输入
echo %2  参数2输入
net user %1 %2 /add
pause

###### 注释符

rem *******
rem Program for example

改变背景及前景颜色：color 0a

改变提示窗口显示的文字：title "hacker"

###### 时间相关命令

date /T  显示日期
time /T 显示分钟

###### 启动命令

start 用来启动
start /B dos.bat  启动但不创建一个新的窗口

###### 调用其他bat文件

call 直接输文件名来调用

例如：可以传递参数

![image-20241129232928736](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241129232928736.png)

![image-20241129232948682](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241129232948682.png)

![image-20241129233013599](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20241129233013599.png

###### 任务列表查看

tasklist  用于显示本地或者远程计算机上当前的进程列表

