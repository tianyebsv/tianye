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
cp 
```

