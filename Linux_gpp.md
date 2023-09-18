[返回首页](README.md)     
**本站访问次数/Visitor Count:**

<a href="https://count.getloli.com/"><img src="https://count.getloli.com/get/@:2356360027"></a>

**请勿复制或者抄袭或者发表本文的部分或者全部内容**  
# 嵌入式c++笔记

## g++编译原理

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

### g++与gcc的区别：  
首先应当说明的是，g++,gcc是俩个个不同的东西哦。他们俩可以理解为GCC的“子集”。他们的区别如下表：



<table align="center" border="1" id="t1" style="width:800px;height:300px"  >
  <tbody align="center" valign="center"  >
    <tr >
      <td colspan="5" style="color:red;font-size:17px;">g++，gcc，GCC的区别</td>
    </tr>
    <tr>
      <td>语言</td>
      <td>说明</td>
      <td>可编译语言</td>
      <td style="width:220px">编译区别</td>
      <td style="width:80px">链接区别</td>
    </tr>  <tr >
      <td>GCC</td>
      <td>编译器集合</td>
      <td>C、C++、JAVA等 </td>
      <td> </td>
      <td> </td>
    </tr>  <tr>
      <td>gcc </td>
      <td>C 编译器 </td>
      <td>C、C++ </td>
      <td>分别当作.c和.cpp编译</td>
      <td>gcc-lstdc++ </td>
    </tr>  <tr>
      <td>g++</td>
      <td>C++编译器 </td>
      <td>C、C++ </td>
      <td>统一当作.cpp文件编译，但g++ 会自动调用 gcc，故二者近似等价。</td>
      <td>g++ </td>
    </tr>  
    </tr>
  </tbody>
</table>


在编译阶段，g++会调用gcc，所以对于c++代码，两者是等价的，但是因为gcc命令不能自动和C++程序使用的库联接，所以通常用g++来完成链接，为了统一起见，干脆编译/链接统统用g++了，这就给人一种错觉，好像cpp程序只能用g++似的。

## 随笔


WiFi密码忘了，尝试登录中。。。
