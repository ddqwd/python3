
pdb 是一个模块。可以在代码插入。
通过
```python
import pdb; pdb.set_trace()
```
or
```python
breakpoint()

```

模块函数：
* pdb.run
* pdb.runeval
* pdb.runcall
* pdb.set_trace
* pdb.post_mortem
* pdb.pm


也可以通过命令行唤醒
```python3
python -m pdb myscript.py
```


# 调试器命令

输入空行重新执行上个命令，但是如果上个命令是list命令，那么下个11行会列举
调试器不能辨认的语法默认被认为是python句法，也可以通过前缀！显示指定。
调试器支持别名
多个命令可以输入在同一行， 用;; 隔开，
如果文件.pdbrc存在用户的主目录或者在当前目录， 默认被认为是一个UTF-8 格式的debug脚本。如果两个文件都存在， 那么主目录的文件首先被读取， 里面定义的别名可以被本地文件覆盖。

命令：
* h(help)
* w(here)
打印堆栈
* d(own) [count]
往下堆栈移动当前frame count行
* u(p) [count]
* b(reak) [([filename:]lineno | function ) [, condition]]
* tbreak [([filename:]lineno | function ) [, condition ]]
临时断点， 当再次命中时移除它。
* cl(ear) [filename:lineno | bpnumber ...] 
* disable [bpnumber ...]
* enable 
* ignore bpnumber [count]
* condition bpnumber [condition ]
* commands [bpnumber]
为某个断点制定一系列命令。
* s(tep) 
* n(ext)
* unt(il) [lineno]
* r(return)
直到函数返回
* c(ontine))
* j(ump) lineno
* l(ist) [first[, last]]
没有参数列举下面的11行
带有.参数， 列举周围的11行
带有两个参数， 列举范围内的行数
* ll | longlist
列举当前函数或frame的所有源代码
* a(rgs)
打印当前函数的参数和他们的值
* p expression
* pp expression
* whatis expression
打印表达式的类型
* source expression
获取表达式的源码并且显示他
* display [expression]
* undisplay [expression]
* interact 
* alias [ name [command]]
给执行命令别名， 传入参数位置通过%\* 指定
如果没有命令，显示当前name的命令
如果没有任何参数， 显示 所有的别名
别名可以内嵌，内部命令可以被外部覆盖

* ualias name
* ! statement
* run [args ...]
* restart [args ...]

* q(uit)
* debug code

* retval 
打印当前函数的上次返回值
