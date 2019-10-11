# XshellToMobaXterm
## 原理
xsh文件本身就是ini 所以调用相关库解析就完事了  
Xshell是一个文件一个会话  
MobaXterm则是一行一个会话  
为了追求效率 尽快完成转换 我直接用拼接字符串的方式去做了。（虽然我知道这样子性能肯定不是最好的）

## 它可以做什么  
递归扫描并在命令行输出转换好的结果

## 它做不到什么
~~根据文件夹的层级,在MobaXterm的配置文件中重现级别~~ (目前没有好的转换思路)  
~~正确地显示图标~~ (我不知道图标ID)  
~~自动输出ini文件~~ (懒,也不是很会写)

## 如何使用?
为了保证转换稳定性,先用 `EncodingConvert.py` 转换一下编码 ,转换成UTF-8  
脚本需要 `Python3` 和 `ConfigParser` (所以pip方面你懂的)
以上工作完成以后 直接 
```bash
python main.py {你的Xshell Session文件夹,可以在CMD里拖进来}
```
由于输出默认打在终端里,嫌麻烦可以用重定向符号,比如
```bash
python main.py {你的Xshell Session文件夹,可以在CMD里拖进来} > list.txt
```
之后就可以把一大段东西放进MobaXterm配置文件里了  
或者在MobaXterm里随便创建一个会话,导出,用N++打开,黏贴进去也是可以的(最后别忘了导入回去)  

