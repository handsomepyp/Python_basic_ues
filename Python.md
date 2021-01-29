# Python

__python的特点:以对象为核心组织代码(Everything is object),支持多种编程范式(multi-paradigm),采用动态类型(dynamic typing),自动进行内存回收(garbage collection),并能用C语言库进行扩展__

## 第二章、Python基础

#### 2.3.2 id(obj) : 获取对象obj的内存地址，del x :清空x的内存空间 type(x):获取x的类型

#### 2.3.3 输入和输出

#### input() 默认输入为str类型，a=int(input()):将其改为整型输入

#### 2.5.1 算术运算符

| 运算符 | 描述                     |
| ------ | ------------------------ |
| //     | 取整除                   |
| **     | 幂，x**y表示返回x的y次方 |

#### 2.5.2 成员运算符

| 运算符 | 描述                                      |
| ------ | ----------------------------------------- |
| in     | 在指定的序列找到则返回True，否则返回False |
| not in | 没找到返回True，否则返回False             |

##### 例子 ：‘a' in 'abcd'  返回True

#### 2.5.6 身份运算符

| 运算符 | 描述                                          |
| ------ | --------------------------------------------- |
| is     | 判断两个变量是否引用同一个对象，是则返回True  |
| is not | 判断两个变量是否引用同一个对象，是则返回False |

##### a='abcd' ；b=a ； a is b 返回True

#### 2.5.7 位运算符

| 运算符 | 描述     |
| ------ | -------- |
| &      | 按位与   |
| ^      | 按位异或 |
| ~      | 按位取反 |
| \|     | 按位或   |
| <<     | 左移     |
| >>     | 右移     |

#### 2.6.1 条件语句（if...elif...else）

```python
if 表达式1:
	执行的代码块1
elif 表达式2:
	执行的代码块2
	...
else:
	执行的代码块n
```

#### 2.6.2 循环之while循环（while 表达式：循环体）

```python
while 表达式:
	循环体
```

#### 2.6.3 循环之for循环

```python
for 可迭代的变量(i) in 序列：
	 循环体
for i in 'python':
  if i == 'h':
    print(i)
```

#### 2.6.6 pass语句

##### 1.空语句，不执行具体的功能

## 第三章、数据类型

### 3.1数据类型

#### 3.1.2 浮点型

##### 对浮点数比较大小:

```python
epsilon = 0.000000001
abs((2.2-1.2)-1)<=epsilon # abs函数返回绝对值
```

#### 3.1.4 复数（a+bj表示）

#### 3.2.1 字符串的常用方法

```python
str = 'http://www.oldboyedu.com/'
str1[3] # 从左到右从0开始
'p'
str[-1] # 从右到左从-1开始
'/'
len(str) # 内置函数，str的长度 
```

##### 1.字符串的切片 str[start_index : end_index : step]

##### 

```python
str = 'http://www.oldboyedu.com/'
str[-3] # 取倒数第三个字符
str[:6] # 取前六个字符
str[7:] # 第七个字符取到末尾
str[6:9] # 两者之间的字符
str[2:9:2] # 两者之间每隔两个字符取一个
str[::4] # 所有字符每隔4个取一个
str[::-1] # 反转字符串
```

##### 2.字符串常用的9个方法

###### 1.str.center(width,filler):width为字符串宽度,filler为填充字符

###### 返回值:返回一个指定宽度的字符串，如果width小于字符串本身的宽度，直接返回字符串，否则字符串两边填充filler

```python
str = 'pyp yyds!'
str.center(20,'*')
输出:*****pyp yyds!******
```

###### 2.str.count(sub,start=0,end=len(str)):sub为要统计的字符，start为开始查找的位置，默认为0，end为字符串结束的位置，默认到字符串的末尾。

###### 返回值：返回sub在字符串中出现的次数

```python
str1="www.oldboyedu.com!"
print(str1.count('w'))
3
print(str1.count('ww'))
1
print(str1.count('ww',1,8))
1
print(str1.count('ww',4,8))
0
```

###### 3.str.startswith(obj,start,end):obj为要判断的对象(可以为字符串或元素)，start和end标识查询的字符串范围

###### 返回值：如果该字符串中存在指定的obj对象，返回True，否则返回False

###### 功能：判断字符串是否已指定的字符串开头

```python
str1="hello oldboy"
print(str1.startswith('old'))
False
print(str1.startswith('h'))
True
print(str1.startswith('e'))
False
print(str1.startswith('i'))
False
print(str1.startswith('hel',2,10))
False
```

###### 4.str.index(obj,start,end):obj是要查找的字符串对象，start为开始的索引，end为结束位置，若start和end不指定，默认检索整个字符串

###### 返回值：包含则返回字符串对象所在字符串中开始位置的索引，否则返回异常

```python
str1="hello oldboy"
print(str1.index('he'))
0
print(str1.index('ol',5,10))
6
```

###### 5.str.join(sequence):sequece为要连接的元素序列（sequence必须是字符串）

###### 返回值：返回生成的新的字符串

```python
str1='-'
str2=''
seq=['p','y','t','h','o','n']
print(str1.join(seq))
p-y-t-h-o-n
print(str2.join(seq))
python
```

###### 6.str.strip(sub):sub为指定的字符（功能：截取字符串两端的sub字符，默认截取空格和换行）

###### 返回值：返回截掉指定字符后的新字符

```python
str1='*******old****boy*****'
print(str1.strip('*'))
old****boy
```

###### 7.str.replace(old,new,[max]):old是旧的字符，new是新的字符，[max]代表替换最多不超过max次

###### 返回值：返回old替换为new后新的字符串

```python
str1='oldboy said hello python'
print(str1.replace('o','O'))
OldbOy said hellO pythOn
```

###### 8.str.upper()、str.lower():

###### 返回值：返回小写转大写的字符串 , 返回大写转小写的字符串

```python
str1='oldboy'
print(str1.upper())
OLDBOY
str1='OLDboy said hello python'
print(str1.lower())
oldboy said hello python
```

###### 9.str.split(str="",num):str为要分割的字符串，num表示分割次数

###### 返回值：split方法返回一个列表，列表内是按照分隔符分割的元素

```python
str1='oldboy said hello python'
print(str1.split())
['oldboy', 'said', 'hello', 'python']
print(str1.split('o'))
['', 'ldb', 'y said hell', ' pyth', 'n']
print(str1.split('o',2))
['', 'ldb', 'y said hello python']
```

##### 3.一个面试题

###### 将str1="Im love, Python!"变成str2="Python,love Im"

```python
str1="Im love, Python!"
# 先分割
print(str1.split(' '))
#['Im', 'love,', 'Python!']
# 再反转
print(str1.split(' ')[::-1])
#['Python!', 'love,', 'Im']
# 再将列表合并
print(''.join(str1.split(' ')[::-1]))
#Python!love,Im
# 再将！替换为，
print(''.join(str1.split(' ')[::-1]).replace(',',' ').replace('!',','))
#Python,love Im
```

#### 3.2.2 字符串总结

| 字符串的操作 | 描述       |
| ------------ | ---------- |
| []           | 索引操作   |
| [:]          | 切片操作   |
| +            | 拼接字符串 |
| *            | 复制字符串 |
| in,not in    | 成员测试   |

| 方法 | 描述 |
| ---- | ---- |
| str. |      |

###### 应用在字符串中的常用函数

| 函数     | 描述                                         |
| -------- | -------------------------------------------- |
| max(str) | 根据ASCⅡ表，返回字符串中对应ASCⅡ表最大的字符 |
| min(str) | 根据ASCⅡ表，返回字符串中对应ASCⅡ表最小的字符 |
| len(str) | 返回字符长度                                 |

###### eval(str):接收一个字符串并求值，int 、float和str在字符串为数字时可相互转换

#### 3.2.4 help():可查看数据类型的方法和具体方法的使用

### 3.3 编码方式（待完善）

### 3.4 列表(list)

#### 3.4.1 基本操作

##### 1.创建列表(用"[]"来创建列表，用","分隔列表中的每个元素)

###### range(start,end,step) :start表示区间起始位置，end表示区间结束位置，step表示步长

```python
l=[]
print(type(l))
print(list('dawdawffdrgdr656835'))
#<class 'list'>
#['d', 'a', 'w', 'd', 'a', 'w', 'f', 'f', 'd', 'r', 'g', 'd', 'r', '6', '5', '6', '8', '3', '5']
```

##### 2.列表的合并 '+'

##### 3.列表的重复 '*'

##### 4.成员资格 'in'

##### 5.通过索引取值

##### 6.切片操作

##### 7.通过for循环取值

##### 8.为列表添加元素

##### 9.列表元素更新

##### 10.通过下标索引删除元素

#### 3.4.2 常用方法

##### 1.list.append(obj):在列表末尾添加新的元素

```python
l=['a','b','c','1','2']
l.append(1)
l.append('b')
print(l)
# ['a', 'b', 'c', '1', '2', 1, 'b']
```

##### 2.list.insert(index,obj):在列表的指定位置添加新的元素

```python
l=['a','b','c','1','2']
l.insert(0,154)
print(l)
#[154, 'a', 'b', 'c', '1', '2']
```

##### 3.list.pop(index):移除列表中的一个元素，并返回该元素的值，通过索引值删除

```python
l=['a','b','c','1','2']
l.pop(3)
print(l)
#['a', 'b', 'c', '2']
```

##### 4.list.remove(obj):obj为要移除的元素

```python
l=['a','b','c','1','2']
l.remove('a')
print(l)
#['b', 'c', '1', '2']
```

##### 5.del:删除列表内的元素,或连续几个元素，或整个列表    del obj1,obj2

```python
l=['a','b','c','1','2']
del l[2:4]
print(l)
#['a', 'b', '2']
```

##### 6.list.reverse():反转列表中的元素

```python
l=['a','b','c','1','2']
l.reverse()
print(l)
#['2', '1', 'c', 'b', 'a']
```

##### 7.list.sort():对原列表进行排序

| 方法                   | 描述                                 |
| ---------------------- | ------------------------------------ |
| list.append(obj)       | 列表添加元素到末尾                   |
| list.insert(index,obj) | 列表添加元素到指定位置               |
| list.pop(obj)          | 删除列表元素                         |
| list.remove()          |                                      |
| list.reverse()         |                                      |
| del obj1,obj2          |                                      |
| list.sort()            |                                      |
| list(seq)              | 将序列转换为列表                     |
| len(list)              |                                      |
| max(list)              |                                      |
| min(list)              |                                      |
| list.extend(seq)       | 列表末尾追加多个值                   |
| list.count(obj)        | 统计某个字符在列表内出现的次数       |
| list.index(obj)        | 找出指定元素的第一个匹配项的索引位置 |

#### 3.4.3 列表的嵌套（可以达到二维数组的效果）

### 3.5 元祖(tuple)

#### 3.5.1 基本操作

##### 1.创建元祖 ('()')

##### 2.元祖的取值

###### 按照索引取值

```python
t=(1,2,4,5,7,8,6,'a','b')
print(t[2])
print(t[2:5])
print(t[::2])
#4
#(4, 5, 7)
#(1, 4, 7, 6, 'b')
```

##### 3.元祖的重复 : *

##### 4.成员资格 ：in

```python
t=('a','b','abc')
print('a' in t)
# True
print('c' in t)
# False
```

##### 5.元祖的打包和解包

```python
t=1,2,3 #打包
x,y,z=t #解包
print(x,y,z,t)
# 1 2 3 (1, 2, 3)
```

##### 6.常用操作符

| 操作符                    | 描述     |
| ------------------------- | -------- |
| +                         | 合并     |
| *                         | 重复     |
| in                        | 成员资格 |
| for i in (1,2,3):print(i) | 迭代     |
| t[2]                      | 索引取值 |
| t[start,stop,step]        | 切片     |

##### 7.常用方法

| 函数       | 描述             |
| ---------- | ---------------- |
| len(tuple) | 返回元祖的长度   |
| max(tuple) | 返回最大的元素   |
| min(tuple) | 返回最小的元素   |
| tuple(seq) | 将序列转换为元祖 |

#### 3.5.2 元祖的嵌套

##### 1.创建同样大小的列表和元祖来观察不同

##### 2.通过存储开销来对比列表和元祖

##### 3.元祖是可哈希的，列表不是

### 3.6 字典

#### 3.6.1 基本操作

##### 1.创建字典 ('{key:value,key:value......}')

###### 1.1 字典不能按照索引取值

###### 1.2 字典中的key可以是任何不可变类型，比如整型、浮点型、字符串、元祖；而value不限制类型

#### 3.6.2 其他操作

##### 1 遍历字典

```python
d={'a':1,'b':2,'c':3}
for i in d:
  print(i)
# a 
# b
# c
for item in d.items():
  print(item)
# ('a', 1)
# ('b', 2)
# ('c', 3)
```

##### 2.对字典的key和value做取值处理（keys,values）

```python
d = {'a':1,'b':2,'c':3}
for k in d.keys():
  print(k)
'
a
b
c
'
for v in d.values():
  print(v)
'
1
2
3
'
print(d.keys())
'dict_keys(['a', 'b', 'c'])'
print(d.values())
'dict_values([1, 2, 3])'
```

##### 3.get方法

```python
# 判断某个字典中是否存在某个键，然后取值
d = {'a':1,'b':2,'c':3}
print(d.get('d')) # None
print(d.get('a')) # 1
```

##### 4.setdefault方法

```python
# 会将不存在的键添加
d = {'a':1,'b':2,'c':3}
print(d.setdefault('d'))# None
print(d.setdefault('a'))# 1
print(d)# {'a': 1, 'b': 2, 'c': 3, 'd': None}
```

##### 5.pop删除指定的键，popitem随机删除键值对，clear清空字典中所有键

```python
# pop删除键并返回值
d = {'a':1,'b':2,'c':3}
print(d.pop('a')) # 1
print(d) # {'b': 2, 'c': 3}
# popitem随机删除键值对
d = {'a':1,'b':2,'c':3}
print(d.popitem()) # ('c', 3)
print(d) # {'a': 1, 'b': 2}
# clear清空
d = {'a':1,'b':2,'c':3}
d.clear()
print(d) # {}
```

##### 6.fromkeys(seq,None)创建一个字典

```python
# seq为序列类型(字符串或列表)，第二个参数为value(默认为None)
print(dict.fromkeys('apple','orange'))
# {'a': 'orange', 'p': 'orange', 'l': 'orange', 'e': 'orange'}
```

##### 5._contains__方法或是 in，判断是否在字典中



##### 常用方法

| 方法                | 描述                                   |
| ------------------- | -------------------------------------- |
| x in dict           | 成员运算符                             |
| help(dict)          | 获取字典的帮助信息                     |
| len(dict)           | 返回字典项目的个数                     |
| str(dict)           | 转字典类型为字符串类型                 |
| type(dict)          | 查看字典类型                           |
| sorted(dict)        | 字典排序                               |
| dict.fromkeys(seq)  | 创建新字典                             |
| dict1.update(dict2) | 另一个字典(dict2)更新当前字典(dict1)   |
| dict.keys()         | 以列表的形式返回字典的所有的键         |
| dict.values()       | 以列表的形式返回字典的所有的值         |
| dict                |                                        |
| dict.popitem()      | 随机删除字典中的键值对                 |
| dict.pop()          | 删除字典中的指定key，并返回相应的value |
| del dict            | 删除字典或期内的指定键值               |
| dict.clear()        | 将字典清空                             |

##### format函数的用法

```python
# 1.不指定参数，按照默认顺序传参
'{},{}'.format('hello','oldboy')
'hello oldboy'
(默认将hello填充到第一个花括号内，oldboy填充到第二个花括号内)
# 2.按照指定位置传递参数
'{0} {1}'.format('hello','oldboy')
'hello oldboy'
'{1}{0}{1}{0}'.format('hello','oldboy')
'oldboy hello oldboy hello'
(format内两个参数都有自己的位置序号，format根据序号填充字符串)
# 3.设置参数

# 4.通过列表索引设置参数
# 5.通过字典设置参数
```

| 格式    | 说明                                            |
| ------- | ----------------------------------------------- |
| {:.4f}  | 保留四舍五入后的四位小数                        |
| {:+.2f} | 带符号保留小数点后两位（正数的前面加了个‘+’号） |
| {:-.2f} | 带符号保留小数点后两位                          |
| {:.0f}  | 保留整数位                                      |
| {:0<3d} | 数字补0，填充在右侧，宽度为3                    |
| {:0^3d} | 数字补0，填充在两边，宽度为3                    |
| {:0>3d} | 数字补0，填充在左侧，宽度为3                    |
| {:r<3d} | 数字补字母‘r’，填充在右侧，宽度为3              |
| (:r^3d) | 数字补字母‘r’，填充在两侧，宽度为3              |
| {:r>3d} | 数字补字母‘r’，填充在左侧，宽度为3              |
| {:.2%}  | 指定位数的百分比格式                            |
| {:,}    | 以逗号分隔数字格式                              |
| {:20d}  | 默认右对齐，宽度20                              |
| {:>20d} | 右对齐，宽度20                                  |
| {:<20d} | 左对齐，宽度20                                  |
| {:^20d} | 居中，宽度20                                    |

```python
a1 = '{:.4f}'.format(3.1415926)
print(a1)
a2 = '{:.4f}'.format(3.1415926)
```

#### 3.6.3 字典的嵌套

### 3.7 集合(set)

#### 3.7.1 基本操作和方法

##### 1.添加新元素set.add(obj)

```python
s = {1,2}
s.add('a')
print(s) #{1, 2, 'a'}
```

##### 2.将一个集合更新到另一个集合set1.update(set2)

```python
s = {1,2}
s1 = {1,2,3,4}
s.update(s1)
print(s1) #{1, 2, 3, 4}
```

##### 3.访问集合

```python
s = {1,2,3,4,5,'a','b','c'}
for i in s:
  print(i) 
1
2
3
4
5
a
b
c
```

##### 4.删除集合 set.pop，set.clear,del

```python
# set.pop() 随机删除集合的元素，并将删除元素返回。集合为空就会报错
# set.remove(obj) 删除指定的元素，若元素不存在就会报错
# set.discard(obj) 删除指定的元素，不会报错
# set.clear() 清空集合
# del set 删除集合
```

#### 3.7.2 集合的运算

##### 1.集合的交集 intersection() 或 &

```python
s1 = {1,54,75,'da','xiao'}
s2 = {26,57,'xiao'}
print(s1&s2) # {'xiao'}
s1.intersection(s2) # {'xiao'}
# intersection_update 在求出结果后更新到原来的集合里
# isdisjoint 判断两个集合是否有交集
```

##### 2.集合的并集 union() 或 |

```python
s1 = {1,54,75,'da','xiao'}
s2 = {26,57,'xiao'}
print(s1|s2) # {1, 'xiao', 54, 'da', 57, 26, 75}
print(s1.union(s2)) # {1, 'xiao', 54, 'da', 57, 26, 75}
```

##### 3.集合的差集 diffence() 或 -

```python
s1 = {1,54,75,'da','xiao'}
s2 = {26,57,'xiao'}
print(s1-s2) # {1, 'da', 75, 54}
print(s1.difference(s2)) # {1, 'da', 75, 54}
```

##### 4.对称差集 symmetric_difference 或  ^

```python
s1 = {1,54,75,'da','xiao'}
s2 = {26,57,'xiao'}
print(s1^s2) # {1, 'da', 75, 54, 57, 26}
print(s1.symmetric_difference(s2)) # {1, 'da', 75, 54, 57, 26}
```

##### 5.判断子集、超集 issubset()判断一个集合是否为另一个集合的子集 issuperset() 判断一个集合是否为另一个集合的超集

```python

```

##### 6.运用集合中的关系运算符表示集合的关系

###### ==、>= 、<=、 >、 <、 != 仅仅代表两个集合的包含关系，不能代表大小关系

##### 方法总结

| 方法(函数)                              | 描述                             |
| --------------------------------------- | -------------------------------- |
| len(set)                                |                                  |
| max(set)                                |                                  |
| min(set)                                |                                  |
| sum(set)                                | 返回集合元素之和                 |
| sorted(set)                             | 排序集合内的元素                 |
| set.add(obj)                            | 添加元素                         |
| set1.issuperset(set2)                   | 判断set1是否为set2的超集         |
| set1.issubset(set2)                     | 判断set1是否为set2的子集         |
| set1.sysmmetric_difference_update(set2) | 求对称差集并将结果更新到set1中   |
| set1.sysmmetric_difference(set2)        | 对称差集                         |
| set.update(set2)                        | 用set2更新当前set1               |
| set.copy()                              | 浅拷贝                           |
| set.discard(obj)                        | 删除指定元素                     |
| set.pop()                               | 随机删除集合内元素并将此元素返回 |
| set.clear()                             | 清空集合                         |
| set.remove(obj)                         | 删除指定元素                     |
| set1.dfference_update(set2)             | 求差集并将结果更新               |
| set1.difference(set2)                   | 差集                             |
| set1.union(set2)                        | 并集                             |
| set1.isdisjoint(set2)                   | 没有交集返回True，否则返回false  |
| set1.instersection(set2)                | 交集                             |

#### 3.7.3 集合的嵌套

### 3.8 推导式、三元表达式和深、浅拷贝

#### 3.8.1 列表推导式

```python
# 规则
variable = [expr for value in collection if condition]
条件         表达式         收集器             条件
```

```
sum = [i for i in range(10)]
print(sum)
# [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

```python
pyp = [x+y for x in 'abc' for y in 'ABC']
print(pyp)
# ['aA', 'aB', 'aC', 'bA', 'bB', 'bC', 'cA', 'cB', 'cC']
```

```python
# 集合推导式
# 规则
variable = {expr for value in collection if condition}
变量         表达式         收集器             条件
pyp = {i for i in range(10) if i%2 == 0}
print(pyp)
# {0, 2, 4, 6, 8}
```

```python
# 字典推导式
```

#### 3.8.2 三元表达式

```python
result = True if condition else False

x = 1
y = 2
if x < y:
  print(x)
else:
  print(y)
res = x if x<y else y
print(res)
# 1
# 1
```

#### 3.8.3 深浅拷贝

```python

```

## 第四章、函数

### 4.1 函数基础

#### 4.1.1 函数的定义与调用

```python
def <name> ([arg1,arg2,...argn]):
  """functional annotation"""
  pass
  return
# def 定义函数
# name 函数名
# 括号里的参数可选，冒号必不可少
# functional annotation:注释里写功能
# pass 函数具体功能实现代码
# 函数的特点：
	  1.一处定义，多处调用
  	2.最大化减少代码冗余和代码重用
    3.有利于程序结构分解
    4.可以打包代码，使功能更加独立
```

```python
def func():
  """文档说明书"""
  return 2
print(func.__doc__)
# 文档说明书
```

#### 4.1.2 函数的返回值

##### 1.函数没有return,没有返回值

```python
def foo():
	pass
f=foo()
print(f)
# 返回None(默认结果)
```

##### 2.返回一个值

```python
def foo():
	# return 1
  # return 'abc'
  # return [1,2,3]
  # return {'a':'b'}
  return len('abcd')
f=foo()
print(f)
# 4	
```

##### 3.返回多个值:值之间用逗号隔开，最后多个值以元祖方式返回

```python
def foo():
  return 1,2,{'a':'b'},[3,4]
  print(res)
result=foo()
print(result) # (1, 2, {'a': 'b'}, [3, 4])
print(result[2]) # {'a': 'b'}
```

#### 4.1.3 函数的参数

```python
def foo(value): # value:形式参数
  return value
foo(2) # 2:实际参数
```

| 参数传递方式                 | 描述                                                     |
| ---------------------------- | -------------------------------------------------------- |
| def foo1(value)              | 位置传参，按位置匹配传参                                 |
| def f002(value=None)         | 按关键字传参，通过变量名匹配传参                         |
| def foo3(value1,value2=None) | 按位置传参匹配和关键字传参搭配传参，称value2为默认参数   |
| def foo4(*arg)               | 可变长度传参，接收任意长度的位置参数，并手机在一个元祖里 |
| def foo5(value,*arg)         | 按位置匹配传参和可变长度传参搭配                         |
| def foo6(*args,value)        | *arg接收任意长度                                         |
| def foo7(**kwargs):          |                                                          |
| def foo8(*arg,**kwargs):     |                                                          |

#### 4.1.4 函数对象

##### 1.函数被引用

```python
def foo():
  return 'ok'
f1=foo()
print('f1',f1) #f1 ok
f2=foo
print('f2: ',f2) # 打印内存地址 f2:  <function foo at 0x000002C83E8AC1E0>
print('f2():',f2()) # f2(): ok
```

##### 2.函数当做函数的参数

```python
def bar():
  a=1
  print('a=',a)
def foo(b):
  pass
print(foo(bar)) #函数当做函数的参数，地址传递
```

##### 3.函数当做其他函数的返回值

```python
def bar():
  print("bar function")
def foo():
  return bar
f = foo()
print(f)
f()
# <function bar at 0x000001ADE15FC1E0>
# bar function
```

##### 4.函数当做容器类型的元素

```python
def add():
  print('add function')
def update():
  print('update function')
def select():
  print('selection function')
def delete():
  print('delete function')
dict = {'add':add,'update':update,'select':select,'delete':delete} #将函数定义在键值对的value中
while 1:
  cmd = input('Enter command:').strip()
  if cmd in dict:
    dict[cmd]()
  elif cmd == 'q':
    print('Goodbye')
    break
  else:
    print('Error command')
    continue
```

#### 4.1.5 命名空间和作用域

* 变量在函数内部定义的话，只能作用于函数内部，而外部无法调用这个变量

* 因为有了作用域，在函数内部和外部定义两个相同的变量名，却不会引起冲突
* 在任何情况下，变量的作用域只是与被赋值的地方有关，而与函数调用没有关系

* 内置作用域 > 全局作用域 > 局部作用域

#### 4.1.6 嵌套函数与嵌套作用域

##### 嵌套函数：一个函数将另一个或多个函数嵌套其内

##### 嵌套作用域：被嵌套起来的作用域，指的是嵌套在函数内部的作用域

#### 4.1.7 闭包函数

```python
def foo():
  x = 1
  y = 2
  def bar():
    print(x,y)
  return bar
f = foo() # 变量f就是bar函数
print(f) #<function foo.<locals>.bar at 0x000002AADBD491E0>
print(f.__closure__) # (<cell at 0x000002AADBD35BB8: int object at 0x00007FFB13C3EF00>, <cell at 0x000002AADBD35F78: int object at 0x00007FFB13C3EF20>)
print(f.__closure__[0].cell_contents) # 1
print(f.__closure__[1].cell_contents) # 2
```

### 4.2 装饰器

##### 语法糖(Syntactic sugar)：为程序添加某种语法，而这种语法对语言的原本功能没有影响

#### 4.2.1 开放封闭原则

* 对拓展是开放的
* 对修改是封闭的

#### 4.2.2 无参装饰器

##### 装饰器的本质：装饰器是任意可调用对象，被装饰的对象也可以是任意可调用的对象

##### 装饰器的功能：在不修改被掩饰对象源代码，以及调用方式的前提下，为其添加新的功能

* 不修改被装饰对象的源代码

* 不修改被调用对象的调用方式，就是说，被装饰对象不知不觉中添加了一些功能

* 要达到的目标：添加新功能

  ```python
  def timer(func):  # 装饰器
    def wrapper():  
      res = func()  # 执行被装饰函数代码
      print(res)    # 
    return wrapper  # 返回功能函数名
  @timer   
  def index():      # 被装饰器函数
    print('index function') 
  index()           # 执行index函数，自动触发装饰器函数的执行
  ```

#### 4.2.3  有参装饰器

#### 4.2.4 多装饰器

### 4.3 迭代器

__类似链表:不依赖索引取值__

```python
# 两种方法判断对象是否为可迭代对象
# 方法1:采用dir函数判断
print('str is iterable','__iter__' in dir('123'))
print('int is iterable','__iter__' in dir(123))
print('list is iterable','__iter__' in dir([1,2]))
print('set is iterable','__iter__' in dir({1,2}))
print('dict is iterable','__iter__' in dir({'a':1}))
print('tuple is iterable','__iter__' in dir((1,2)))
print('range is iterable','__iter__' in dir(range(10)))
"""str is iterable True
int is iterable False # 不是可迭代对象
list is iterable True
set is iterable True
dict is iterable True
tuple is iterable True
range is iterable True"""
# 方法2:通过isinstance函数判断
from collections import Iterable
print('str is iterable',isinstance('123',Iterable))
print('int is iterable',isinstance(123,Iterable))
print('list is iterable',isinstance([1,2],Iterable))
print('set is iterable',isinstance({1,2},Iterable))
print('dict is iterable',isinstance({'a':1},Iterable))
print('tuple is iterable',isinstance((1,2),Iterable))
print('range is iterable',isinstance(range(10),Iterable))
```

```python
# 迭代器的应用
it = {1,2,3}
it = it.__iter__()
print(it)
print(it.__next__())
print(it.__next__())
print(it.__next__())
# <set_iterator object at 0x0000022059077168>
# 1
# 2
# 3
```

> 可迭代对象和迭代器的区别
>
> 可迭代对象只有_____iter_____方法，而迭代器有____iter____和____next____方法

1. 迭代器的优点
   - 提供一种不依赖于索引的方式取值
   - 懒惰计算，节省内存空间
2. 迭代器的缺点
   - 取值不如索引方便
   - 迭代过程不可逆
   - 无法获取迭代器的长度

> for循环的本质：
>
> ​	for语句在可迭代对象上调用iter函数，iter函数返回一个迭代器，for语句循环调用迭代器的每一个元素的next方法，当迭代器为空时，提示for语句终止循环

### 4.4 生成器

#### 4.4.1 生成器函数

```python
from collections import Iterator
def generator_func():
  print('first')
  yield 1
  print('second')
  yield 2
  print('third')
  yield 3
generator_obj = generator_func()
print(isinstance(generator_obj,Iterator))
print(generator_obj)
print(generator_obj.__next__())
print(generator_obj.__next__())
print(generator_obj.__next__())
# True
# <generator object generator_func at 0x000001566F04C7C8>
# first
# 1
# second
# 2
# third
# 3
```

> 函数体内包含yield关键字，该函数执行的结果(返回值generator_obj)为生成器，而该函数称为生成器函数

### 4.5 递归和面向过程编程

#### 4.5.1 递归

#### 4.5.2 面向过程编程(以一个简易计算器为例)

```python
import re
def cal_mini_exp(mini):
  '''乘除计算'''
  if '*' in mini:
    val1,val2 = mini.split('*')
    return str(float(val1)*float(val2))
  elif '/' in mini:
    val1,val2 = mini.split('/')
    return str(float(val1)/float(val2))
def dealwith(exp):
  '''整理表达式内部的符号'''
  return exp.replace('--','+').replace('+-','-').replace('-+','-').replace('++','+')
def calculate(son_exp):
  '''计算没有括号的表达式'''
  son_exp = son_exp.strip('()')
  while 1: # 完成了表达式中乘除法的计算
    ret = re.search('\d+\.?\d*[*/]-?\d+\.?\d*',son_exp)
    if ret:
      mini_exp = ret.group()
      res = cal_mini_exp(mini_exp)
      son_exp = son_exp.replace(mini_exp,res,1)
    else:
      break
  son_exp = dealwith(son_exp)
  res = re.findall('[+-]?\d+\.?\d*',son_exp) 
  sum = 0
  for i in res:
    sum += float(i)
  return str(sum)
def remove_bracket(express):
  """去括号，把内部不再有小括号的表达式匹配出来"""
  while 1:
    ret = re.search('\([^()]+\)',express)
    if ret:
      son_exp = ret.group()
      ret = calculate(son_exp)
      express = express.replace(son_exp,ret,1)
    else:
      break
  return express
def main(express):
  express = express.replace(' ','')
  express = remove_bracket(express)
  ret = calculate(express)
  return ret
def core():
  print('输入计算的内容或输入Q退出'.center(30,'*'))
  while 1:
    # express = '-1 + 2 * ( (60-30 +(-40/5)*(9-2*5/3+7/3*99/4*2998+10*568/14))-(-4*3)/(16-3*2))'
    express = input('please enter:')
    if express == 'Q' or express == 'q':
      break
    elif '/0' in express:
      print('0不能为被除数')
    elif express.count('(') != express.count(')') or '=' in express:
      print('表达式错误，请重新输入')
    else:
      ret = main(express)
      print('计算结果',ret)
      break
  # print(express)
  # print('eval计算结果:',eval(express))
core()
```

### 4.6 内置函数

#### 4.6.1 lambda(可以替代简单函数)

```python
lambda arg1,arg2...argn:expression
# 类似于define
```

- lambda是表达式，而def是语句
- lambda执行的功能有限，是为了编写简单的函数设计的，def用来执行更大的任务
- 保持lambda的简单优雅

#### 4.6.2 映射函数 map

```python
map(func,*iterables)
func:可执行的函数
iterables:迭代器，可迭代的序列
  
from collections import Iterator
m = map(lambda x: x ** 2, [1,2,3,4])
isinstance(m,Iterator) # True
print(next(m)) # 1
print(next(m)) # 4
```

#### 4.6.3 拉链函数：zip

```python
zip(iterables1,iterables2,...iterablesn)
iterables:迭代器
```

#### 4.6.4 过滤函数：filter 

```python
filter (func,*iterables)
func:可执行的函数
iterables:迭代器，可迭代的序列
```

#### 4.6.5 累积函数：reduce

```python
reduce(func,sequence,initial)
func:function
sequence:序列
initial:初始值，可选参数
```

#### 4.6.6 偏函数：partial



#### 4.6.7 其他内置函数



### 4.7 文件操作

#### 4.7.1 打开文件

```python
open(file, [mode = 'r',buffering = None,encoding = None,errors = None,newline = None,closefd = True])
```

* open 函数打开文件或文件描述符并返回文件对象，如果无法打开则抛出OSError错误
* file 参数为字符串或者是字节对象的路径或相对路径（当前工作目录）
* buffering 参数控制着文件的缓冲，如果参数是1或者True
* encoding 参数以什么方式操作文件，该参数只适用于文本模式
* errors 参数指定如何处理编码和解码错误，仅适用于文本模式
* newlines 参数
* closefd 
* mode 为可选参数，用于指定打开文件的模式，默认为‘r’，以只读方式打开文件

| mode | 描述                                                         |
| ---- | ------------------------------------------------------------ |
| 'r'  | 打开文件，以读的方式，该方式为默认方式                       |
| 'w'  | 打开文件，写入文件，如果原文件存在则会被覆盖，如果没有此文件就会创建，前提是该模式下必须保证文件目录的存在 |
| 'x'  | 创建一个新文件并打开以写入，如果文件存在则抛出FileExistsError错误 |
| 'a'  | 以追加的方式打开文件，如果文件存在则从原文件末尾写入，否则会创建文件 |

| mode | 描述                                         |
| ---- | -------------------------------------------- |
| 'b'  | 二进制文件，可以搭配其他模式使用             |
| 't'  | 文本模式，默认                               |
| '+'  | 读/写模式，用于更新                          |
| 'rt' | 文本读模式，默认模式                         |
| 'wt' | 以文本写模式打开，打开前原文件会被清空       |
| 'rb' | 打开文件，以二进制的形式读文件               |
| 'ab' | 以二进制追加模式打开文件                     |
| 'wb' | 以二进制写模式打开文件，打开前原文件会被清空 |
| 'r+' | 以文本读写模式打开文件                       |

#### 4.7.2 文件常用方法

##### f.read和f.write以字符串的形式完成读写操作

```python
f1 = open('t1.txt','w') # 打开文件
f1.write('hello') # 写入字符串
print(f1.write('oldboy')) # 写入字符串 输出6
f1.close() # 关闭文件
```

##### f.read()函数

```python
f1 = open('t1.txt','w')
f1.write('hello')
f1.write('oldboy')
f1.close()
f2 = open('t1.txt','r') 
print(f2.read(5)) # 'hello'
print(f2.read()) # 'oldboy'
f2.close()
```

##### f.readline()和f.readlines()和f.writelines() 顺序读写文件

```python
f1 = open('t1.txt','w')
f1.writelines('fg\nwh\n')
f1.close()
f2 = open('t1.txt','r')
print(f2.readlines())# ['fg\n', 'wh\n']
f2.close()
f3 = open('t1.txt','r')
print(f3.readline())# fg
f3.close()
```

##### 随机读写文件

```

```

| 方法              | 描述                                                         |
| ----------------- | ------------------------------------------------------------ |
| f.read(size)      | 默认一次性读取所有文件，以字符串的形式返回，size规定读取多少字节 |
| f.readline(size)  | 读取文件的整行，包括换行符，如果指定size则返回指定大小的字节数 |
| f.readlines(size) | 读取文件的所有行，以列表的形式返回                           |
| f.write(str)      | 向文件写入指定的个字符串                                     |
| f.writelines(str) | 向文件写入序列的字符串                                       |
| f.tell()          | 返回文件指针的当前位置                                       |

#### 4.7.3 手动挡关闭文件

* 当对文件对象操作完成后，要关闭文件
* 虽然文件被关闭
* 如果文件被一个文件对象占用，那么此文件生成别的对象则无法操作此文件

#### 4.7.4 自动挡关闭文件

```python
with open('t1.txt','w') as f:
  f.write('with真省事')
with open('t1.txt','r') as f:
  print(f.read()) # with真省事
```

## 第五章、模块

### 5.2 常用模块

#### 5.2.1 time

##### 1.时间戳时间:从1970年1月1日的00:00:00开始按秒计算时间的偏移量（以UTC为准，Coordinated Universal Time）

```python
import time
print(time.gmtime(0)[0])
print(time.time())
# 1970 计算时间的开始年份
# 1606200169.2668417 当前时间
```

##### 2.结构化时间：9个整数组成的元祖

```python
import time
print(time.localtime())
# time.struct_time(tm_year=2020, tm_mon=11, tm_mday=24, tm_hour=14, tm_min=46, tm_sec=36, tm_wday=1, tm_yday=329, tm_isdst=0)
```

| 参数                    | 含义             |
| ----------------------- | ---------------- |
| tm_year(年)             | 如2018           |
| tm_mon(月)              | 1~12             |
| tm_moday(日)            | 1~31             |
| tm_hour(时)             | 0~23             |
| tm_min(分)              | 0~59             |
| tm_sec(秒)              | 0~61             |
| tm_wday(星期)           | 0~6（星期一为0） |
| tm_yday(一年中的第几天) | 1~366            |
| tm_isdst(是否是夏令时)  | 0,1或-1          |

###### 格式化时间字符串(format string):经过格式化，将时间输出为对用户友好的时间表现形式

```python
import time
print(time.strftime('%Y-%m-%d %H:%M:%S')) #2020-11-24 14:56:27
```

###### 格式化时间字符

| 字符 | 描述                                        |
| ---- | ------------------------------------------- |
| %Y   | 四位数的年份表示（0000~9999）               |
| %y   | 两位数的年份表示（00~99）                   |
| %m   | 月份（01~12）                               |
| %d   | 月内的一天（01~31）                         |
| %H   | 24小时制小时数（00~23）                     |
| %I   | 12小时制小时数（01~12）                     |
| %M   | 分钟数（00~59）                             |
| %S   | 秒数（00~59）                               |
| %a   | 本地简化星期名称                            |
| %A   | 本地完整星期名称                            |
| %b   | 本地简化月份名称                            |
| %B   | 本地完整月份名称                            |
| %c   | 本地相应的日期表示和时间表示                |
| %j   | 年内的一天（001~366）                       |
| %p   | 本地a.m或p.m的等价符                        |
| %U   | 一年中的星期数（00~53），星期天为星期的开始 |
| %w   | 星期（0~6），星期一为星期的开始             |
| %W   | 一年中的星期数（00~53），星期一为星期的开始 |
| %x   | 本地相应的日期表示                          |
| %X   | 本地相应的时间表示                          |
| %Z   | 当前时区的名称                              |
| %%   | %本身                                       |

###### time 模块常用方法和变量

| 常用方法/变量                | 描述                                     |
| ---------------------------- | ---------------------------------------- |
| time.time()                  | 返回当前的时间戳时间                     |
| time.strptime(string,format) | 根据格式将字符串解析为时间元祖           |
| time.gmtime(seconds=None)    | 将时间转换为时间元祖UTC                  |
| time.mktime(p_tuple)         | 将local时间元祖转换为时间戳时间          |
| time.clock()                 | 将进程启动后的CPU时间作为浮点数返回      |
| time.tzset()                 | 更改本地时区                             |
| time.asctime(p_tuple=None)   | 将时间元祖转换为字符串                   |
| time.altzone                 | UTC和local DST的秒差                     |
| time.timezone                | UTC和本地标准时间之间的秒差              |
| time.tzname                  | 标准时区名称与夏令营时时区名称组成的元祖 |

##### 1.timestamp----struct_time

#### 5.2.2 collections 模块(额外提供了几种数据类型)

##### 1.OrderedDict 有序字典

```python
for k,v in enumerate({'computer':200,'phone':100}):
  print(k,v)
 '''
  # 第一次打印 
  0 computer
  1 phone
  # 第二次打印
  0 phone
  1 computer
 '''
from collections import OrderedDict
od = OrderedDict([('computer',200),('phone',100)]) # 将元祖转化为字典的key和value
for k,v in enumerate(od):
  print(k,v)
'''
0 computer
1 phone
'''
```

```python
# 生成有序字典的另一种方式
from collections import OrderedDict
od = OrderedDict(a=1,b=2,c=3)
for k,v in od.items():
  print(k,v)
od.update(b=4)
print(od)
'''
a 1
b 2
c 3
OrderedDict([('a', 1), ('b', 4), ('c', 3)])
'''
```

##### 2.defaultdict 带默认值的字典

```python
# 一个简单的例子
li = [11,22,33,44,55,66,77,88,99]
d = {}
for i in li:
  if i>=66:
    if 'k1' in d:
      d['k1'].append(i)
    else:
      d['k1'] = [i]
  else:
    if 'k2' in d:
      d['k2'].append(i)
    else:
      d['k2'] = [i]
print(d)
# {'k2': [11, 22, 33, 44, 55], 'k1': [66, 77, 88, 99]} 大于等于66的在k1，其他在k2
```

```python
from collections import defaultdict
default_dic = defaultdict(list)
print(default_dic) # defaultdict(<class 'list'>, {})
default_dic = defaultdict(set) 
print(default_dic) # defaultdict(<class 'set'>, {})
default_dic = defaultdict(tuple)
print(default_dic) # defaultdict(<class 'tuple'>, {})
default_dic = defaultdict(None)
print(default_dic) # defaultdict(None, {})
```

> defaultdict的默认值是callable(指必须是可调用的)或者None这两种类型。因为上例中的字典都为可调用的，所以可以成为带有默认值的字典的默认值。可用callable函数来判断一个对象是否为callable的

```python
print(callable('a')) # False
print(callable(list)) # True
print(callable(tuple)) # True
def foo():
  print('pypnb')
print(callable(foo)) # True
```

```python
from collections import defaultdict
li = [11,22,33,44,55,66,77,88,99,90]
default_dic = defaultdict(list)
for i in li:
  if i>=66:
    default_dic['k1'].append(i)
  else:
    default_dic['k2'].append(i)
print(default_dic)
# defaultdict(<class 'list'>, {'k2': [11, 22, 33, 44, 55], 'k1': [66, 77, 88, 99, 90]})
```

##### 3.namedtuple 命名元祖(类似结构体)

__主要用来生成可以使用名来访问元素的数据对象，通过点的方式取值__

```python
point = (1,2)
x = point[0]
y = point[1]
print(x,y)
# 1 2
```

```python
from collections import namedtuple
point = namedtuple('Point',['x','y']) # 将元祖命名为Point,元祖的两个元素代表x轴和y轴，再把命名好的元祖传递给point
p1 = point(1,2) 
print(p1) # Point(x=1, y=2)
print(p1.x,p1.y) # 1 2
```

```python
from collections import namedtuple
ip_port = namedtuple('id_port',['ip','port'])
p = ip_port('127.0.0.1',8833)
print(p) # id_port(ip='127.0.0.1', port=8833)
print(p.ip,p.port) # 127.0.0.1 8833
```

##### 4.deque 双端队列

__先进先出queue__

```python
import queue
qu = queue.Queue()
print(qu) # <queue.Queue object at 0x00000214F757F8D0>
qu.put(1) # put为队列添加元素
qu.put(2)
qu.put(3)
qu.put('a')
print(qu.qsize()) # 4
print(qu.get()) # 1 get获取元素
print(qu.get()) # 2
```

__deque__

```python
from collections import deque
de = deque()
print(de) # deque([])
print(type(de)) # <class 'collections.deque'>
print(isinstance(de,list)) # False 不是一个队列
de.append(1)
de.insert(0,'a')
de.append(['b','d'])
print(de) # deque(['a', 1, ['b', 'd']])
print(de.index('a')) # 0
de.appendleft('x') 
print(de.popleft()) # x
```

```python
from collections import deque
dp = deque(maxlen=3) # maxlen用来限制双端队列的大小
while 1:
  cmd = input('>>>')
  if cmd not in dp:
    dp.appendleft(cmd)
  print(dp)
"""
>>>25
deque(['25'], maxlen=3)
>>>25
deque(['25'], maxlen=3)
>>>36
deque(['36', '25'], maxlen=3)
>>>357
deque(['357', '36', '25'], maxlen=3)
>>>369
deque(['369', '357', '36'], maxlen=3)
"""
```

| 方法                  | 描述                                                  |
| --------------------- | ----------------------------------------------------- |
| append(x)             | 将x添加到双端队列的右侧                               |
| appendleft(x)         | 将x添加到双端队列的左侧                               |
| clear()               | 清空队列                                              |
| copy()                | 浅拷贝                                                |
| count(x)              | 统计双端队列元素为x的个数                             |
| extend(iterable)      | 将iterable添加到双端队列右侧                          |
| exttendleft(iterable) | 将iterable中的元素反转后，添加到双端队列左侧          |
| index(x,[start,stop]) | 返回双端队列中x的索引位置，可选start和end设置查找范围 |
| insert(i,x)           | 将x插入位置为i的双端队列中                            |
| pop()                 | 从deque的右侧移除一个元素并返回该元素                 |
| popleft()             | 从deque的左侧移除一个元素并返回该元素                 |
| remove(value)         | 从deque的左侧开始删除第一次出现的value                |
| reverse()             | 原地反转deque                                         |
| rotate(n)             | 向右反转deque n步。如果n是负数，则向左反转            |
| maxlen                | 设置deque的大小                                       |

```python
from collections import deque 
dq = deque()
dq.extend([1,2,3,4,5])
print(dq) # deque([1, 2, 3, 4, 5])
dq.rotate(1)
print(dq) # deque([5, 1, 2, 3, 4])
dq.rotate(-1)
print(dq) # deque([1, 2, 3, 4, 5])
dq.rotate(3)
print(dq) # deque([3, 4, 5, 1, 2])
```

##### 5.Counter 计数器

__返回值为一个字典，key为元素，value为次数__

```python
from collections import Counter
print(Counter([1,2,3,3,1,1,2,2])) # Counter({1: 3, 2: 3, 3: 2})
print(Counter('dawdfsefsegdtht')) # Counter({'d': 3, 'f': 2, 's': 2, 'e': 2, 't': 2, 'a': 1, 'w': 1, 'g': 1, 'h': 1})
```

| 方法             | 描述                                  |
| ---------------- | ------------------------------------- |
| most_common([n]) | 返回n的最多计数次数的列表，按从多到少 |
| copy()           | 浅拷贝                                |
| +                | 添加两个计数器                        |
| -                | 差集，只保留正数计数的元素            |
| &                | 交集                                  |
| \|               | 并集                                  |

#### 5.2.3 funtools 模块

##### 1.functools.update_wrapper

```python

```



##### 2.fundtools.wraps

#### 5.2.4 random 模块

| 方法                                  | 描述                                  |
| ------------------------------------- | ------------------------------------- |
| random.random()                       | 随机返回大于0小于1之间的浮点数        |
| random.uniform(a,b)                   | 随机返回指定范围内的浮点数            |
| random.randint(a,b)                   | 随机返回指定范围内的整数              |
| random.randrange(start,stop,[step=1]) | 随机返回指定范围内的整数，step默认为1 |
| random.choice(seq)                    | 随机返回序列内的元素                  |
| random.sample                         | 随机返回序列内的任意k个元素的组合     |
| random.shuffle(seq)                   | 打乱序列内元素的次序                  |

```python
import random
print(random.random())
print(random.uniform(1,100))
print(random.randint(1,100))
print(random.randrange(1,100,3))
print(random.choice([1,2,3,4]))
print(random.sample([1,2,3,4],3))
seq=[1,2,3,4]
random.shuffle(seq)
print(seq)
# 0.30674144456915076
# 3.4136078875593983
# 36
# 31
# 2
# [1, 3, 2]
# [3, 4, 2, 1]
```

###### 生成随机验证码

```python
import random
def ver(v):
  code=''
  for i in range(v): # v次循环，生成v位验证码
    num = random.randint(0,9)
    alf_big = chr(random.randint(65,90)) # 随机整数
    alf_small = chr(random.randint(97,122)) # 随机大写的A-Z
    add = random.choice([num,alf_big,alf_small]) # 随机小写的 a-z
    code = ''.join([code,str(add)])
  return code
print(ver(8))
```

#### 5.2.5 序列化模块

__将数据结构或者某种状态转换为某种格式，称为序列化，转换过程称为序列化(pickling)的过程。而将这种具有某种格式的数据还原为原数据称为反序列化(unpickling)__

> 1.pickle模块
>
> pickle模块实现了用于序列化和反序列化Python对象的二进制协议，pickle模块的picking是将Python对象转换为字节流的过程，unpickling则是反向的操作
>
> | 方法                  | 描述                         |
> | --------------------- | ---------------------------- |
> | pickle.dumps(obj)     | 将obj序列化                  |
> | pickle.loads(obj)     | 反序列化obj                  |
> | pickle.dump(obj,file) | 将obj序列化后写入file中      |
> | pickle.load(file_obj) | 将文件中的序列化对象反序列化 |
>
> ```python
> import pickle
> dic = {'a': 'b','c':'d'}
> p = pickle.dumps(dic)
> print(p) # b'\x80\x03}q\x00(X\x01\x00\x00\x00aq\x01X\x01\x00\x00\x00bq\x02X\x01\x00\x00\x00cq\x03X\x01\x00\x00\x00dq\x04u.'
> d = pickle.loads(p)
> print(d) # {'a': 'b', 'c': 'd'}
> ```

#### 5.2.6 re

__正则表达式：__

| 元字符 | 匹配内容                       |
| ------ | ------------------------------ |
| .      | 匹配除换行符以外的任意字符     |
| \w     | 匹配字母或数字或下划线         |
| \s     | 匹配任意的空白符               |
| \d     | 匹配数字                       |
| \n     | 匹配一个换行符                 |
| \t     | 匹配一个制表符                 |
| \b     | 匹配一个单词的边界             |
| ^      | 匹配一个字符串的开始           |
| $      | 匹配字符串的结尾               |
| \W     | 匹配非字母或数字或下划线       |
| \D     | 匹配非数字                     |
| \S     | 匹配非空白符                   |
| a\|b   | 匹配字符a或字符b               |
| ()     | 匹配括号内的表达式             |
| [...]  | 匹配字符组中的字符             |
| [^...] | 匹配除了字符组中字符的所有字符 |

| 量词  | 用法          |
| ----- | ------------- |
| *     | 重复0次或多次 |
| +     | 重复1次或多次 |
| ？    | 重复0次或1次  |
| {n}   | 重复0次或1次  |
| {n,}  | 重复n次或多次 |
| {n,m} | 重复n到m次    |

__re模块中的常用方法__

| 方法                        | 描述                                                         |
| --------------------------- | ------------------------------------------------------------ |
| re.findall(pattern,string)  | 以列表的方式返回所有满足匹配条件的结果                       |
| re.search(pattern,string)   | 扫描整个字符串并返回第一个成功匹配的项                       |
| re.match(pattern,string)    | 从字符串开始匹配，成功则返回匹配对象                         |
| re.split(pattern,string)    | 按照匹配到的子串将字符串分解，并以列表的形式返回             |
| re.sub(pattern,repl,string) | 用于替换repl中的匹配项，repl可以是字符串，也可以是函数       |
| re.compile(pattern)         | 用于编译正则表达式并生成一个正则表达式对象，供match和search这两个函数使用 |
| re.finditer(pattern,string) | 返回一个存放匹配结果的迭代器                                 |

```python
import re
# \d 匹配一位数数字 \d+ 匹配多位数字
res1 = re.findall(r'\d+','123+223-333,22,11') 
print(res1) # ['123', '223', '333', '22', '11']
# 匹配标签
res2 = re.search("<(?P<tag_name>\w+)>\w+</(?P=tag_name)>","<h1>hello</h1>") 
print(res2) # <re.Match object; span=(0, 14), match='<h1>hello</h1>'>
# group 获取到匹配到的所有结果
print(res2.group()) # <h1>hello</h1>
print(res2.group('tag_name')) # h1
# 以列表的形式返回所有的可能结果
res3 = re.findall(r'[0-9]','123,abcd234')
print(res3) # ['1', '2', '3', '2', '3', '4']
```

```python
import re
res4 = re.match('a','abc')
print(res4.group()) # a
res5 = re.match('b,','abc')
print(res5) # None
res6 = re.search('b','abc')
print(res6.group()) # b`
```

__search方法搜索整个字符串，直至找到第一个匹配结果返回，如无匹配结果，返回None。而match方法则从字符串开始匹配，符合条件则将结果返回，否则返回None__

```python
import re
res1 = re.findall(r'www.(baidu|oldboy).com','www.oldboy.com')
print(res1) # ['oldboy']
res2 = re.findall(r'www.(?:baidu|oldboy).com','www.oldboy.com') # ?:代表取消权限，获得真正的匹配结果
print(res2) # ['www.oldboy.com']
```

```python
import re
res3 = re.split('[a]','abcd') # 将字符串以a分割
print(res3) # ['', 'bcd']
res4 = re.split('[ab]','abcd') # 将字符串以a分割得到一个结果，将这个结果再以b分割，将结果返回
print(res4) # ['', '', 'cd']
```

```python
import re
res5 = re.split('\d+','a1b2c3')
print(res5) # ['a', 'b', 'c', '']
res6 = re.split('(\d+)','a1b2c3')
print(res6) # ['a', '1', 'b', '2', 'c', '3', '']
```

__re.split在书写正则规则时，加括号和不加括号是有区别的。不加括号时，返回结果不包含匹配项，只返回分割后的结果；有括号时，返回的结果包含匹配项__

```python
import re
print(re.split('[;,]','a,b  c')) # ['a', 'b  c']
print('a;b  c'.split(',')) # ['a;b  c']
```

__相对于split，re.split可以有多个分割符__

#### 5.2.7 os

| 方法                             | 描述                                                 |
| -------------------------------- | ---------------------------------------------------- |
| os.makedirs('dirname1\dirname2') | 创建多级目录                                         |
| os.removedirs('dirname')         | 若为空目录，则删除，并递归到上一层，若也为空，则删除 |
| os.mkdir('dirname')              | 创建单级目录                                         |
| os.rmdir('dirname')              | 若该目录为空，则删除                                 |
| os.listdir('dirname')            | 以列表的形式返回指定目录下的目录和文件               |
| os.remove(file)                  | 指定文件存在则删除                                   |
| os.rename('old','new')           | 文件重命名                                           |
| os.system('bash command')        | 运行平台的Shell命令                                  |
| os.popen('bash command').read()  | 运行平台的Shell命令并返回执行结果                    |
| os.getcwd()                      | 获取当前脚本的工作目录                               |
| os.chdir('dirname')              | 改变当前脚本工作目录，如Shell平台的cd命令            |
| os.stat('dirname')               | 获取文件、目录信息                                   |
| os.environ                       | 获取系统环境变量                                     |

### 5.3 模块探索

#### 1.自定义模块的创建

__在Python中，一个py文件就是一个模块。模块名的命名要遵循变量的命名规范，避开关键字和与其他模块名一致的名字，比如自己定义的模块名不要写成def.py或者time.py__

```python
# a.py
x = 1
y = [2,3]
def foo(x):
  print('b.foo prints',x)
```

__a.py为一个模块。当这个模块被别的模块调用时，变量x，y和foo都会成为模块a的属性，也就是说位于模块a的全局作用域的变量、函数名、类名都将会成为模块a的属性，在别的模块通过module.attribute方式被调用__

#### 2.模块的导入

```python
import module_name
```

```python
import a
print(a.x,a.y,a.foo) # 1 [2, 3] <function foo at 0x000001D6D14BA1E0>
```

__from语句可以引用一个模块中的一个或几个属性__

```python
from a import foo
print(foo)
```

#### 3.from语句的弊端

#### 4.模块导入规范

- 内置模块在最上部
- 第三方模块在中间
- 自定义模块放在最下

#### 5.模块倒入只发生一次

#### 6.模块重载

__reload函数强制使模块重新执行一次导入过程__

```python
from importlib import reload
reload(module_obj)
```

#### 7.object.attribute

#### 8.模块的闭环导入

__避开模块的相互导入__

#### 9.让模块如脚本一样运行

```python
# a.py
def login(user,pwd):
  print(user,pwd)
if __name__ == "__main__": # 表示模块在执行自己代码时，就执行login函数。否则要被别的模块导入时不执行
  login('oldboy','666')
```

#### 10.模块导入都发生了什么

- 找到导入的模块文件。python解析到import语句时，会自动搜索路径，并找到这个模块，添加到sys.modules字典中。
- 编译成字节码
- 执行字节码

sys模块

| 方法                     | 描述                         |
| ------------------------ | ---------------------------- |
| sys.argv                 | 获取python命令行参数         |
| sys.version              | 获取python解释器版本信息     |
| sys.platform             | 获取平台信息                 |
| sys.modules              | 维护python运行中所有的模块   |
| sys.getdefaultencoding() | 返回解释器当前的默认字符编码 |
| sys.stdin                | 标准输入                     |
| sys.stdout               | 标准输出                     |

| 方法                    | 描述                               |
| ----------------------- | ---------------------------------- |
| sys.stderr              | 错误输出                           |
| sys.getrecursionlimit() | 返回递归限制的当前值               |
| sys.setrecursionlimit() | 设置递归的最大深度                 |
| sys.exit(n)             | 引发SystemExit异常来实现退出python |
| sys.path                | 维护python搜索模块的路径           |

```python
# a.py
import sys
def login(user,pwd):
  print(user,pwd)
if __name__ == "__main__": # 表示模块在执行自己代码时，就执行login函数。否则要被别的模块导入时不执行
  login('oldboy','666')
print(sys.version) # 3.7.0 (default, Jun 28 2018, 08:04:48) [MSC v.1912 64 bit (AMD64)]
print(sys.platform) # win32
print(sys.getdefaultencoding()) # utf-8
```

#### 11.模块搜索路径——sys.path

```python
import sys
import os
import a
print(sys.path) 
'''
['d:\\pyex\\pyex1', 'D:\\anaconda\\conda\\python37.zip', 'D:\\anaconda\\conda\\DLLs', 'D:\\anaconda\\conda\\lib', 'D:\\anaconda\\conda', 'D:\\anaconda\\conda\\lib\\site-packages', 'D:\\anaconda\\conda\\lib\\site-packages\\win32', 'D:\\anaconda\\conda\\lib\\site-packages\\win32\\lib', 'D:\\anaconda\\conda\\lib\\site-packages\\Pythonwin']
'''
print(os) # <module 'os' from 'D:\\anaconda\\conda\\lib\\os.py'>
print(a) # <module 'a' from 'd:\\pyex\\pyex1\\a.py'>
```

### 5.4 模块与包

#### 1.包的导入

__如果想导入test\dir\a.py中的x属性，那么使用import导入时，列出路径名，路径分隔符用点号分割__

```python
import test.dir1.a
from test.dir1.a import x
```

#### 2.包的初始化

> 包导入路径中的每个目录都要有____init.py____文件

## 第六章、面向对象(Object-Oriented Programming,OOP)

### 6.1 类与对象

#### 6.1.1 类的创建(class)

```python
class Person:
  role = "人"
print(Person.role) 
# 人
```

#### 6.1.2 实例化

##### 1.类：一类事物的统称

##### 2.对象：由上面的类”生产“出的具体事物

##### 3.实例化：类名加括号“生产”对象的过程

##### 4.实例：实例化后的对象。

```python
# 以书中的盖伦为例
class Person:
  role = "人"
obj = Person()
obj.name = 'garen'
obj.speed = 340
obj.attack = 64
obj.hp = 616
print(obj.__dict__) # 对象通过自带的“dict”属性，椅子垫形式存储其属性
'''
{'name':'garen','hp':616,'attack':64,'speed':340}
'''
# 改变
class Person:
  role = "人"
  def __init__(self,name,speed,attack,hp):
    self.name = name
    self.speed = speed
    self.attack = attack
    self.hp = hp
obj = Person('garen',340,64,616)
print(obj)
print(obj.__dict__)
"""
<__main__.Person object at 0x0000028EB0FC07B8>
{'name': 'garen', 'speed': 340, 'attack': 64, 'hp': 616}
"""
# __init__方法的作用是：在实例化对象时__init__函数自动执行，负责具体的实例化过程
```

__方法：属于某个类的函数__

__init:实例化方法__

```python
class Animal:
  def __init__(self,name): # 临时称这个对象为self
    self.name = name
obj1 = Animal('gnar')
obj2 = Animal('nasus')
print(obj1.name) # gnar
print(obj2.name) # nasus
```



```python
class Animal:
  def __init__(self,name,speed,attack,hp):
    self.name = name
    self.speed = speed
    self.attack = attack
    self.hp = hp
  def passive_skill(self):
    '''对象的被动技能'''
    self.hp += 100
obj1 = Animal('gnar',340,64,616)
print(obj1.hp) # 616
obj1.passive_skill()
print(obj1.hp) # 716
```

```python
# 两个对象的交互
class Person:
  role = '人'
  def __init__(self,name,speed,attack,hp):
    self.name = name
    self.speed = speed
    self.attack = attack
    self.hp = hp
  def passive_skill(self):
    self += 100
  def q(self,enemy):
    '''对象的q技能'''
    enemy.hp -= self.attack
    print('%s中了%s的q技能，受到了%s点伤害'%(enemy.name,self.name,self.attack))
garen = Person('garen',340,64,616)
riven = Person('riven',340,76,558)
garen.q(riven) # riven中了garen的q技能，受到了64点伤害
riven.q(garen) # garen中了riven的q技能，受到了76点伤害
print(garen.hp) # 540
print(riven.hp) # 494
```

```python
class Person:
  role = '人'
  def __init__(self,name,speed,attack,hp):
    self.name = name
    self.speed = speed
    self.attack = attack
    self.hp = hp
  def passive_skill(self):
    self += 100
  def q(self,enemy):
    '''对象的q技能'''
    enemy.hp -= self.attack
    print('%s中了%s的q技能，受到了%s点伤害'%(enemy.name,self.name,self.attack))
garen = Person('garen',340,64,616)
riven = Person('riven',340,76,558)
garen.q(riven) # riven中了garen的q技能，受到了64点伤害
riven.q(garen) # garen中了riven的q技能，受到了76点伤害
print(garen.hp) # 540
print(riven.hp) # 494
class Animal:
  role = '动物'
  def __init__(self,name,speed,attack,hp):
    self.name = name
    self.speed = speed
    self.attack = attack
    self.hp = hp
  def passive_skill(self):
    self.hp += 25
  def w(self,enemy):
    enemy.hp -= enemy.attack
    print('%s中了%s的w技能，受到%s点伤害'%(enemy.name,self.name,self.attack))
gnar = Animal('gnar',340,70,600)
garen.q(gnar) # gnar中了garen的q技能，受到了64点伤害
gnar.w(garen) # garen中了gnar的w技能，受到70点伤害
gnar.passive_skill()
gnar.w(garen) # garen中了gnar的w技能，受到70点伤害
```

### 6.2 继承

#### 6.2.1 命名空间

```python
class Plants:
  role = '植物'
  def __init__(self,name):
    self.name = name
  def passive_skill(self):
    print(self)
obj1 = Plants('maokai')
obj2 = Plants('zyra')
print(id(obj1)) # 2227759085104
print(id(obj2)) # 2227759085888
print(id(Plants)) # 2227726419384
print('obj1.__dict__:',obj1.__dict__)
print('obj2.__dict__:',obj2.__dict__)
print('Plants.__dict__:',Plants.__dict__)
'''
obj1.__dict__: {'name': 'maokai'}
obj2.__dict__: {'name': 'zyra'}
Plants.__dict__: {'__module__': '__main__', 'role': '植物', '__init__': <function Plants.__init__ at 0x00000206B0B5A1E0>, 'passive_skill': <function Plants.passive_skill at 0x00000206B0C82378>, '__dict__': <attribute '__dict__' of 'Plants' objects>, '__weakref__': <attribute '__weakref__' of 'Plants' objects>, '__doc__': None}
'''
```

- 类的数据属性是共享给所有对象的
- 类的方法是绑定到所有对象的
- 每个实例(对象)自己的数据属性存储在自己的命名空间中

#### 6.2.2 单继承

```python
class Garne_Parent:
  mom_deposit = 100
  def __init__(self,name,money):
    self.name = name
    self.money = money
  def deposit(self):
    self.money += self.mom_deposit
garen = Garne_Parent('garen',100)
print(garen.money) # 100
garen.deposit() # 去找妈妈借钱
print(garen.money) # 200
```

__父类：在Python中，当前类可以继承一个或多个父类，父类又称为基类或超类__

__子类：当前类，可以成为子类或派生类__

```python
class Garen_Grandparent:
  grand_pension = 30
  case_dough = 10
  def __init__(self,name,money):
    self.name = name
    self.money = money
  def deposit(self):
    self.money += self.grand_pension
  def gf_case_dough(self):
    self.money += self.case_dough

class Garen_Parent(Garen_Grandparent):
  mom_deposit = 100
  def __init__(self,name,money):
    self.name = name
    self.money = money 
  def deposit(self):
    self.money += self.mom_deposit
garen = Garen_Parent('garin',100)
garen.deposit() # 借妈妈的存款
print(garen.money) # 200
garen.gf_case_dough() # 借爷爷的私房钱
print(garen.money) # 210
```

#### 6.2.3 多继承

#### 6.2.4 接口类

> 1.程序归一化思想
>
> ```python
> class Alipay:
>   '''支付宝支付'''
>   def pay(self,money):
>     print('支付宝支付了%s元'%money)
> class Applepay:
>   '''苹果支付'''
>   def pay(self,money):
>     print('苹果支付了%s元'%money)
> class Wechatpay:
>   '''微信支付'''
>   def pay(self,money):
>     print('微信支付了%s元'%money)
> def pay(payment,money):
>   '''
>   支付函数
>   payment:支付对象
>   money:支付金额
>   '''
>   payment.pay(money)
> ali = Alipay()
> apple = Applepay()
> wechat = Wechatpay()
> pay(ali,200) # 支付宝支付了200元
> pay(apple,200) # 苹果支付了200元
> pay(wechat,200) # 微信支付了200元
> ```
>
> 2.ABC模块实现接口归一化
>
> 3.抽象和继承
>
> 4.依赖倒置原则

#### 6.2.5 抽象类

#### 6.2.6 新式类和经典类

#### 6.2.7 C3算法

#### 6.2.8 issubclass和isinstance

`issubclass`__判断当前对象(第一个参数)是否是类(第二个参数)的派生类__

### 6.3 组合(在一个类中以另外一个类的对象作为数据属性)

```python
class Course(object):
  def __init__(self,name,cycle):
    self.name = name
    self.cycle = cycle

class Student(object):
  def __init__(self,name,sex):
    self.name = name
    self.sex = sex
class Teacher(object):
  def __init__(self,name,student,course):
    self.name = name
    self.student = student
    self.course = course

t1 = Teacher('王老师',Student('李四','男'),Course('python','6'))
t2 = Teacher('王老师',Student('二妞','女'),Course('linux','6'))
print(t1.course.name,t1.course.cycle) # python 6
print(t2.student.name,t2.student.sex) # 二妞 女
```

### 6.4 封装

> 1.类的私有属性
>
> 在类中，变量名前加下划线，表示该变量只能在内部使用
>
> ```python
> class People:
>   role = '人'
>   __income = 20000
> maggie = People()
> print(maggie.role) # 人
> print(maggie.__income) # AttributeError: 'People' object has no attribute '__income'
> ```
>
> 2.对象的私有属性
>
> 属性名前加双下划綫
>
> 3.类的私有方法
>
> ```python
> class People:
>   __income = 20000
>   def __init__(self,name,age,sex):
>     self.name = name
>     self.__age = age
>     self.sex = sex
>   def information(self):
>     print(self.name)
>     print(self.__age)
> maggie = People('maggie',18,'女')
> maggie.information() 
> # maggie
> # 18
> ```
>
> 4.封装的应用（注册）
>
> ```python
> import hashlib
> class Register:
>   __salt = 'c2d8f4a'
>   def __init__(self,name,pwd):
>     self.name = name
>     self.pwd = pwd
>     self.__pwd = self.name + '%s'%pwd # 将用户名和密码拼接
>   def __hash_pwd(self,salt):
>     return hashlib.md5((self.__pwd + self.pwd + salt).encode('UTF-8')).hexdigest()
>   def set_pwd(self):
>     return self.__hash_pwd(self.__salt)
> wang = Register('wang','123')
> print(wang.set_pwd()) # 275211793c3da5f9cbcbb357aa178991
> print(wang.pwd) # 123
> # 
> ```

__封装的优点__

- 将变化隔离
- 便于使用
- 提高复用性
- 提高安全性

__封装的原则__

- 将不需要对外提供的内容都隐藏起来
- 把属性都隐藏，提供公共方法对其访问

### 6.5 多态

 

### 6.6 装饰器函数

### 6.7 反射

__反射：当程序在运行时可以访问、检测和修改自身状态或者行为的一种能力__

> 1.getattr
>
> 第一个参数为类名，第二个参数是获取的输入
>
> ```python
> class Dog:
>   name = '京巴'
>   age = 2
>   color = 'white'
> while 1:
>   choose = input('>>>:').strip()
>   print(getattr(Dog,choose))
> '''
> >>>:name
> 京巴
> >>>:age
> 2
> '''
> ```
>
> 2.hasattr
>
> 判断对象是否有某个方法或者属性
>
> ```python
> class Dog:
>   name = '京巴'
>   age = 2
>   color = 'white'
> while 1:
>   choose = input('>>>:').strip()
>   if hasattr(Dog,choose):
>     print(getattr(Dog,choose))
>   else:
>     print("Dog has no attribute '%s'" %choose)
> '''
> >>>:name
> 京巴
> >>>:age
> 2
> >>>:dawd
> Dog has no attribute 'dawd'
> >>>:
> '''
> ```
>
> 3.setattr
>
> setattr(obj, str, attribute) 以字符串的形式为obj设置一个属性或者方法
>
> 设置属性
>
> ```python
> class Dog:
>   name = '京巴'
> obj = Dog()
> setattr(obj,'age',2)
> print(obj.__dict__) # {'age': 2}
> ```
>
> 修改属性
>
> ```python
> class Dog:
>   name = '京巴'
> obj = Dog()
> setattr(obj,'age',2)
> print(obj.__dict__) # {'age': 2} 
> setattr(obj,'age',3)
> print(obj.__dict__) # {'age': 3}
> ```
>
> 设置方法
>
> ```python
> class Dog:
>   name = '京巴'
> obj = Dog()
> def guard(self,x,y):
>   print(x,y)
> setattr(obj,'guard',guard)
> print(obj.__dict__) # {'guard': <function guard at 0x000001628518C1E0>}
> obj.guard(obj,1,2) # 1 2
> ```
>
> 4.delattr
>
> 删除属性
>
> ```python
> class Dog:
>   name = '京巴'
> obj = Dog()
> setattr(obj,'age',2)
> print(obj.__dict__) # {'age': 2}
> delattr(obj,'age')
> print(obj.__dict__) #{}
> ```

### 6.8 函数vs方法

- 函数是显式传递数据的
- 函数跟对象无关
- 方法可以操作类内部的数据
- 方法和对象是关联的
- 方法的数据是显式传递的

### 6.9 类中的内置方法

#### 6.9.1 对象的诞生与死亡

> 1.元类:type
>
> 
>
> 2.构造方法:____new____
>
> 3.实例化方法：____init____
>
> 4.析构方法：____del____

#### 6.9.2 ____len____

#### 6.9.3 ____eq____

#### 6.9.4 字符串格式化三剑客

> 1.三剑客之____format____
>
> 2.三剑客之____str____
>
> 3.三剑客之____repr____

#### 6.9.5 item系列

