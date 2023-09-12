
[返回首页](README.md)     
**本站访问次数/Visitor Count:**

<a href="https://count.getloli.com/"><img src="https://count.getloli.com/get/@:2356360027"></a>

**请勿复制或者抄袭或者发表本文的部分或者全部内容**

# Linux基本指令  
<html>
    <body>
        <table align="center" border="1" id="t1" style="width:600px;height:200px"  >
            <tbody align="center" valign="center"  >
            <tr >
                <td colspan="4" style="color:red;font-size:17px;">windows和Linux/macOS操作目录</td>
            </tr>
            <tr style="font-size:17px;">
                <td>Windows </td>
                <td>Linux/macOS </td>
                <td>说明 </td>
                <td>注释 </td>
            </tr>  <tr>
                <td>cd </td>
                <td>cd </td>
                <td>切换目录 </td>
                <td> </td>
            </tr>  <tr>
                <td>cd </td>
                <td>pwd </td>
                <td>获取当前所在位置 </td>
                <td> </td>
            </tr>  <tr>
                <td>dir </td>
                <td>ls </td>
                <td>列出当前所在的文件列表 </td>
                <td> </td>
            </tr>  <tr>
                <td>mkdir </td>
                <td>mkdir </td>
                <td>创建新的目录（文件夹） </td>
                <td> </td>
            </tr>  <tr>
                <td>无 </td>
                <td>touch </td>
                <td>创建文件 </td>
                <td> </td>
            </tr>  <tr>
                <td>copy </td>
                <td>cp </td>
                <td>复制文件 </td>
                <td> </td>
            </tr>  <tr>
                <td>move </td>
                <td>mv </td>
                <td>移动文件 </td>
                <td> </td>
            </tr>  <tr>
                <td>del </td>
                <td>rm </td>
                <td>说明 </td>
                <td> </td>
            </tr>  <tr >
                <td>cls </td>
                <td>clear </td>
                <td>清除上面内容 </td>
                <td> </td>
            </tr> <tr>
                <td> </td>
                <td>  rpm -ivh  </td>
                <td>安装 </td>
                <td> </td>
            </tr> <tr>
                <td></td>
                <td>  su root </td>
                <td>切换root系统 </td>
                <td> 必须在Desktop目录下</td>
            </tr><tr>
                <td>  </td>
                <td> gedit </td>
                <td>打开文件 </td>
                <td> </td>
            </tr>  <tr>
                <td>  </td>
                <td> rpm -ivh  </td>
                <td>说明 </td>
                <td> </td>
            </tr>  
            </tbody>
        </table>
    </body>
</html>  

## g++编译原理
### 注释
用"#"
### 预处理
预处理：宏替换，注释消除，查找相关库文件等。(使用-E参数)
```c++
g++ -E xxx.cpp > xxx.i
```
- 只激活预处理，不会自动生成.i文件，如果需要可以通过>重定向生成xxx.i。

### 编译
将预处理后的文件转换成汇编语言，生成.s汇编文件。(使用-S参数)
```c++
g++ -S xxx.cpp
```
- cpp源文件直接经过预处理，编译生成.s汇编文件  

```c++
g++ -S xxx.i
```
- 将预处理生成的.i文件编译生成.s汇编文件

### 汇编
将汇编文件转换为目标文件(机器代码)，即.o文件。 (使用-c参数)
生成xxx.o文件:
```c++
g++ -c xxx.cpp // 实际执行了预处理，编译，汇编
g++ -c xxx.i   // 实际执行了编译，汇编
g++ -c xxx.s   // 实际执行了汇编
```  
- .o文件不可以文件名一样呦
### 链接  
链接相关目标文件或动静态库等，生成可执行文件(使用-o参数用于指定可执行文件名)
```c++
g++ hello.cpp // 默认生成a.out可执行文件，一步到位(执行了预处理，编译，汇编，链接)
g++ hello.cpp -o hello //生成可执行文件，指定文件名为hello。
g++ hello.o -o hello //基于hello.o目标文件生成可执行文件。
``` 
- 可执行文件的后缀名可以没有，换句话说，就是执行的时候一定要输入全名。
## 别急，剩下的我还没学会呢