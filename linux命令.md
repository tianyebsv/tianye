# Linux 初级指令

## ls介绍

ls 全称list。列出有关文件的信息（默认为当前目录）

#### ls 参数格式

```linux
ls [OPTION]... [FILE]...
```



## pwd介绍

打印当前工作目录的完整路径名。(print name of current/working directory)

#### pwd 参数格式

```linux
pwd [OPTION]...
```

## touch (change file timestamps)

#### touch 介绍

将每个文件的访问和修改时间更新为当前时间。除非提供-c或-h。否则将不存在的FILE参数创建为空。

#### touch参数格式

```
touch [OPTION]... [FILE]...
```



## cat介绍

将FILE或标准输入连接到标准输出。

#### cat参数格式

```
cat [OPTION]...[FILE]...
```

#### tac 命令与cat命令展示内容相反，不能带行号输出。



## mkdir--Make Directory

#### mkdir介绍

如果目录不存在，则创建目录。

#### mkdir 参数格式

```
mkdir [OPTION]...[DIRECTORY]...
```



## cd

#### cd介绍

切换当前目录到指定目录



## rm&rmdir -- Remove Directory

#### rm介绍

rm使用程序城市删除命令行上指定的非目录类型文件。如果文件的权限不允许写入，并且标准输入设备是终端，则会提示用户（在标准错误输出上）进行确认。

#### rm参数格式

```
rm [-dfird] file...
```

#### rm命令参数

-f , --force 忽略不存在的文件，从不给出提示。

-i, --interactive 进行交互式删除

-r, --recursive 指示rm将参数中列出的全部目录和子目录均递归地删除

-d, --dir 删除空目录



rmdir == rm  -d 删除空目录



## mv---Move

#### mv介绍

移动目录火文件到指定目录下，同时具有重命名的功能。

#### mv参数格式

```
mv [-f|-i|-n][-v] source target 
mv [-f|-i|-n][-v] source ... directory
```

#### mv命令参数

-b: 若需覆盖文件，则覆盖前先行备份。

-f: force强制的意思，如果目标文件已经存在，不会询问而直接覆盖；

-i：若目标文件已经存在，就会询问是否覆盖；

-n：不要覆盖现有文件；

-u：若目标文件已经存在，且source比较新，才会更新

#### mv常用参数示例

```
##修改文件名
$ touch tmp.cc

$ ls
tmp.cc

$ mv tmp.cc tmp.java

$ ls
tmp.java
#移动文件或者目录
$ pwd
/Users/localhost/test
#移动文件并重命名
$ mv /Users/localhost/logs/tmp.txt ./tmp.log 

$ ls /Users/localhost/logs/
discover-client metabase        tesla

$ ls ./
tmp.java tmp.log
#移动目录并重命名
$ mv /Users/localhost/logs/tesla  ./tesla.ba 

$ ls
tesla.ba tmp.java tmp.log
```



## cp---Copy

#### cp介绍

cp 将source_file的内容复制到target_file。

#### cp参数格式

```
cp [-R [-H |-L|-P]] [-fi|-n] [-apvX] source_file target_file
cp [-R [-H |-L|-P]] [-fi|-n] [-apvX] source_file ... target_directory
```



## echo

#### 介绍

常用来打印变量、文本内容



## head&tail

#### head介绍

此过滤器显示每个指定文件或标准输入（如果未指定文件）的前几行或字节。

如果省略count，则默认为10，如果指定多个文件，则每个文件的头均有字符串==>XXX<==组成，其中“XXX”为文件名。

#### head参数格式

```
head [-n count|-c bytes] [file ...]
```

#### head常用参数示例

-n 展示前n行

-c 展示前n个字符

#### tail介绍

与head完全相反，是从尾部开始展示文本，他的参数用法更多。

#### tail常用参数示例

-f 循环读取

-q 不显示处理信息

-v 显示详细的处理信息

-c <数目> 显示的字节数

-n <行数> 显示行数

--pid = PID  与-f合用，表示在进程ID，PID死掉之后结束

-q 从不输出给出文件名的首部

-s 与-f合用，镖师在每次反复的间隔休眠S秒



###### tail和head命令经常用来查看日志。



## more&less

#### more介绍

more命令类似cat，不过会以一页一页的形式显示，流式读取，支持翻页。

#### more参数格式

```
more [-dlfpscu] [-num] [+/pattern][+linenum][file...]
```

#### more命令参数

+n 从第n行开始显示

-n 定义屏幕大小为n行

+/pattern 在每个档案显示前搜寻该字串(pattern),然后从该字串前两行之后开始显示

-c 从顶部清屏，然后显示

-d 提示“Press space to continue,'q' to quit”,禁用响铃功能

-l 忽略Ctrl+l（换页）字符

-p 通过清除窗口而不是滚屏来对文件进行换页，与-c选项相似

-s 把连续的多个空行显示为一行

-u 把文件内容的下划线去掉

###### less与more类似，但使用less可以随意浏览文件，而more仅能向前移动，却不能向后移动，而且less在查看之前不会加载整个文件

#### 常用操作命令

- Enter 向下n行，需要定义。默认1行
- Ctrl+F 向下滚动一屏
- 空格键 向下滚动一屏
- Ctrl+B 返回上一屏
- = 输出当前行的行号
- ：f 输出文件名和当前行的行号
- V 调用vi编辑器
- !命令 调用Shell，并执行命令
- q 退出more



