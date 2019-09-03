[TOC]

# 目录

---

**面试重点总结**

`面试中可能会遇到的题目`



# 一、面试重点总结
	线程，进程，IO
	中间件本质
	关系数据库
	web界面开发，Django源码
	数据分析：工具应用熟练，数学理论熟悉
	函数封装
	面向对象
	难点：装饰器
	数据库原理，网络原理，操作系统原理，数据结构和算法(bat)
	求10万以内质数，判断某个数是否为质数，求斐波那契数列第101项或者前都少项（递归，生成器，循环），打印菱形

# 二、面试中可能会遇到的题目
## 1.动态语言的内存管理：
    什么是垃圾回收GC？面向对象编程在内存管理方面的优势和劣势？
    在程序运行时某一些对象的引用计数（sys.getrefcount(x)）可能为0，这些对象会被打上标记，说明为空，这些对象,所占用的碎片化内存，会被整理成连续的内存空间以便后续使用，这个过程叫做垃圾回收。但是垃圾回收时内存不能使用，所以需要在空闲时间整理内存，也不需要频繁整理，看实际需要。
    引用计数增加的方式：
        对象赋值给其他变量例如：x = [1,2] y = x  列表的引用计数加1
        函数调用 foo(x)  调用时某些变量引用计数会增加，调用完成，恢复原来的次数
    引用计数减少的方式：
        函数运行结束时，局部变量会被自动消除，引用计数减少
        变量指向给其他对象 x = 3 x = 4, 3的引用计数少一次
    另外， 字面常量的引用计数不容易判断
## 2.元编程
    可能是会拉开差距的面试题

## 3.计算机5大组成部分及各部分的功能

## 4.python语言的特点

## 5.python中的线性结构及特点

# 三、计算机基础知识

## 1.冯诺伊曼体系
+ 计算机5大部分：输入设备，输出设备，内存，cup（包括运算器，和控制器,  寄存器，缓存器）

+ cup：做所有运算，并通过控制器来控制内存，输入输出设备

+ 内存：作为cup和IO之间的桥梁，数据需要从IO设备加载到内存，才能被
  cup使用
  
+ 内存的特点：断电易失

+ 寄存器：用来暂时存放内存中的数据，速度和cup一样快

+ 多级缓存：用来存放内存中的数据，级数越高速度越慢，存储空间越大

+ 数据流向：IO设备到内存再到cup

+ 计算机中可以存数据的结构：IO设备，内存，cup中还有寄存器和缓存器

+ 个各结构的运算速度：cup >> 内存 >> IO设备

  ![](/Users/jw/Projects/python23/magedu/冯诺伊曼体系.png)

## 2.解释性语言和汇编语言
+ 解释性语言工作流程：源代码被解释器翻译成Bytecode,然后在虚拟机上运行（如pvm）,转换成机器语言

+ 编译语言工作原理：源代码被编译器，直接编译成机器语言
+ 非结构化：多个入口多个出口
+ 结构化：一个入口一个出口
+ Python是多范式的面向对象，结构化，函数式编程



# 四、python基础知识及练习
## 1.进制

    0xa 十六进制
    0b1 二进制
    0o7 八进制

+ 10 进制到 其他进制 用除法取余数
+ 其他进制转10进制 对应位置累乘
+ 2进制以1结尾在10进制中都是奇数
+ 2进制与16进制相互转换容易
+ 8bits(位) = 1byte（字节）= 1B    下载速度？？？？？？？？
+ 网络一般是bits，u盘一般是1byte

+ 需要记住的16进制到10进制的几个数：
        0x30 48
        0x31 49
        0x41 65
        0x61 97
        0x7F 127
  
+ 例子：
            
    1.  111 二进制
        F 十六进制      
        9 十进制

    2.  0xFF 十六进制 表示256个无符号位0～255  表示多少有符号位？？？？？？
        1111 1111 二进制
        2的8次幂减1 255

    3.  1000 00000 二进制
        2的7次幂 128 十进制
        0x80 十六进制

    4.  0x7F 十六进制
        0111 1111 二进制
        255-128=127 十进制

    5. int('1a', 16) = 16+10=26

## 2.按位运算
    &  位与
    |  位或
    ~  位非
    ^  位异或
+ 例子：
    1. 正数的源码反码和补码都相同，例如：12的源码,补码,反码都为 0000 1100在按位取反的过程中计算机自动求了补码，～12的**按位取反**（每一位都取反，包括首位） 为1111 0011，计算机认为这是个负数，所以又取了补码（负数的补码为，首位不变，其他位数取反码，并加1），即为1000 1100+1=1000 1101=-13。  

    2. -1 我们看到的格式为-0b1和1000 0001, 在计算机中的存在格式为1111 1110 + 1=1111 1111 =0xFF。所以0xFF 不仅表示正的255还表示-1 

    3. 0xFE = 0xFF-1=1111 1111 -1 = 1111 1110 = 0xFE

    4. 0xFE的补码即在计算机中的存在格式 1000 0001+1=1000 0010 =-2

    5.异或
    10^9 = 0000 1010 ^ 0000 1001 = 0000 0011=3
    10^-9 = 0000 1010 ^ (1000 1001自己看到的）1111 0110+1 =1111 1101 取补码 1000 0011=-3
    
    例子：?????????????????????????
    
    ```python 
    
    ```
    
    

## 3.逻辑运算
    逻辑元算
    and
    or
    not 

+ Or短路是指返回表达式第一个位置的为非零    1 or 0 or 6= 1+0+6 返回1
+ and短路是指 第一个位置为0    0 and 5 and 6 = 0\*5\*6 返回0
+ 与false等价的 4个空容器，空串，None，0
+ 运算符的优先顺序: 单目运算符> 双目算数运算符 >比较运算符 >逻辑运算符
+ 例子：
    1. (1 and 0) or (5 and 6) 返回6  ??????????????????????????
    2. 0 or 'abc' 返回‘abc’

## 4.分支及循环
+ 分支： if前面的条件被跳过，后面隐含前面条件
+ If 和elif加条件与冒号 ，else后面直接加冒号
+ 只有一个条件可以写成 if 3<2:print('111')

+ range(a)前包后不包，是惰性对象，range?查看帮助 ，一般作为计数器，当作为计数器时a大于0
+ for i in range(10, -1, -2)打印10，8，6，4，2，0
+ continue  跳过当前一次continue后面的循环，进入到下一次循环，如果当前循环是最后一次，则跳出循环

+ break终止当前for循环或者其他循环，continue终止本次循环进入下一次循环
+ 例子：
      
    1.  ``` python
        for i in range(100):
            print(i)
            if  i > 2:
                break
        else:
        		print('end')
        ```
    + 当如果已经进入循环，并且遇到了break,就认为循环不正常，不执行else(两个条件)，否则都执行else
    + 如果在一个函数中存在for   else 结构，而且for中有return语句，return语句执行后，else语句的内容也不执行

## 5.特殊符号
+ \n 换行
+ \r 换行
+ \r\n 回车换行
+ r R \ 加到字符串前面表示不转义
+ \t 四个空格
+ \  在转义前面再加一个反斜杠表示不转义
+ 在字符串最后加上\ 表示不换行
+ f 表示字符串前缀，例如f'{a}, {6}' = '100, 200'

## 6.python语言的特点
+ python是动态的强类型语言，动态语言的特点是不需要事先定义变量类型，
  可以在使用的同时被定义，赋值即定义，使用方便，但是也存在无法判断变量类型问题，遇到问题难以发现，在使用函数时也不知道该传什么类型的参数（但是可以通过类型注释来改善），bur强类型语言的特点是只有相同类型变量之间才可以操作  ，例如：python不能运算‘abc’+1, 但是在python中也存在隐式的类型转换，例如：1+0.5=1.5

  

## 7.数值类型

+ int 为长整型，无大小限制，但是受内存限制

+ bool 可以和整型直接运算

+ int 截取整数部分

+ // floored quotient 向下取整  （5颗星）

+ math.floor() 向下  math.ceil()向上   round 4舍6入 5取偶(不是math中的，是内建函数)

+ math.pi math.e math.sqrt()=2 ** 0.5 pow(2,3) math.pow(2,3) math.log2(4) math.log10(100)=2

+ min(range(5))=0 min([9,0])=0 min(3, 4, 5)=3 max用法相同, 时间复杂度为O（n）

  ```python
  # min(range()) TypeError
  # min([]) ValueError
  min([], default=0)
  ```

  

+ a = 2 , b = hex(100) 不能这么用，尽量不要写在一行

+ bin(100) = 0110 0100  hex(100) = 64 oct(100)=0o144

  ```python
  int(0o10) # 8
  int(0xf)  # 15
  int(0b10) # 2
  
  bin(2)  # 0b10
  bin(0xf) # 0b1111
  bin(0o10) # 0b1000
  
  hex(15) # 0xf
  hex(0xf) # 0xf
  hex(0o10) # ox8
  
  oct(8) # 0o10
  oct(0xf) #0o17
  oct(0b10) #0o2
  ```

  

+ type(12)返回类型  

+ isinstance('abc', (str, int, float))返回布尔

## 8. 容器

### (1). 列表

+ list 索引0-len(a)-1  -len到-1，构建list=[1,2] list=list(range(5)) list=list(可迭代对象)

  ​	list 方法：

  ​	alst.len() 时间复杂度O(1)

  ​	alst.append() O(1)

  ​	alst.extend([1,2]) O(1)

``` python
#alst.append() alst.extend() 都是原地修改 相extend()当于
alst = []
alst += [1]
```

  ​	alst.index(object, 开始索引，结束索引)  O(n) 两个索引范围前包后不包，列表只能通过索引查找

​       没有  find方法

  ​	alst.count()  O(n)

  ​	alst.insert(索引，object)  在索引前面插入，超出索引插在最前面或最后面 O(n)

  ​	alst + blst 生成新列表，开劈新空间   **注意**

  ​	alst*5 对当前列表里面的元素操作，例如：[[2,3]乘5]=[[2,3,2,3,2,3,2,3]]生成新列表，开辟新空间，**注意**

  ​	alst.sort(*, key=None, reverse=False) 只能接受2个keyword_only参数，没生成新的列表，原地排序，sort有时必须要用，但是少用。例子：

  ```python 
  alst=[1,2,'a']
  #在排序的过程中会转换成字符串，但不改变原来的结果
  alst.sort(key=str)
  #不可以用?，因为int('a', 16)
  alst.sort(key=int)
  
  ```

  alst.remove(object) 找不到会报错，会删除第一个找到的object，因为需要先找到再删除，而且需要挪位置，所以效率很低, O(n)

  alst.pop() 删除指定索引，只有一个参数

  alst.clear()  引用计数标记为0

  修改列表

  ```python
  a = [1,2,3]*2
  a = [1,2,3,1,2,3]
  a[1] = 31
  a = [1,31,3,1,2,3]
  
  # 相乘后a两个位置的元素具有相同地址（5颗星）
  a = [[1,2,3]]*2
  a = [[1,2,3], [1,2,3]]
  a[1][2] = 31
  a = [[1,2,31], [1,2,31]]
  
  #a两个位置元素具有不同地址
  a = [[1,2,3], [1,2,3]]
  a[1][2] = 31
  a = [[1,2,3], [1,2,31]]
  
  #a与b的值相等即 a==b,但是地址不同 ，shallow_copy之后id(a) != id(b), id(a[1])=id(b[1])
  a = [[1,2,3], [1,2,3]]
  b = a.copy()
  a[1][2] = 31
  a = [[1,2,3], [1,2,31]]
  b = [[1,2,3], [1,2,31]]
  
  #a与b的值相等及 a==b, deepcopy之后id(a) != id(b), id(a[1]) != id(b[1])
  a = [[1,2,3], [1,2,3]]
  b = copy.deepcopy()
  a[1][2] = 31
  a = [[1,2,3], [1,2,31]]
  b = [[1,2,3], [1,2,3]]
  
  
  ```

  ![浅拷贝图示](/Users/jw/Projects/python23/magedu/shallowcopy.png)

  

  ![]()

  in  O(n)不要经常用

  als.reverse() 通过对调实现的，一般不用，只需要倒着打印即可

  倒着打印字符串： ''.join((i for i in reversed('abc')))

   

+ 链表Linkedlist

+ 栈stack 后进先出，一端操作元素，底层一般用链表和数组实现，不在中间进行修改和删除，也不会遍历

+ 队列queue 先进先出, 从一端增加元素，另一端出元素，底层一般用链表实现，不在中间进行删除和修改，也不会遍历

+ 比较：列表查找很快，因为有索引，但是需要连续的内存空间，插入和删除很慢，两个方向都可以操作；链表因为没有索引，所以查找元素需要从头查找速度慢，但是插入和删除很快，两个方向都可以操作；栈一般用作处理后进后出的数据，一般不做插入删除和索引和计算长度的操作；队列一般用作处理先进先出的数据，一般不做插入删除和索引和计算长度的操作，栈和队列是基于列表和链表实现，以上4种都是顺序线性结构。

  

### (2). 元组

  新建元组，() (1,) (1,2)   tuple()  1,2

  ​	元组不可以修改：是指里面的值和地址不能修改，但是如果地址指向的是可变对象，那么这个可变对象可以修改。

  ​	修改元组

  ```python
  tup =(1, (2,3),[4,5,'a',(4,)])
  tup[0] = 31 #不可以修改
  tup[1][1] = 31 #不可以修改
  tup[2][1] = 31 #可以修改
  tup[2][3] = 31 #可以修改  （5颗星）
  tup[2][3][0] = #不可以修改
  
  tup = (1,)*3  #（5颗星）
  tup = (1, 1, 1)
  
  tup = ((1,),)*3
  tup = ((1), (1), (1))
  #tup不可以修改
  
  tup = ([1])*3
  tup = ([1], [1], [1])
  tup[1][0] = 100
  tup = ([100], [100], [100])
  
  tup.index(value, [start, [stop]])
  tup = (1,2,3,4,5,5,4,3)
  tup.index(3, 5) #从第5个索引之后找3的值
  
  tup.count(value)
  len(tup)
  
  () + (1,) 返回（1）这是生成新的元组
  	
  ```

  ### (3). 字符串

+ 字符串一旦定义不可以修改，是字面常量，在python3中字符串都是**Unicode**类型

+ 字符串是容器，可以遍历，而且有序，通过索引遍历比较快

+ 字符串格式化

  '{:星号>9.3%}'.format(1.732)  转换成百分数，并且**一共9位右对齐, 小数点后面留3位**，其余用星号填充\*

  '{:星号>9.3}'.format(1.732) **字符串一共占用9位，数字部分一共占3位。**

  '{:.2f}'.format(1.732) 小数点后保留2位

  ‘{:*>6.2f}'.format(1.732)

  '{:3.2f}'.format(1.732)  #宽度为3，但是不起作用

  '{:2}'.format(1.732)  #宽度为2但是不起作用

   '{:f}'.format(3**0.5)  #默认小数点后面保留6位

  octets = [192, 168, 0, 1] 四个位置分别对应四个数，16进制各占5位2位2位
  '{:5x}{:2X}{:02X}{:02X}'.format(*octets) 

  "int:{0:d} hex:{0:#x} oct:{0:#o} bin:{0:b}".format(8) 0代表4个位置都是8，0一定要写，#表示显示0x 或0b 或0o,d代表十进制

  '{:*^5}'.format(21) 共占5位并且中间对齐，空缺位置用星号填充

  + '{}乘{}={:<04}'.format(3, 7, 3*7) 共占4位，左对齐，空缺位置用0填充

  + '{}乘*{}={:0>4}'.format(3, 7, 3乘7) 共占4位，右对齐，空缺位置用0填充

    '{}乘*{}={:>04}'.format(3, 7, 3乘7) 两种写法等效

  + Point = namedtuple('Point', 'x,y') p = Point(4,5)  "{{{0.x},{0.y}}}".format(p) 显示效果‘{4, 5}’

    "{0.x},{0.y}".format(p) 显示效果‘4, 5'

+ s.isidentifier() 判断字符串是否为标识符（字母数字下划线）

+ 查

  + s.count('very', 4, 20)

  + s.index('very', 4, 20)  s.rindex('very', 4, 20)

  + s = "Hello"   s.find('l', -3, -1) 找到第一个L,并返回索引2, find找不到会返回-1，不会报错

    s.rfind('l',-3, -1)   找到第二个L,并返回索引3

+ 改

  + s.strip() 默认去除字符串两端所有空白字符（\r \n \r\n \t \f等）

    s.strip('\r\f\n\t   ')  也可以指定需要去除的字符串，取''或''的关系, 如果指定1个空格或者2个空格，都可以去除所有空格

    s.lstrip()

    s.rstrip()

    

  + s.replace(old, new, 替换次数，不指定全部替换)

  + s.title() #每个单词首字母大写

  + s.capitalize() #单词首字母大写

  + s.swapcase() #交换大小写

  + s = "I'm\tasu\rper\r\nstu\nd\\fent\f."  s.partition('I')   #返回3元组，必须指定一个参数

    s.partition('空格')   #若字符串中没有空格，则最后用两个空格填充 ，partition中的参数不能是

    空字符串

  + s.splitlines()  #不能指定参数，行分隔符默认是\r\n \n \r \f 等，不包含\t制表符

    s.split() 默认拆分空白字符

    s.split('\n',maxsplit=1) 可以指定拆分次数

    s.split('I', -1)  s.rsplit('I', -1) -1代表所有的都拆分，两个结果一样

+ 增

  + "".join(["1",'2','3'])  join(可迭代对象)，并且对象本身都是字符串，返回新的字符串

  ​         也返回新的字符串

  ​		",".join(tuple(map(str, range(5)))) 需要将数字转换成字符串

  ​		

  + ‘+’ 相加的两个对象必须是字符串，并且返回新的字符串

+ 防止字符串转义 R r \

### (4). bytes



+ python3中新增加了 bytes 和bytearray

+ bytes是不可变字节，bytearray是可变字节数组

+ 一个**字节**有8位，表示0～255，共256种可能

+ x = 'abc' x是**字符**组成的有序序列，x是一个字符串，x.encode() 将字符串转换成2进制字节，x.decode()将二进制转换成字符串。

  x.encode()  = b'abc'   = b'\0x61\0x62\0x63'  =bytes('abc', 'ascii' )  第二个参数一定需要传

  ‘\x09’  回车对应‘\t’

  '\x13'    表中对应去找

  ‘\x0d\x0a’  '\r\n'       'a'.encode()  0x61

  '1'

  '\x01' 

  '\x0d0a'  '\r0a'

  + 构建bytes的方法

    bytes(range(97, 100)) 返回b'abc'(给开发人员看的) , 在计算机中存的是b'\0x61\0x62\0x63'

    bytes([97, 98, 99])   =  bytes(range(97, 100))    =   bytes('abc', 'utf-8')  =   bytes('abc', 'ascii')

    =bytes(b'abc')    =   bytes.fromhex('61 62 63')

    都返回b 'abc'(给开发人员看的) , 在计算机中存的是b'\0x61\0x62\0x63'

    bytes() 返回b''

    bytes(3) 返回b'\x00\x00\x00'

    bytes() + bytes(b'abc')  返回 b'abc'

    bytes(b'123') + bytes(b'abc')  返回 b'123abc'

  + bytes的返回值

    b'\tabc'  返回 b'\tabc'

    b'9abc'  返回 b'9abc'

    b'abc'[0]  返回10进制的97

  + 十六进制加法

    0x30 -1 = 0x2f  在计算机中的表示hex(0x30 -1)  返回字符串'0x2f'

    0x7f + 1 = 0x80  在计算机中的表示hex(0x7f + 1)  返回字符串'0x80'

    hex(127) 十进制的127转换成16进制，可以用一个字节表示（因为1个字节可以表示0～127）， 但是‘127’需要3个字节来表示，前面的几种编码都兼容了ASCII

  

+ 几种编码方式：unicode 是python 内部使用的字节编码 ，中文是2个字节一共16位，表示65536种方式，GBK编码中中文也是两个字节，utf-8中文大多数是3个字节表示（多字节编码一般用在网络编程中），ASCII中不能表示中文，编码范围是0-255
  
+ x = '中文'  y = x.encode() 默认是utf-8编码，y.decode()
  
+ 字符串与编码相关，在字节的世界只有数字

+ ASCII码表

  ![](/Users/jw/Projects/python23/magedu/ascii.png) 

+ 方法

  + b'abca'.replace(b'a',  b'123', 次数)

  + 'abc'.encode()  返回b'123'，如果在结果.hex(), 则返回'616263'

    'abc'.encode().hex()  =  bytes(range(97, 100)).hex()  = b'abc'.hex()

    与b'616263'.hex() 不同？？？？

  

### (5). bytearray

+ 构建bytearray

  bytearray(range(97, 100))  =   bytearray('abc', 'utf-8')    =   bytes(bytearray(b'abc'))  都返回b'abc'

  bytes(bytearray)  bytearray(bytes). 两者相互转换

+ 方法

  m = bytearray()  

  bytearray(b'abc') + bytearray(b'123') 返回 bytearray(b'abc123')

  bytearray(b'') + bytearray(b'123') 返回 bytearray(b'123')

  **bytearray后面只能添加数字 16进制或者10进制**

  m.append(0x31)  返回bytearray(b'1')

  m.extend(range(65, 67)) 返回bytearray(b'AB')

  m.strip()  去掉两侧空格，有返回值，不改变原来的m

  其他方法：m*2  pop remove  clear   等等

+ 16进制表示与字符串中的16进制表示

  0x31   回车返回49

  ‘\x31’.encode() 返回b'1'

  '\0x31'.encode() 返回b'\x00x31'    ？？？？

  

### (6). 字节序

+ 大端模式与小端模式

  

### (7). 线性结构切片

+ x[1:-1] 去头去尾

+ 索引切片可以超过上界和下界

+ x[-1, -5, -1] [start, stop-1]=[start, stop)

+ x[1: : -3]  1:空格，切片控制方向向左

+ x[-10: : -3]   同样的道理

+ y = x[:] = x[::]  与浅拷贝相同   y = x 表示引用计数加1

+ == 对于内建数据结构表示内容相同，但是对于自定义结构可能退化成表示内存地址相同

+ 通过索引更新list  

  将原列表区间替换 ，左侧是可变类型，右侧是可迭代对象

  n[1:3] = (5, 0)

  n[1:3] = [10, 11, 12]


### (8). set

+ set ，dictionary 都是哈希表，set不能修改，也不能根据索引查找

+ collection指定容器和集合类型，set指定集合

+ is 判断地址是否相同（也包括内容），== 只判断内容 相同

+ set 是可变的，不重复，无序的容器

+ 定义集合：空集合set(),   有元素的集合set('abc')  = set(['a', 'b', 'c']), set（可哈希对象），任何层次又不能出现

  [] bytearray set dict等。

+ set（）按内容相等去重复

+ 增 s1.add() 加一个元素，无append

  ​      s1.update(*多个set)，原地修改s1

  删 s1.remove('a')  找不到会报keyerror

  ​     s1.discard('a') 找不到也不会报错, 返回None，只有一个参数，没有缺省参数

  ​     s1.pop()  随机删除一个元素并返回, 如果是空集合则返回keyerror

  ​     s1.clear()

+ 判断一个元素在不在集合中用in, 速度很快O（1）

+ &交集 |并集 -差集  A^B = (A-B) U (B-A) ，对称差集， A^=B,表示直接修改A，不加等号表示生成新的

+ 可哈希的对象：

  None  字面常量 布尔值 tuple bytes 字符串

+ 散列：一个微小的变化引起结果巨大的变化

+ 幂等性：一个可哈希对象，运行几次哈希值都相同

+ 哈希冲突：2个不同的哈希对象，对应相同的哈希值

+ 整数的哈希值：数%很大的数 再通过某些映射成很大的   哈希值, 哈希值再对应内存中的地址

### (9). mapping

+ 字典的特点：无序，可变，key不重复可哈希

+ Python3.6之后有一个OrderDict，可以记录录入顺序，但是不同排序。

+ 构建空字典：{}  dict()

+ 构建字典的几种方式：

  d = dict(a=1,  b=2)  **注意a,b不能是字符串**

  d = dict((1,2), ['a', 4],  a=4) 可以修改a, 无a则新建，2元组结构第一个数需要可哈希, 

  **注意a ,b 需要的字符串 **

  d2 = dict(d,  a=23). 可以修改a, 无a则新建

  d = dict.fromkeys('abc',  0) 0为缺省值，不给则默认生成None

  d3 = d.setdefault('a', 1000)  无a则重新生成，有a则返回对应的value

  d.update(*键值对)

+ 增

  d['a'] = 100   

+ 删

  **注意：没有remove 方法**

  d.pop('一定要有键'，如果找到键，返回要删除的键对应的值，如果没找到会keyerror，也可以填缺省值，找不到返回缺省值)

  d.popitem() 没有参数随机删除键值对，原地修改，返回删除的键值对

  def d['键']    删除原字典中的键值对，同时被删除的value，对应的值计数减1，这也是删除的本质，即

  删除标识符，并且标识符对应的对象引用计数减1，但是对象是否被引用计数清0，取决于在其他地方使用使用了该对象

  d.clear()

+ 改

  d['a'] = 100 如果a存在于字典中，则a的值被修改为100

  d.setdefault('a',  100)  如果a存在于字典中，则返回‘a’对应的value，如果不存在，则将键值对（‘a’ : 100)加入到字典中，并且返回新加入的value100，如果不给定100，则默认值是None。

  d2.update({'a': 1, 'c':2},   a = 30,  b = []) a会被更新成30，b会新加入到d2中。

+ 查

  d['a']

  d.get('a', 缺省) 如果缺省值不填写，找不到a时返回None,  如果找不到a返回对应的value

  d.setdefault('a', 缺省)  如果a存在则返回对应的value。与get不同的是，setdefault有一个修改的过程

+ 遍历有3种方法

  在for 循环中有dictionary view 对象控制d.keys() d.values() d.items()   的长度不可以改变，但是值可以修改，

  d.keys()生成类似set对象，其他两种方法不可，因为里面的值不一定哈希，所以查找values里面的值时间复杂度很高。在while循环中，字典长度可以改变。

  怎么删除呢？ 可以先放到列表里再删除

  d.keys() d.items()  都可以进行集合之间的运算
  
  判断一个对象是否可哈希用hash()
  

### (10). 16进制、字节等类型转换

![](/Users/jw/Projects/python23/magedu/python各个类型转换.png)





### (11). 解析式与迭代器

字典，集合，列表等的解析式，一般用来构建数据，如果if else比较多，不适合用推导式

生成器不可以使用len（）函数，因为不确定里面有多少个元素。

#### 11.1 列表推导式（解析式）

a = [表达式   for i  in range(10) if i %2 == 0 or i % 3 == 0]

a =  [表达式   for i  in range(10) if i %2 == 0 and i % 3 == 0]

a =  [表达式   for i  in range(10) if i %2 == 0  if  i % 3 == 0]

a = [(i, j)  for i  in range(3)  for j in 'abc']

2与3的结果一样，都是同时是被2，3整除的数  两个if或者for相当于两次右斜,  表达式可以是函数等多种形式

[(i,j)  for i in range(7)  if i >4 for j in range(20, 25) if j >23]   都返回两个结果，但是第一种方法会快一点儿

[(i,j)  for i in range(7)    for j in range(20, 25) if j >23  if i >4]

#### 11.2 字典和集合推导式

字典与集合的区别是前面表达式有没有冒号，**推到式前面的表达式一定需要有返回值**，例如：print（）[].append() 都不能作为推到式前面的表达式

{i : str(j)  for i in 'abc'   for j  in range(3)}   因为字典的键不能重复，所以最后只生成3个字典元素

{(i str(j))  for i in 'abc'   for j  in range(3)}  包含生成的6个元祖的集合

{{i : str(j)}  for i in 'abc'   for j  in range(3)}  集合中的元素必须可哈希

{[i : str(j) ] for i in 'abc'   for j  in range(3)} 

#### 11.3 生成器迭代器总结

将列表推导式的方括号改成圆括号就变成生成器，生成器里面的值可以通过的for循环，next（）方法，list（），set（）方法取出，但是for循环可以取出生成器里面的所有元素，next()方法每次只能取出一个，当取出最后一个元素时，如果再调用next（）方法会报错，不过可以通过添加缺省值的方式返回，生成器只能用一次，如果再次需要，只能重新构造。生成器与迭代器和迭代对象有一定的差别，生成器包含于迭代器，迭代器包含于迭代对象。

例如：range()函数是可迭代对象，但不是迭代器，zip()函数是迭代器，但不是生成器，如果想构造迭代器，只需要在可迭代对象外面加上iter()函数即可。

#### 11.4 列表表达式与生成器的比较

列表表达式一次生成全部对象，返回新的列表，生成器是返回生成器对象，这是个惰性对象，驱动一次返回一个元素，列表表达式因为一次性生成全部元素，所以从单次返回值来看，很占内存空间，生成器表达式更节约空间，如果生成器里面没有元素几乎不占内存空间，从总的空间来看，列表表达式与生成器表达式所占用的空间相近。生成器表达式的计算时间短，列表解析式时间长。

### 11.5 生成器函数





## 9.常用的模块

+ random模块

  random.choice(squence)

  random.shuffle(squence)

  random.randint(1, 3) #左右全包

  random.randrange(1, 3) # 左包又不包

  random.sample(squence, k=3) #只能抽取不同地址的元素，k表示采样个数，random.sample([2,2], k=2) = [2,2]

+ collections模块

  + namedtuple ：Point = namedtuple('classname', 'x   y') 第二个参数也可以是'x,y'    ['x', 'y']   ('x', 'y')

  point = Point(5, 4) 一旦定义不可以修改，若point = Point([5], [4]) ,则可以修改point.x[0] = 13, 可以通过两种方式取出里面的值point.x point[0] point.y point[1]

  + defaultdict(函数可以是str, int, list, 也可以是高阶函数)
  + OrderedDict 可以记录数据录入顺序

+ datetime

  datetime.datetime.now()= datetime.datetime.today()   datetime.datetime.utnow()   now会多出8小时

  d1.timestamp()  从1970.1.1到目前的时间戳，是一个具体数值，但不是时间对象，单位是s, 精确到小数点后

  6位，到us

  + 创建时间对象的2种方法：

    datetime.datetime(按格式填写)

    datetime.datetime.fromtimestamp(时间戳)

  + 可以取出d1.date  d1.month  d1.isoweekday()   d1.replace(month=12 d1.isocalendar() 等等

  + 思考：已知现在的时间求2年前的时间？

  + 格式化时间：

    datetime.strptime('20180612 12:23:45',   '%Y/%m%d   %H:%M:%S')

    '{:%Y/%m/%d   %H:%M:%S }'.format(d1)

  + datetime.timedelta

    datetime对象  1  timedelta  2

    1 - 1 = 2

    1 + 1 = 错误

    1 + 2 = 1

    datetime.timedelta(day=5) 参数可以选

+ time  time.sleep(5) 阻塞当前线程10秒

## 10.内建函数

+ divmod(10, 3)  同时返回商和模（余数）

+ chr(20013), chr(97) 生成结果为字符，传入的参数需要是unicode编码

+ ord('中'), ord('a')  生成的结果为unicode编码

+ sorted( [1, 2, 3, 'a'], reverse = True, key=str)   内部使用高阶函数，效率高，转换时需要将元素转换成字符串

  先比较，最后但是不改变最后元素的类型

  可以排序字典：sorted({'b':1,  'a':2})    也可排序集合sorted({'b',  'a'})  ，字典和集合虽然无序但是可以给其排序

+ reversed（序列）或者reversed（range(10)） 可传入迭代器，reversed（）函数使用需要的两个条件，一是需要序列，二是需要知道长度。例如：reversed((0,1,2))  生成一个新的包含元组的迭代器，reversed（g），里面不能放生成器或者迭代器，因为不知道长度。

  **字符串反转**

  "".join((i for i in reversed('abc')))  效率高

  类似于：

  str1 = ''

  for i  in range(len('abc')):

  ​	str1  +=  'abc'[-(i+1)]	

+ zip(), 传入两个可迭代对象，取长度小的一个

  dict（zip(d1.keys(), d1.values())）给dict传入键值对

+ enumerate（）传入可迭代对象

+ iter()  生成迭代器

+ callable（函数名字不加括号），判断函数是否可以调用

## 11. 函数

### (1). 函数定义：

+ 函数名字不能和关键字重复，如果和内建函数重复则会覆盖原函数，名字只能由数字字母下划线组成，不能以数字开头，名字是一个标识符。*在函数定义时，表示可变位置参数，在函数调用时表示解构。

+ 参数列表，参数是形式上的参数，简称形参。

  + 形参包括：普通参数（位置参数，关键字参数），可变位置参数，可变关键字参数，keyword_only参数，共5种

  + 函数调用时只能传位置参数和关键字参数，即实参

  + 函数定义时，可以同时存在着几种参数

  + 位置参数与关键字参数同时使用：

    例如：

    def   add(a, b=5):

    ​	print(a + b)

    不可以这么使用：def add(a=4,  b) 或者add(4, a=5) (a被赋值了两次)也不能这么定义，**位置参数需要在关键字参数之前**

    可以这么使用 add(4), 为缺省参数

  + 可变位置参数：z以**元组的方式传入**，不可以修改，因为本例为求和，所以如果传人range(10), 或者[1,2,3,], 传入的是这种样式（range(10),）([1, 2, 3], ),不可相加。调用时不能传关键字参数，只能传位置参数。

    例如：def sum(*z):

    ​				s = 0

    ​				for i in z:

    ​					s += z	

  + 可变关键字参数：kwargs以字典的方式传入，可以传入test(a = 1, b=2), 如果写成这种样式test(kwargs = {'a': 1, 'b': 2}), kwargs将作为单独的key, {'a': 1, 'b': 2}将作为value,一般不这么用

    调用时只能使用关键字参数

    def  test(**kwargs):

    ​	print(kwargs)

  + 可变位置参数和可变关键字参数个数范围都是0～n

  + keyword_only参数：

    ‘*’，后面的位置参数，需要通过关键字参数传递，如果有多个keyword_only参数, 参数的位置可以不按位置参数和关键字参数的顺序。‘**’kwargs后面不可以接keyword_only参数。

    keyword_only的使用场景：def fn(x, y, *, m)想要keyword_only, 但是不想要星m, def fn(x, y, *m)

  + 5大参数总结：

    def fn(x, y, z=100, *args, n, m=0, o, **kargs)

    (1). n, m, o只能通过关键字参数传入

    (2).  如果传入5个参数，x,  y, z会先占用3个，z虽然是关键字参数但是也会占一个

    (3).  x, y, z可以通过位置传也可以通过关键字传，但是关键字参数必须在位置参数之后。

+ ：后面需要加语句块，注释不算语句块

+ 不加return返回None == return None==return，函数只能返回一个值，一个数值或一个元组等容器

+ 在函数中，for  循环后面如果有return，并且执行了，则外面的else，不执行

  

### (2). 函数调用：

+ add()  后面需要加（），里面的参数为实参

+ print（add）只打印表示标识符，标识符指向函数，并且打印出地址。

+ 函数执行流程：

  ![](/Users/jw/Projects/python23/magedu/函数执行流程.png)
  
+ 执行流程栈解释：

  ![](/Users/jw/Projects/python23/magedu/栈_函数执行流程.png)



### (3). 函数解构：



```python
def add(x, y):
	print(x + y)
 
add(*{7, 8})
add(*{'a':7, 'b':8})  #打印字符串‘ab',只取出keys,并且满足OrderDict
add(**{'x':7, 'y':8})  #里面只能keys只能是x和y,不能是a和b, 相当于传入了add(x=7, y=8)
add(*{'x':7, 'y':8}.values()) #打印15
```

```python
def add(x, y, *z):
  print(x, y, z)
  
add(*[1, 2, 3, 4, 5])  #x 1  y 2  z是一个元组（3，4，5）
add(*range(6)) #z是一个元组（2，3，4，5）
```



### (4). 函数作用阈

+ 函数或者类内部的区域称为局部或者本地作用域，内部变量称为局部变量，局部变量外部不可见

+ 函数或者类外部的区域称为全局作用域，外部变量称为全局变量，全局变量内部可见。

+ 作用域总结：

  

+ 每个函数的函数都用自己单独的作用域，变量不能共用，但是对于嵌套函数，内部函数可以使用外部函数的变量

  例子：inner，先打印‘a’, 97    outer,打印‘A’，65，因为外面的o看不到里面的小o,  所以还保持原来的65

  ```python
  # exmple1
  def outer():
    o = 65
    def inner():
      o = 97
      print('inner:', chr(o), o)
    inner()
    print('outer:', chr(o), o)
    
    
  # inner, 'a', 97
  # outer, 'A', 65
  ```

  ```python
  # exmple2
  def outer():
    o = 65
    def inner():
      global o
      o = 97
      print('inner:', chr(o), o)
    inner()
    print('outer:', chr(o), o)
  
  # inner, 'a', 97
  # outer, 'a', 97
  ```

  + global语句的另一个例子：

    没有x = 10, 会报错

    ```python
  def foo():
        global x
        x = 10  # 相当于在全局作用域中定义一个x = 10
        x += 1  # 成立的条件1为在局部域中定义x = 10,
                # 或者条件2为在全局域中找到x = 10
                # 本例中为条件2    
        print(x)
  foo()
    print(x) # 11 11
    ```
  
+ global语句总结：
  
    尽量不要使用，global, 如果函数需要参数可以通过形参的方式传递，通过实参赋值，但是如果使用了global，函数里面的参数就会到外面找值，同时，也可以在函数里面修改，这样就不清楚变量最终被改成什么样子，会照成全局变量污染。
    
+ nonlocal语句：

    在内部函数使用 nonlocal（非全局，只能在函数中的内部函数使用），即使在内部
    使用了c+=1,也可以在外面找到c

+ global与nonlocal语句的比较：

    这两条语句一般用在，内部作用域想要修改外部作用域的变量时使用，但是一般不用global，因为可能会引起全局变量的污染，在局部作用域中对变量使用global，则在此局部作用域中该变量不会被定义，在上级的某一局部作用域中也不会被定义，而是在全局作用域中被定义，如果在局部作用域中变量前面加上nonlocal,    则此变量不会在该局部作用域中被定义，也不会在全局作用域中被定义，而是在上级的某一局部作用域中被定义。

+ 变量名解析原则：

  总结：外层变量对内层可见，内层变量对外层不可见，就近原则

  ![](/Users/jw/Projects/python23/magedu/变量名解析原则.png)

+ 默认值的作用域

    函数中的型参的作用域都是局部作用域，python中的函数都有默认值，默认值都放在函数对象的属性中，例如：foo.\_\_name\_\_   foo.\_\_defaults\_\_(一般放简单参数)        foo.\_\_kwdefaults\_\_ （一般放可变和keyword_only参数）

    ```python
    def a(x=[]):
        x = x + [1]
        return x
      
      a.__defaults__, a(), a(), a.__defaults__
    #([],), [1], [1], ([],)
    ```

    ```python
    def a(x=[]):
        x = x + [1]
        x.append(1)
        return x
      a.__defaults__, a(), a(), a.__defaults__
      # ([],), [1, 1], [1, 1], ([],)
    ```

    ```python
    def a(x=[]):
        x.append(1)
        x = x + [1]    
        return x
     a.__defaults__, a(), a(), a.__defaults__
    # ([],), [1, 1], [1, 1, 1], ([1, 1],)
    ```

    ```python
    def a(x=[]):
        x += [1] # 相当于x.extend([1])就地修改。对于可变类型，+=不同于x = x + ['z']
        # 对于不可变类型 += 等于同于 x = x + 'z'
        return x
      a.__defaults__, a(), a(), a.__defaults__
      # ([],), [1], [1, 1], ([1, 1],)
    ```

    ```python
def foo(x=[], *, b=2):
        print('x_id:' ,id(x), 'b_id:', id(b))
    x += [1]   
        return x
    print('foo_id:', id(foo), 'defaults_id:', foo.__defaults__, id(foo.__defaults__), 'kwdefaultid:', foo.__kwdefaults__, id(foo.__kwdefaults__))
    foo()
    print('foo_id:', id(foo), 'defaults_id:', foo.__defaults__, id(foo.__defaults__), 'kwdefaultid:', foo.__kwdefaults__, id(foo.__kwdefaults__))
    foo() #第二次调用x的地址没有变
    print('foo_id:', id(foo), 'defaults_id:', foo.__defaults__, id(foo.__defaults__), 'kwdefaultid:', foo.__kwdefaults__, id(foo.__kwdefaults__))
    foo(x=[]) #第三次调用x的地址变了
    print('foo_id:', id(foo), 'defaults_id:', foo.__defaults__, id(foo.__defaults__), 'kwdefaultid:', foo.__kwdefaults__, id(foo.__kwdefaults__))
    
    # 输出（3次调用函数的地址没有变，只有第3次调用时x_id变了）
    
    foo_id: 4584989560 defaults_id: ([],) 4585050352 kwdefaultid: {'b': 2} 4585835328
    x_id: 4584614472 b_id: 4544013776
    foo_id: 4584989560 defaults_id: ([1],) 4585050352 kwdefaultid: {'b': 2} 4585835328
    x_id: 4584614472 b_id: 4544013776
    foo_id: 4584989560 defaults_id: ([1, 1],) 4585050352 kwdefaultid: {'b': 2} 4585835328
    x_id: 4585946632 b_id: 4544013776
    foo_id: 4584989560 defaults_id: ([1, 1],) 4585050352 kwdefaultid: {'b': 2} 4585835328
    ```
    
    ```python
    # 简单参数例子：
    def foo(xyz, m=123, n='abc'):
        print('xyz_id:', id(xyz))
        m = 456
        n = 'def'
    print(foo.__defaults__)
    foo('python')
    print(foo.__defaults__)
    foo('py')
    print(foo.__defaults__)
    
    # 输出
    # xyz_id 变了，defaults没变
    (123, 'abc')
    xyz_id: 4546904840
    (123, 'abc')
    xyz_id: 4545577512
    (123, 'abc')
    
    ```
    
    ```python
    # 引用参数的另一个例子：
    def foo(xyz, m=123, *, n='abc', t=[1,2]):
        print('xyz_id:', id(xyz))
        t.append(3)
        m = 456
        n = 'def'
    print(foo.__defaults__, foo.__kwdefaults__)
    foo('python')
    print(foo.__defaults__, foo.__kwdefaults__)
    foo('py')
    print(foo.__defaults__, foo.__kwdefaults__)
    
    # 输出
    # kwdefaults参数被存在字典中，改变了 
    
    (123,) {'n': 'abc', 't': [1, 2]}
    xyz_id: 4546904840
    (123,) {'n': 'abc', 't': [1, 2, 3]}
    xyz_id: 4545577512
    (123,) {'n': 'abc', 't': [1, 2, 3, 3]}
    ```
    
+ 函数销毁：
  
  ```python
  del  函数名
  ```
  
    
  
    
  
    
  
###  (5). 闭包(5星)

 + 自由变量：为定义在本地作用域中的变量。定义在本层函数外，其他函数内的变量
  + 闭包：内层函数引用到了外层函数的自由变量，就形成了闭包

```python
"""
闭包的例子
"""
def counter():
    c = [0]
    def inc():
        c[0] += 1 #c没有被重新定义，而是取出里面的元素
        return c[0]
    return inc

#foo = counter()() 另一种获得值的方式
# counter()返回标识符inc,inc标识符指向一个函数对象
# 所以foo与inc一样也指向函数对象
foo = counter()  # 内部函数用到了外部函数的变量，如果内部函数没用消亡，则外部变量没有消亡
									# 调用inc,但是可以找到外部函数定义的c = [0]
print(foo(), foo()) #1 2
c = 100
# 引用的是counter下面的c, 即自由变量, 而不是100
print(foo()) # 3
```



```python
'''
使用nonlocal实现闭包的例子
'''
def counter():
    count = 0
    def inc():
        nonlocal count
        count += 1  # count在局部作用域中被重新定义，
                    # 如果不加nonlocal，则会报错，nonlocal关键字的作用是，
                    # 声明变量count不在本地作用域定义，而是在外部作用域定义，
                    # 可以是几层函数外的作用域，但一定需要在函数内部
        return count
    return inc
foo = counter()
print(foo(), foo())
```

```python
"""
使用全局变量实现上面的例子，方法1
"""
# 使用global只是声明 count，还需要到函数外面找count
# 如果不在函数在最外面count=0, 会报NameError错误
count = 0 
def counter():
    count = 0
    def inc():
        global count 
        count += 1
        return count
    return inc
foo = counter()
print(foo(), foo())
```

```python
"""
使用全局变量实现上面的例子，方法2
"""
def counter():   
    global count # global只能放到count前面，先声明再定义
    count = 0    
    def inc():
        global count # 有了第一个global后，第二个global也需要加上，
                     # 因为将第二个count定义成全局变量，count+=1,
                     # 才不会重新定义 count
        count += 1   # 先引用再定义，先引用再赋值
        return count
    return inc

foo = counter()
print(foo(), foo())
```



 ###  (6). python赋值语句的注意事项

在本例子中会报错，找不到x, 因为赋值即定义（在函数定义时，已经解释了语句 x += 1, 所以左侧的x被重新定义成局部变量）

  ```python
x = 5
def test():
  x += 1 # x = x + 1
  print(x)
  ```

  解决上诉问题的方法：

  ```python
  x = 5
  def test():
    global x  #x不可以被定义为局部变量 
    x += 1 # x = x + 1
    print(x)
  ```

  打印x则为100

  ```python
  x = 5
  def test():
    global x  #x不可以被定义为局部变量 
    x = 100
    x += 1 # x = x + 1
    print(x)
  print(x)
  
  # 101, 101
  ```

  

使用函数时尽量使用形参定义局部变量

```python
# method1  方法不好
x = 1
y = 2
def add():
  print(x + y)
  
# method2 方法好
def add(x, y):
  print(x + y)
```

###  (7). lambda表达式

+ lambda表达式记匿名函数，格式： lambda[参数列表] ：表达式

+ 参数列表中参数的个数>=0,  参数可以是形参的任意一种， 后面的冒号必须写，表达式相当于函数返回值，不能出现赋值语句=，表达式可以返回生成器，列表，集合，字典，迭代器，也可以再包含一个lambda表达式。

  python中的lambda表达式只能有一行，称为单行函数

  例如：

  ``` python
  def fn():
    return 0
  # 等价于
  lambda : 0  # 省略了函数名字，和return，更简洁
  
  # 返回0的函数在字典中的应用1
  from collections import defaultdict
  dict1 = defaultdict(lambda : 0)
  for i in 'abc':
      for j in range(4):
          dict1[i]+= 1 # KeyError  dict1[i] = (lambda : 0)()
  print(dict1)
  
  # 返回0的函数在字典中的应用1
  from collections import defaultdict
  dict1 = defaultdict(int)
  for i in 'abc':
      for j in range(4):
          dict1[i]+= 1
  print(dict1)
  ```



+ 用途：一般用在高阶函数传参时

  例如：

  ```python
  sorted([1, 2, 3, 'a'], key=str)
  # 等价于
  sorted([1, 2, 3, 'a'], key=lambda x: str(x))
  ```

  ```python
  # 普通传参
  lambda x, y=1: x+y  # 等价于fn，返回函数对象
  (lambda x, y=1: x+y)(2) # 等价于fn(2)  2
  
  
  # keyword_only参数
  (lambda x, *, y: x + y)(1, y=2)
  (lambda x, *, y: x + y)(x=1, y=2)
  
  (lambda x, *, y=2: x + y)(1)
  (lambda x, *, y=2: x + y)(x=1)
  (lambda x, *, y=2: x + y)(1, y=2)
  (lambda x, *, y=2: x + y)(x=1, y=2)
  
  
  # 可变位置参数，表达式可以返回迭代器，列表，集合，元组等
  # 思考如果参数传入range会返回什么？
  (lambda *args: (x for x in args))(*range(5))
  (lambda *args: [x for x in args])(*range(5))
  (lambda *args: {x%2 for x in args})(*range(5))
  (lambda *args: [(x,x) for x in args])(*range(5))
  
  
  # 可变关键字参数, 注意结构的星号
  (lambda *kwargs: {i:0 for i in kwargs})(*{'a':1, 'b':2})
  (lambda *kwargs: {i:0 for i in kwargs})(*dict(a=1, b=2))
  
  
  # 列表生成式与lambda表达式混合使用,lambda表达式里面还有
  # 一个lambda,并使用map高阶函数
  [i for i in (lambda *args: map(lambda x: x+1, args))(*range(3))]
  [i for i in (lambda *args: map(lambda x: (x+1, args), args))(*range(3))]
  # [(1, (0, 1, 2)), (2, (0, 1, 2)), (3, (0, 1, 2))]
  ```

  

### (8). 递归

+ 递归是指函数直接或者间接的调用自身（在同一个函数内部，或者多个函数之间相互调用），递归一定要有边界条件，当边界条件满足时递归返回，当边界条件不满足时，递归前进。递归的深度不宜太深，python中对递归的调用深度做了限制，以保护解释器（不要超过1000）。在写代码的过程中，要避免函数间接调用导致的循环递归。递归的效率相对较低，因为每一次调用都要开辟新的栈桢，所以即使递归很简洁，能不用就不用。

+ 大部分递归都可以通过循环实现

  例子：

  ```python
  # 斐波那切数列
  # 循环实现
  a = 0
  b =1
  ```

  



### (9). 高阶函数

高阶函数：如果一个函数的参数或者返回值中有函数
则这个函数是高阶函数

例如：

```python
# 是高阶函数，counter()返回值指向内层函数
# 如果返回inc(),也是高阶函数
def counter(base):
    def inc(step=1):
        nonlocal base
        base += step # 在内层又重新定义了base,里面的base已经看不到外面的base了，两个base不是同一个
        return base
    return inc
  
fn = counter(2)
fn() # 3  # 如果inc(), 后面加括号，则counter直接返回3


# f1和f2是函数调用的结果，无法比较大小
# 所以 = 用来判断地址是否相等，每次函数
# 调用都创建新的栈桢，所以地址不同，但是
# 标识符 counter 的地址没有变。
f1 = counter(5)
f2 = counter(5)
f1 = f2 f1 is f2  #(False, False)

```



#### (1). sorted()

插入排序实现sorted()高阶函数，不可以用while循环的原因，思考？

思考？ ['12', '1', '3', '0']如何排序

```python
def sorted(iterable, *, key=None, reverse=False):
    new_list = []
    for value in iterable:
        cvalue = key(value) if key else value
        for j, value1 in enumerate(new_list):
            cvalue1 = key(value1) if key else value1
            flag = cvalue < cvalue1 if not reverse else cvalue > cvalue1
            if flag:
                new_list.insert(j, value)
                break
        else:
            #new_list.insert(i, value)
            new_list.append(value)
    return new_list
 

nums = ['a', 9, 0, 8, 6, 2, 2, 2, 1, 7]
sorted(nums, key=str, reverse=True)
```

#### (2). filter()

filter(function, iterable)
function是**一个参数**的函数，且返回值应当是bool或者等效布尔值
function参数如果是None, 可迭代对象的每一个元素自身等效bool

```python
# function 不是None, 则返回表达式对应True的可迭代元素
# function 过滤掉部分元素，但是最终表达式返回True，元素才可以返回
list(filter(lambda x: x%3==0, range(10)))
# [0, 3, 6, 9]

list(filter(lambda x: x%3, range(10)))
# [1, 2, 4, 5, 7, 8]

# 将等效于None的元素过滤掉
list(filter(None, range(5)))
# [1, 2, 3, 4]

list(filter(None, range(-5, 5)))
# [-5, -4, -3, -2, -1, 1, 2, 3, 4]
```

#### (3). map()

可以代替zip()

map(function, *iterables)

```python
dict(map(lambda x: (x%5, x), range(500)))
# {0: 495, 1: 496, 2: 497, 3: 498, 4: 499}

dict(map(lambda x,y: (x, y), 'abc', range(3)))
{'a': 0, 'b': 1, 'c': 2}

dict(map(lambda x:x, zip('abc', range(3))))
```
### (10). 生成器函数

生成器表达式：(i for i in range(3))

生成器函数：在函数中出现yield关键字

生成器函数的执行过程 ：

```python

# 被驱动一次，遇到一个yield时函数暂停，yield返回一个值，被驱动第二次
# 遇到第二个yield函数暂停，返回第2个值，第三次驱动遇到return，函数返回
# 因为没有yield了，所以驱动时会报错，但可以添加缺省值避免包报错，next(g, None),next()
# 是一个函数，不是g的属性

def gen():
    print(1)
    yield 2
    print(3)
    yield 4
    print(5)
    return 6
  
g = gen() # 直接调用函数是个生成器，没有打印和输出，函数体不会立即执行
next(g) # 驱动一次打印1，返回2，停在第3行

next(g) # 驱动第二次打印3，返回4，停在第5行

next(g) # 驱动第二次打印5，报错，在错误中可以看的返回的6

next(g, 6)# 打印5，返回缺省值6

# 没有显式的return
def gen():
    print(1)
    yield 2
    print(3)
    yield 4
    print(5)
    
g = gen()
next(g)
next(g)
next(g) # 打印5，报错，错误中返回一个看不到的None
next(g, None) # 打印5，不会报错，返回一个看不到的None
```

无限次循环例子：

```python
# 无限循环, 每一次循环遇到yield会暂停
def counter():
    i = 0
    while True:
        i += 1
        yield i
c = counter()
next(c) # 返回1，停在yield
next(c) # 返回2，停在yield
```

计数器例子：

```python
# 计数器
def inc():
    def counter():
        i = 0
        while True:
            i += 1
            yield i
    c = counter()
    def fn():    # return lambda : next(c)  后3行可以用lambda表达式代替
        return next(c) 
    return fn 
g = inc()
```

计数器改进例子：

思考c.send(0)

```python
def inc():
    def counter():
        i = 1
        while True:
            i += 1            
            reponse = yield i
            if reponse is not None:
                i = reponse
            
#         def a():
#             nonlocal reponse            
    c = counter()        
    return lambda reset=False: next(c) if not reset else c.send(0)
g = inc()
g()
g()
g(True) # 需要调用几次g(),等待生成器启动，才可以使用重置功能
```



生成器实现斐波那契数列：

```python
# 斐波那契数列，生成器实现
def fib():
    a1 = 0
    a2 = 1
    while True:
        a1, a2 = a2, a1+a2
        yield a1
g = fib()
count = 1
for i in g:    
    if count == 101:
        print(i)
        break
    count += 1
       
```

生成器函数与生成器表达式：

```python
# 前3个例子为函数
# 调用函数，使用g()
g = lambda : (i for i in range(5))

def foo():
    yield from range(5)   # from后面加可迭代对象
        
# 生成器函数与生成器表达式比较，可以写出复杂的功能
def foo():
    for i in range(5):
        yield i
        
# 第4个例子为generator       
m = (i for i in range(5))
```

### (11). 装饰器

装饰器：无参装饰器、有参装饰器
无参装饰器：是一个函数，无参实际上是只有一个函数作为参数，
而且装饰器返回一个函数。

```python
# 给函数增加统计时间的功能
import datetime
def add(a, b):
    return a + b

def logger(fn, *args, **kwargs): # 同时传入另一个函数的参数和变量
    start = datetime.datetime.now()
    x = fn(*args, **kwargs)
    
    delta = (datetime.datetime.now()-start).total_seconds()
    print(delta)
    return x
    
logger(add, 1, 2) # 三种调用方式等价
logger(add, 1, b=2)
logger(add, a=1, b=2)



# 第一次修改，在logger中先传入add, 再传入2个参数(柯里化)
import datetime

def add(a, b):
    return a + b

def logger(fn):
    def wrapper(*args, **kwargs):     
        start = datetime.datetime.now()
        x = fn(*args, **kwargs)
        delta = (datetime.datetime.now()-start).total_seconds()
        print(delta)
        return x
    return wrapper
logger(add)(1, 2) 


# 进一步修改成装饰器（背）
import datetime

def logger(fn):
    def wrapper(*args, **kwargs):     
        start = datetime.datetime.now()
        x = fn(*args, **kwargs)
        delta = (datetime.datetime.now()-start).total_seconds()
        print(delta)
        return x
    return wrapper

@logger # add = logger(add)
def add(a, b):
    return a + b

# logger(add)(1, 2) 相当于在add上面加一个装饰器 
add(1, 2)




# 在上面装饰器的基础上增加修改函数fun.__name__ 、fun.__dic__的功能
def update_add():
    wrapper.__name__ = fn.__name__
    wrapper.__doc__ = fn.__doc__

def logger(fn):
    def wrapper(*args, **kwargs):
        'wrapper doc'
#         wrapper.__name__ = fn.__name__ # 写到里面只有函数执行时才会被修改
#         wrapper.__doc__ = fn.__doc__   
        return fn(*args, **kwargs)
    wrapper.__name__ = fn.__name__  # 写到外面在函数定义时就可以被修改
    wrapper.__doc__ = fn.__doc__
    
    #update_add(fn, wrapper)
    return wrapper

@logger # add = logger(add)
def add(a, b):
    'add doc'
    return a + b    
# 调用add, 先执行装饰器，在返回来的add基础上再接着执行
# 调用logger(add),返回内层的wrapper函数，该函数用到
# 外层函数的fn变量，形成闭包，所以但调用到内层函数时fn,
# fn不会消亡
# 当调用add时，add已经指向wrapper函数对象了，所以，当
# 获取name和dict属性时，得到的是wrapper属性
add(1, 2)


# 第一次修改将更新操作提取成一个函数
def update_add(wrapper, fn):
    wrapper.__name__ = fn.__name__
    wrapper.__doc__ = fn.__doc__
    
def logger(fn):
    def wrapper(*args, **kwargs):
        return fn(*args, **kwargs)
   
    update_add(wrapper, fn)
    return wrapper
    
@logger # add = logger(add)
def add(a, b):
    return a + b
#add(1, 2)
add.__name__

# 第二次修改，柯里化实现修改属性的功能
def update_properties(src):
    def _copy(dest):
        dest.__name__ = src.__name__
        dest.__doc__ = src.__doc__
        return dest # 装饰器的内层函数需要有返回值
    return _copy    
  
def logger(fn):
    @update_properties(fn)  #wrapper = update_properties(wrapper, fn)
    def wrapper(*args, **kwargs):
        return fn(*args, **kwargs) # 装饰器的内层函数需要有返回值   
    return wrapper
  
@logger # add = logger(add)
def add(a, b):
    return a + b


#add(1, 2)
add.__name__

```

## 12. 正则表达式

正则表达式(Regular Expresion): regex,regexp,RE

+ 基本正则表达式：(BRE), grep、sed、vi等软件支持。vim有扩展

+ 扩展正则表达式：(ERE) egrep(grep-E)、sed-r等

+  PCRE:几乎所有高级语言都是PCRE的方言或者变种

+ 正则表达式中的元字符(metacharat er):

  ![](/Users/jw/Projects/python23/magedu/re元字符.png)

\w : 可以匹配字母，数字，下划线，中文



+ 控制匹配次数的字符：

  ![](/Users/jw/Projects/python23/magedu/re匹配数量.png)

+ 捕获(分组匹配)：

  ![](/Users/jw/Projects/python23/magedu/re捕获分组匹配.png)

+ 贪婪匹配：

  ![](/Users/jw/Projects/python23/magedu/re贪婪匹配.png)

+ 匹配反义字符

  

转义字符：正则表达式中有特殊意义的字符用\转义，例如：
\\ 表示反斜杠  \r \n \r\n表示换行
或： x|y
    

# 五、知识点杂记

+ 剩余内存够用不代表连续的内存够用
+ 字节码也是可以被虚拟机识别的二进制
+ js可以动态生成网页，但是消耗内存
+ 代码都放放在内存中，以便cpu使用
+ 二进制的机器语言 到cpu的指令集一定要有几行汇编语言
+ 动态语言运行时才知道变量类型，静态语言编译时就知道变量类型
+ 赋值即定义，赋值同时重新指向
+ Jupyter notebook
   + 快捷键：
   + m 切换文字
   + ‘#’后面加空格
   + ‘*’ 表示正在运行 两种停止办法
   + shift + enter 运行
   + ctrl + enter 生成新行加运行
   + a b 新建cell
   + 找个文件夹打开 jupyter notebook
   + ~/.pip/pip.conf 里面填写`[阿里云镜像](mirrors.aliyun.com)` 里面pypi
的内容
   + dd  删除单元格
   + _  下划线返回上一次输出，__两个下划线表示前2次输出
   + 可以使用 ls cd       cd-   (减号表示)上一次目录
   + _dh   可以到处切换历史
   + ！touch test.txt表示当前操作系统中的命令
   + %%timeit  语句块的时间，%timeit primenum()函数执行时间
   + 在jupyter notebook里面无out无返回值
+ 程序放在内存中分为几个进程
+ 几个核就是几个cup
+ 充分利用内存可以优化程序
+ python中大写字母一般用在类中，或者表示常量
+ python常量无法定义，但是可以以全大写字母表示常量
+ 字面常量：例如12，不可以更改，但可以通过运算生成新的常量13
+ 三引号可以表示多行字符串，也可以识别里面的单引号和双引号
+ 不要同时使用多个if if 尽量使用if elif else
+ 除法的计算量很大
+ [1,2] +[4,5]表示新生成一个列表（会单独占用空间）
+ str(任何对象都可以转换成字符串)
+ if else 判断语句如果多，对效率的影响不大，但是如果下面的交换次数多则会影响效率
+  容器与遍历互为充要条件，可以遍历的不一定有索引，但是有索引的一定可以遍历
+  reversed 函数底层实现，与倒着取索引-(i+1), 原理相同
+  referenced 引用
+  
+  


# 六、平时练习注意事项：
+ 多查看官方文档，自己整理
+ 练习时现有基本思路，写出代码再修改
+ 自己debug, 学会单元测试，注意多线程都会在哪里出现bug
+ 在学框架之前，需要熟悉标准库

# 七、待解决的问题：
+ 8086原理？
+ 固态硬盘与硬盘？
+ 标识符与变量？
+ c =3 >5 返回false，先计算右侧再进行左侧赋值

# 八、文件操作

文件操作：IO操作一般指文件IO，如果是网络IO就会直接说网络IO。
磁盘：目前仍是文件持久化最重要的设备
磁盘结构示意图：

![](/Users/jw/Projects/python23/magedu/磁盘结构示意图.png)

等弧长分区示意图：

![](/Users/jw/Projects/python23/magedu/磁盘等弧长分区.png)

+ 打开文件

  + 一般写文档时只使用'\n', 读文档时使用默认的None模式读取
  

open函数常用的参数：file mode encoding

open(file, mode='r', buffering=-1, encoding=None, errors=None, newline=None, closefd=True, opener=None)
  文件的访问模式分为：文本模式和二进制模式

  + mode

     r: 只读模式，不可以写入文件，如果文件不存在FileNotFoundError，rb rt(默认) rb+ rt+ r+

    w: 只写模式，不可以读文件，如果文件存在会**清空**原来的内容，从头开始写入，不存在会创建文件，wb wt wb+ wt+ w+

    x: 只写模式，文件存在会FileExitsError,  文件不存在会新创建一个文件，xb xt xb+ xt+ x+

    a: 只写模式，文件存在打开追加内容，文件不存在创建文件，写入内容，ab at ab+ at+ a+

    r: **只读**，wxa: **只写**,并且会产生新文件    

  + encoding:打开或者创建文件时都需要指定编码，因为可能会在不同的操作系统上使用文件，Windows中使用codepage代码页,可以认为每一个代码页就是一张编码表，cp936等同于GBK，这也是Windows中默认的编码，linux中默认的编码是utf-8。

  + errors: 如果值为NONE或strict，有编码错误会抛出ValueError, 如果值为ignore表示忽略编码错

  + newline: 一般文本模式会使用，只可以填5种None,  "",  '\r',  '\n',  '\r\n'

    写时：

    + None模式下，'\n'会被替换成系统的缺省行分隔符，例如：windows系统为'\r\n', mac系统'\r',linux系统'\n'

    +  ""空串模式下常见的换行符都会换行

    +  其他3种换行符，按照指定换行符换行
    
    

  读时：

  + None模式下，是在5种模式下唯一发生转换的模式'\r','\n','\r\n'都会被转换成'\n', 即'\n','\n','\n\n'
    
    +  ""空串模式下常见的换行符都认为是换行
  + 其他3种换行符，按照指定换行符换行


  + closefd:默认为True，表示关闭文件时会关闭文件描述符。

    例子：

```python
with open('test', 'w', newline=) as f:
		f.write('python\rwww.python.org\nwww.magedu.com\r\npython3')
# 在Windows下相当于写入
'python\rwww.python.org\r\nwww.magedu.com\r\r\npython3'
# 在mac下相当写入???
'python\rwww.python.org\rwww.magedu.com\r\rpython3'

newlines = [None, '', '\r', '\n', '\r\n']
for nl in newlines:
		f = open('test', newline=nl) # 分别替换不同换行符
		print(f.readlines())
		f.close()

# ['python\n', 'www.python.org\n', 'www.magedu.com\n', 'python3'] None模式下\r被替换为\n ???
# ['python\r', 'www.python.org\n', 'www.magedu.com\r\n', 'python3'] ''模式下会识别出来3中换行符，但是不会替换
# ['python\r', 'www.python.org\nwww.magedu.com\r', '\npython3'] 遇到'\r'换行
# ['python\rwww.python.org\n', 'www.magedu.com\r\n', 'python3'] 遇到'\n'换行
# ['python\rwww.python.org\nwww.magedu.com\r\n', 'python3'] 遇到'\r\n'换行

```

+ 文件读取方法总结

  f.read(size=-1) # 从头开始读
  f.readline(size=-1) # 一行一行读取，size可以设置读取行内几个字符或字节
  f.readlines() # 读取所有行返回列表

  大多数情况都用下面的方式读取文件内容

  ```python
  f = open('test') #  返回可迭代对象
  for line in f:
      print(line.encode().strip())
  f.close()
  ```

+ 写方法总结

  f = open('test', 'w+')
  f.writelines(['abc\n', '123']) #需要提供换行符

  常用的写入文件的方法

  ```python
  f = open('test', 'w+')
  f.write('\n'.join(['abc', '123']))
  ```

  

+ 关闭方法总结

  f.close() # 文件关闭时自动调用一次flush()
  为了避免因为异常而无法关闭文件，有两种处理方式
  方式1:异常处理

  ```python
  try:
      f = open('test', 'w')
      f.read()
  finally: # 无论try中是否报错都会执行finally 语句
      f.close()
  ```

  方式2:上下文管理的方式
  上下文管理的语句不会开启新的作用域
  with语句块执行完会自动关闭文件对象

  ```python
  with open('test', 'w') as f:
      f.write('abc')
  f.closed
  ```

+ 其他方法总结

  f.seekable() f.readable() f.writable()
  f.closed 查看文件是否关闭，返回一个布尔值，不能加括号，不可调用
  如果文件已经关闭则 f.fileno()会报ValueError

  cat test1 # 查看文件，如果文件中是字节b'abc'，则也可以查看出'abc'
  f.read() # 如果文件中是字节b'abc', 则查看出b'abc'

+ 文本模式及二进制模式总结

| 方法：                                                       | 文本模式  ：                                                 | 二进制模式 ：                                                | 指针位置：                            |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------- |
| f.read(2)                                                    | 按字符读取                                                   | 按字节读取                                                   | 指针起始在0，读完指针指向第2个位置    |
| f.write()                                                    | 按字符写入                                                   | 按字节写入                                                   | 从指针当前位置开始写，写完指针停在EOF |
| f.tell()                                                     | -                                                            | -                                                            | 显示指针当前位置                      |
| f.seek(偏移量[,whence=0,1,2])                                | 按字节偏移，3种模式分别是指针在开头，也是缺省值 ，offset只能接受正整数；                                  当前指针位置，offset只能接受0；                                                EOF offset只能接受0。 | 按字节偏移，3种模式是开头位置，也是缺省值                                                offset只能接受正整数；                                                当前指针位置，offset可正可负；                                                EOF offset可正可负。                                             二进制模式支持任意起点的偏移，从头，从尾，从中间开始，向后 seek可以超界，向前超界则会抛异常 |                                       |
| open中的参数buffer                                 <br/>可以看作是是一个先进先出的队列（FIFO）文件，<br/>在缓冲区满了或者达到阈值时，数据会被flush到磁盘上<br/>flush()将缓冲区数据写入到磁盘、<br/>close()关闭前会自动第一次flush()<br/> | -1 缺省模式可通过io.DEFAULT_BUFFERSIZE  查看大小（一般都用缺省）缺省值的大小一般是4096或8192KB<br /><br/>>1使用缺省模式<br /><br />1 行缓冲遇到换行符才flush（用得少<br /> <br /> 0不支持 | -1 同文本模式<br/><br />>1比如buffer=10,那么超过10缓冲区hui被flush<br/><br />1不支持<br/><br />0关闭缓冲区（一般不用）br /><br /><br /> |                                       |
| open中的参数mode为a时                                        | -                                                            | -                                                            | 指针会停在EOF                         |

linux查看打开文件数量

![](/Users/jw/Projects/python23/magedu/Linux查看open文件数量.png)

  

# 九、作业及练习

