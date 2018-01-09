Python基础-常用内建函数
字符串内建函数
在字符串类型中，还包含一些其他方便我们处理数据的内建函数，
注意：某些函数可能返回结果与原字符串不同，但并不是修改了本身字符串，只是返回了一个新的而已

大小写转换函数
string.lower()：字母大写转换为小写
>>> mystr = 'aBc,bDc'
>>> mystr.lower()
'abc,bdc'
string.upper()：字母小写转换成大写
>>> mystr = 'aBc,bDc'
>>> mystr.upper()
'ABC,BDC'
string.swapcase()：字母大写转换小写，小写转换成大写
>>> mystr = 'aBc,bDc'
>>> mystr.swapcase()
'AbC,BdC'
string.title()：将每个单词首字母大写，将句中字符变为小写
>>> mystr = 'aBc,bDc'
>>> mystr.title()
'Abc,Bdc'
string.capitalize()：将第一个字母大写，将句中字符变为小写
>>> mystr = 'aBc,bDc'
>>> mystr.capitalize()
'Abc,bdc'
搜索函数
tring.find(str,[start=0,stop=len(string)])：计算string中出现str的第一个字母的索引，如果没有出现，则返回-1
>>> mystr = 'aabbcc'
>>> mystr.find('a')
0
>>> mystr.find('1')
-1
string.index(str ,[start=0,stop=len(string)])：计算string中出现str的第一个字母的索引，如果没有出现，引发异常
>>> mystr = 'aabbcc'
>>> mystr.index('b')
2
>>> mystr.index('d')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: substring not found
string.count(str ,[start=0,stop=len(string)])：计算str在string中出现的次数
>>> mystr = 'aabbcc'
>>> mystr.count('a')
2
>>> mystr.count('d')
0
string.endswith(chr,[start=0,stop=len(string)])：检查string是否以chr结尾，如果是，返回True，反之，返回False
>>> mystr = 'aabbcc'
>>> mystr.endswith('cc')
True
>>> mystr.endswith('aa')
False
替换函数
string.replace(str1, str2,[num= string.count(str1)])：将str1替换为str2, num为替换次数，默认次数为str1出现的次数
>>> mystr = 'aabbcc'
>>> mystr.replace('a','*')
'**bbcc'
>>> mystr = 'aabbcc'
>>> mystr.replace('a','*',1)
'*abbcc'
string.strip(chr)：在string的开头和结尾删除chr，当chr为空时，默认删除空白符
>>> mystr = ' aabbcc '
>>> mystr.strip()
'aabbcc'
>>> mystr = '**abc**'
>>> mystr.strip('*')
'abc'
string.rstrip(chr)：删除string字符串末尾的空白符或给定字符
>>> mystr = ' aabbcc '
>>> mystr.rstrip()
' aabbcc'
分割，组合函数
string.split(chr,num=string.count(str))：以chr为分割符将string字符串分割，返回分割后的结果保存在列表中；如果指定num参数，则只分割前num次
>>> mystr = 'a:b:c'
>>> mystr.split(':')
['a', 'b', 'c']
chr.join(str.[list,tuple])：以chr作为连接符，拼接字符串序列
>>> ''.join(['a','b','c'])
'abc'
>>> '*'.join(['a','b','c'])
'a*b*c'
判断函数
string.isdigit()：如果string只包含数字，则返回True，否则返回False
>>> mystr = '123'
>>> mystr.isdigit()
True
string.islower()：字符串中的字母全为小写则返回True，否则返回False
>>> mystr = 'abc'
>>> mystr.islower()
True
string.isupper()：字符串中的字母全为大写则返回True，否则返回False
>>> mystr = 'ABC'
>>> mystr.isupper()
True
string.isspace()：字符串中只包含空白字符，返回True，否则返回False
>>> mystr = '   '
>>> mystr.isspace()
True
列表内建函数
list.append(obj)：在列表尾部追加obj
>>> mylist = [1,2,3]
>>> mylist.append('abc')
>>> mylist
[1, 2, 3, 'abc']
list.count()：返回一个对象在列表中出现的次数
>>> mylist = [1,2,3]
>>> mylist.count(1)
1
list.extend(seq)：把序列seq中的内容分别提取并加入到列表中
>>> mylist = [1,2,3]
>>> mylist.extend('abc')
>>> mylist
[1, 2, 3, 'a', 'b', 'c']
list.insert(index,obj)：在索引index的位置插入obj，原位置的内容向后移动
>>> mylist = [1,2,3]
>>> mylist.insert(1,'a')
>>> mylist
[1, 'a', 2, 3]
list.pop(index)：删除并返回index位置的数据对象，默认是最后一个对象
>>> mylist = [1,2,3]
>>> mylist.pop()
3
>>> mylist
[1, 2]
list.reverse()：反转列表
>>> mylist = [1,2,3]
>>> mylist.reverse()
>>> mylist
[3, 2, 1]
元组内建函数
tuple.index(obj,beg=0,end=len(string))：检查obj是否包含在tuple中，不存在会报错
>>> mytuple = (1,2,3)
>>> mytuple.index('a')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: tuple.index(x): x not in tuple
>>> mytuple.index(1)
0
tuple.count(obj)：返回obj在元组中出现的次数
>>> mytuple = (1,2,3)
>>> mytuple.count(1)
1
系统内建函数
reversed(seq)：接受一个序列作为参数，返回一个以逆序访问的迭代器
>>> mytuple = (1,2,3)
>>> for var in reversed(mytuple):
...     print(var)
...
3
2
1
sorted(iter,key=None,reverse=False)：接受一个可迭代对象作为参数，返回一个有序的列表，可选参数是一个排序方式
>>> mytuple = (3,5,7,2,9)
>>> sorted(mytuple)
[2, 3, 5, 7, 9]
>>> mylist = ['aa','bbb','c']
>>> def cmp(x):
...     return len(x)
...
>>> sorted(mylist,key=cmp)
['c', 'aa', 'bbb']
sum(seq,init=0)：返回seq的总和
>>> mylist = [1,2,3,4,5]
>>> sum(mylist)
15
zip(it0,it1,..itN)：返回一个zip数据类型，将其中序列相同位置的值组成一个元组，以短板结束
>>> a = [1,2,3]
>>> b = ['a','b','c','d']
>>> for var in zip(a,b):
...     print(var)
...
(1, 'a')
(2, 'b')
(3, 'c')
map(func,seq)：map函数第一个参数可以是一个函数对象，第二个是一个序列，函数将作用于序列中的每个值，返回一个map数据类型
>>> def func(x):
...     return x*x
...
>>> mylist = [1,2,3]
>>> for var in map(func,mylist):
...     print(var)
...

reduce(func,seq)：该函数来自于functools标准库，把一个函数作用在一个序列[x1, x2, x3…]上，这个函数必须接收两个参数，他会把结果继续和序列的下一个元素做累积计算

>>> from functools import reduce
>>> def myadd(x,y):
...     return x+y
...
>>> mylist = [1,2,3,4,5]
>>> reduce(myadd,mylist)
15
转载请注明原文地址

# Python3.x # 基础
Python基础-字典集合数据类型
文章目录  站点概览
1. 字符串内建函数
1.1. 大小写转换函数
1.2. 搜索函数
1.3. 替换函数
1.4. 分割，组合函数
1.5. 判断函数
2. 列表内建函数
3. 元组内建函数
4. 系统内建函数
© 2018  渔夫
由 Hexo 强力驱动 | 主题 — NexT.Mist v5.1.4
