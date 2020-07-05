# python

## 命令

### 基础

1.输入语句

```python
print('hello',sep=' ',end='/n',file=sys.stdot,flush=False)
```

sep:分隔符

end:结束时执行

file:文件输出的位置

2.输入语句

```python
password = input('请输入您的银行卡密码:')
print(password)
```

变量保存的结果都是字符串

进制

```python
#以0b开头的数是二进制   bin()转化成二进制
默认打印十进制
以0o开头是八进制，python2中以零开头也是八进制  oct()
以0x开头是十六进制   hex()
```

数据类型的转换

```python
转换成int  int()  print(x,16)十六进制
转换成float float()
转换成str  str()
转换成bool(数字一或零存储)  bool()  数字除了0都是True 字符串只有''是False  None是False []是False ()是False  {}是False set()是False
```

运算符

```ptyhon
算数运算符 + — * / ** //整除（向下取整）   %取余
```

```python
赋值运算符  m,n = 3,5  q,*w,e=1,2,3,1,4,56
```

```python
比较运算符  不等于 （'a' == 97）
```

```python
 逻辑运算符	 and  or  not 短路 andfalse是不执行后面的语句，都是true取最后一个 ortrue不执行 
```

```python
位运算符
按位异或：相同为0，不同为1   ^
按位或：只要有一个为1，就为1  |
按位与：同1则为1，否则为0   &
按位左移   <<
按位右移   >>
```

运算符优先级

```python
运算符           描述
**            指数
~+-           按位翻转 正负号
*/ % //       乘， 除，取模，取整除
+-            加减
>> <<         右移，左移
&             按位与
^ |           位运算符
<= < > >=     比较运算符
<> == !=      等于运算符
= %= /= //= -= += *= **= 赋值运算符
is is not     身份运算符
in  not in    成员运算符
not>and>or    逻辑运算符
```

逻辑运算符规则

```python
逻辑与运算
	#只要有一个运算数是False,结果就是False;只有所有的运算数都是True，结果才是True
    #短路：只要遇到了False，就停止，不在继续执行了
    #取值：取第一个为False，如果所有的运算数都是True,取最后一个运算数
逻辑或运算
	#只要有一个运算数是True,结果就是True;只有所有的运算数都是False，结果才是False
    #短路：只要遇到了True，就停止，不在继续执行了
    #取值：取第一个为True，如果所有的运算数都是False,取最后一个运算数
```

判断语句

```python
import  random
player =int(input('请输出石头（0），剪刀（1），布（2）:'))
computer = random.randint(0,2)
if (player )== 0:
    print('你出的是','石头')
elif  (player )== 1:
    print('你出的是','剪刀')
elif  (player ) == 2  or  computer == 2:
    print('你出的是','布')
else:
    print('输入错误')
if (computer)== 0:
    print('电脑出的是','石头')
elif  (computer) == 1:
    print('电脑出的是','剪刀')
elif  (computer) == 2:
    print('电脑出的是','布')
else:
    print('输入错误')
if (player == 0 and computer == 1) or (player == 1 and computer == 2) or (player == 2 and computer == 0):
    print('你赢了')
elif player == computer:
    print('平局')
else:
    print('你输了')
```

三元表达式

```python
num1=3
num2=2
if num1 > num2:
    x=num1
else:
    x=num2
```

```python
x = num1 if num1 > num2 else num2
```

循环语句

while

```python
i = 0
num = 0
while i < 100:
    i += 1
    num += i
print(num)
```

for  

```python
for  i  in 可迭代对象 range(1,10)
```

break

```python
while  True:
    username = input('请输入账号:')
    password = input('请输入密码:')
    if  username == 'zhangsan' and  password == '123':
        break
    print('输入错误，请重试。')
```

循环的嵌套

九九乘法表

```python
for i in range(1,10):#控制行
    for  j  in range(1,10):#控制列
        if i >= j:
            print(j,'*',i,'=',i*j,end=' ')
    print()
```

```python
j = 0
while   j < 9 :
    j += 1
    i = 0
    while  i < j:
        i += 1
        print(i,'*',j,'=',i*j,end=' ')
    print()
```

数字取个位

```python
count = 0
for i in range(1,101):
    if i % 10 == 2 and i % 3 == 0:
        count += 1
        print(i)
print('满足条件的数字的个数是',count,'个')
```

判断数字的位数

```python
num = int(input('请输入一个整数：'))
count = 0
while  True:
    count += 1
    num //= 10
    if num == 0:
        break
print('您输入的数字是',count,'位数')
```

水仙花数

```python
for  i in range(100,1000):
    ge = i % 10
    shi = i // 10 %10
    bai = i // 100
    if  ge ** 3 + shi ** 3 + bai **3 ==i:
        print(i)
```

素数

```python
for i in range(101,201):
    for j in range(2,int(i ** 0.5) + 1):
        if  i % j == 0:
            #print(i, '不是素数')
            break
    else:
        #break没有执行时，执行else
        print(i,'是素数')
```

```python
for i in range(101,201):
   	flag = True
    for j in range(2,int(i ** 0.5) + 1):
         if  i % j == 0:
            flag = False
            break
   	if  falg:
        print(i,'是素数')
```

```python
for i in range(101,201):
   	count = 0
    for j in range(2,int(i ** 0.5) + 1):
         if  i % j == 0:
                count += 1
    if count == 0:
        print(i,'是素数')
    else
    	print(i,'是合数，它能被',count,'个数整除')
    
```

斐波那契数列

```python
num1 = 1
num2 = 1
for  i in range(0,12-2):
    a = num1
    num1 = num2
    num2 = a + num2
print(num2)
```

百马百担

```python
for  x  in range(0,100 // 3 + 1):
    for y in range(0,100 // 2 + 1):
        if 3 * x + 2 * y +(100 - x - y) * 0.5 == 100:
            print(x,y,(100-x-y))

```

纸张

```python
height = 0.08 / 1000
count = 0
while True:
    height *= 2
    count += 1
    if height >= 8848.13:
        break
print(count)
```

#### 索引

```python
w = 'aa'

print(w[1])  [start:end：步长] 有头 没尾  步长为负往左走
```

```python
print（len('z')） 字符的长度
```

```python
print(x.find('l')) 字符在第几个  不存在结果是负一
print(x.index('l'，开始，结束))   第一个l           不存在结果报错
print(x.rfind('l')) 最后一个
```

##### 判断字符串

```python
.startswith('a') 是不是以a开头
.endswith('a') 是不是以a结尾
.isalpha()   是不是字母
.isdigit()   是不是数字
.isalunm()    是不是字母和数字
.isspace()    是不是空格
.replace('a','b')  将字符中的a换成b
.split('-'，x) 将字符串以-分隔   rsplit为从右往左
.partition('x'),以x分割分成三段
.count()次数
.capitalize() 第一个单词首字母大写
.upper() 全都大写
.lower()全小写
.title()首字母大写
.ljust(10,'+') 字符串长度 长度不够补齐 超过长度不操作 rjust()左
.center（10,'-'）  居中两边加
.lstrip() 去空格 左 rstrip() 右  strip()两边
print('*'.join('hello')) 列表变字符串  
```

### 字符集

```python
ASCII   字符  编码  二进制   127
latin1    255
unicode 万国码
```

#### 字符编码

```python
chr()#编码看字符   ord() #查看编码
GBK：国标码 汉字两个字节 简体中文
BIG5:繁体中文
utf-8统一编码，汉字三个字节
.encode（）  #编码
.decode（）  #解码  .edcoed('gbk')
```

成员运算符

```python
in   not in 
```

格式化

```python
%s 字符串
%d  数字
%f  浮点数
%nd  几位  不够补齐
print('大家好，我是%s,今年%d岁了' % ('zhangsan',19))
print('大家好，我是{}，今年{}岁了'.format('zhangsan',18))
print('大家好，我是{0}，今年{1}岁了'.format('zhangsan',18))
print('大家好，我是{name}，今年{age}岁了'.format(name='zhangsan',age=18))
print('大家好，我是{name}，今年{age}岁了'.format(name='zhangsan',age=18))
d = ['zhangsan',18]
print('大家好，我是{}，今年{}岁了'.format(*d))
info = {'name':'zhangsan','age':18}
print('大家好，我是{name}，今年{age}岁了'.format(**info))
```

#### 列表

```python
#数据需要有序的保存  可变
#用[]   中，分割
#可以使用下标获得元素   #切片
name = ['张三','李四']
name = list（（'zhangsan','lisi'）） #list+可迭代对象 
name[1] = 'ss'
print(name[3:7])
#列表操作
#增
name.append('wanwu')
name.insert(index,object)
name.extend(可迭代对象)
#删除
name.pop() #最后一个 
name.remove(oject) 
nane.clear() #清空
del name[0]
#查
name.index('lisi')
name.count('lisi') 个数
print('wanwu' in name)
#改
name[1] = 'wanwu'
#遍历（可迭代对象）
cike = ['l','k','j','i','o','p']
for k in cike:
    print(k)
i = 0
while i < len(cike):
    print(cike[i])
    i += 1
交换
a = a + b
b = a - b 
a = a - b 

a = a ^ b
a = a ^ b
a = a ^ b

a,b = b,a
#冒泡排序 相邻比较
#方法一
s = [9,4,5,6,10]
n = 0
while n < len(s) - 1 :
    n += 1
    i = 0
    count = 0
    while i < len(s) - n :
        if s[i] > s[i+1]:
            s[i],s[i+1] = s[i+1],s[i]
            count += 1
        i += 1
    if count == 0:
        break
    print(count)
print(s)
#方法二
s = [9,4,5,6,10]
n = 0
while n < len(s) - 1 :
    flag = True
    n += 1
    i = 0
    count = 0
    while i < len(s) - n :
        count += 1
        if s[i] > s[i+1]:
            s[i],s[i+1] = s[i+1],s[i]
            flag = False
        i += 1
    if flag:
        break
    print(count)
print(s)
s.sort() #排序
sorted(s) #内置函数 新的列表
s.reverse() #翻转  print(s[::-1])
#列表的复制-----内容一样，指向不同的内存空间
	#数据保存在内存
    #不可变类型	字符串，数字，元祖  如果修改值，内存地址会发生变化
	#可变类型 	列表，字典，集合	如果修改值，内存地址不会发生变化
a = s.copy
import copy
a = copy.copy(x)
id(s)
用户名
names = ['s','sa']
name = input('请输入用户名')
for i in names:
    if name == names:
        print('用户名已存在')
        break
else:
    names.append(name)
print(names)

s.sort(reverse=True)
移入空字符串
word = ['s','','','b','']
word2 = []
for i in word:
    if i != '':
        word2.append(i)
    word = word2
print(word)
#老师学生
import random
laoshi = ['a','b','c','d','e','f','g','h','i','j']
rooms = [[],[],[]]
for ls in laoshi:
    room = random.choice(rooms)
    room.append(ls)
print(rooms)
for  i,room in enumerate(rooms):
    print('第%d个房间有%d为老师' % (i,len(room)),end=' ')
    for  room in room:
        print(room,end=' ')
    print('')
列表推导式
s  = [i for i in range(10)]
points = [(x,y) for x in range(5,10) for y in range(10,20)]
m = [i for i in range(1,101)]
n = [m[j:j+3] for j range(0,100,3)]
深浅拷贝
copy.copy(x)
copy.deepcopy(x)
```

元祖

```python
#不可变类型
print(tuple(可迭代对象))
+
```

字典

```python
key不重复 不可变类型
print（person['key']）
print(person.get('key','返回值'))
person.pop('key')  value
person.popitem() 删除的键值对
person.clear()清空
del person['key']
a.update(b)合并
#遍历
person = {'name' : 'sans','age' : 18,'height' : 180}
for  x in person:
    print(x,'=',person[x])
for  x in person.keys():
    print(x,'=',person[x])
for  x in person.values():
    print(x)
for  x in person.items():
    print(x[0],'=',x[1])
for  x,k in person.items():
    print(x,'=',k)
#用户添加
persons = [
    {'name' :'zhansan','age' : 19 },
    {'name': 'lisi','age' : 18 }
]
x = input('请输入用户名：')
for  person  in persons:
    if person['name'] == x:
        print('该用户名已存在')
        break
else:
    new_person = {'name':x}
    y = int(input('请输入年龄：'))
    new_person['age'] = y
    persons.append(new_person)
    print('用户添加成功')
    print(persons)
#统计
a = ['a','s','b','a','a','s','r','b']
char_count = {}
for  char in a:
    if char in char_count:
        #print('字典已经有这个字符了')
        char_count[char] += 1
    else:
        char_count[char] = 1
print(char_count)
char = char_count.values()
max_count = max(char)
print(max_count)
for k ,v in char_count.items():
    if v == max_count:
        print(k)
#推导式
dic1 = {'a':100,'b':200,'c':300}
dic2 = {}
for k,v in dic1.items():
    dic2[v] = k
print(dic2)
dict1 = {v:k for k,v in dic1.items()}
print(dict1)
#学业
sing = ('s','y','t')
dance = ('s','t','b')
rap = ('a','b','c')
total = sing + dance + rap
x = set(total)  #去重
print('学生总数是:',len(x))
sing_only = []
for person in sing:
    if  person not in dance and person not in rap:
        sing_only.append(person)
print('只选择了第一个学科的学生有{}人，是{}'.format(len(sing_only),sing_only))
p_dict = {}
for i in total:
    if i not in p_dict:
        p_dict[i] = total.count(i)
print(p_dict)
sing = ('s','y','t')
dance = ('s','t','b')
rap = ('a','b','c')
total = sing + dance + rap
x = set(total)  #去重
print('学生总数是:',len(x))
sing_only = []
for person in sing:
    if  person not in dance and person not in rap:
        sing_only.append(person)
print('只选择了第一个学科的学生有{}人，是{}'.format(len(sing_only),sing_only))
p_dict = {}
for i in total:
    if i not in p_dict:
        p_dict[i] = total.count(i)
print(p_dict)
m1 =[]
m2 =[]
for k,v in p_dict.items():
    if v == 1:
        m1.append(k)
    if v == 2:
        m2.append(k)
print('一门的：',m1)
print('两门的：',m2)
for k,v in p_dict.items():
    if v == 1:
        print('报了一门的：',k)
    if v == 2:
        print('报了两门的:',k)
#学生表
#student  = {'name' : '张三','age':18,'score':18, 'tel':'1298888123','gender':'female'}
students = [
{'name' : '张三','age':18,'score':18, 'tel':'1298888123','gender':'female'},
{'name' : '李四','age':78,'score':98, 'tel':'1297777128','gender':'male'},
{'name' : '王五','age':28,'score':108, 'tel':'1296666123','gender':'male'},
{'name' : '赵六','age':8,'score':28, 'tel':'1295555123','gender':'unknown'},
{'name' : '程七','age':48,'score':28, 'tel':'1294444128','gender':'female'},
{'name' : '周八','age':12,'score':68, 'tel':'1293333123','gender':'female'},
]
#(不及格)
count = 0
teenager_count = 0
max_score = students[0]['score']
for  i,student in enumerate(students):
    if student['score'] < 60:
        count += 1
        print('%s不及格，分数是%d' % (student['name'],student['score']))
    if student['age'] < 18:
        teenager_count += 1
        print('未成年的有%s' % student['name'])
    if student['tel'].endswith('8'):
        print('手机号以八结尾的有%s' % student['name'])
    if student['score'] > max_score:
        max_score = student['score']
print('不及格的学生有%d名' % count )
print('未成年的有%d名' % teenager_count)
print('最高成绩是--%d分' % max_score)
for  student in students:
    if student['score'] == max_score:
        print('最高分的学生%s' % student['name'] )
new_students = [x for x in students if x['gender'] != 'unknown']
print(new_students)
for  j in range(0,len(students) - 1):
    for i in range(0,len(students) - 1 - j):
        if  students[i]['score'] < students[i+1]['score']:
                students[i],students[i+1] = students[i+1],students[i]
print(students)
```

集合

```python
#无序，不重复，重复去重
.add()
.pop()随机
.clear()清空
.remove()删除指定的元素
.union()新的集合合并
.update()两个集合拼接
#运算符
-
& 与
| 并
^ 异或
#去重排序
nums = [1,25,4,8,7,4,7,6,5,12,1,21,5,45,5,24,1,2,5,4,4]
x =set(nums)
y =list(x)
y.sort(reverse=True)
print(y)
tuple(y)
#eval执行字符命令
a = 'input("请输入用户名")'
eval(b)
#结合其他语言
import  json
m = json.dumps(person)
print(type(m))#字符串
n = json.loads(m)#转换回去
```

比较

```python
#下标in遍历
#列表元祖字典
for i,j in enumerate(nmes):
    print(i,j)
#字典kv
for k,v in items():
    print(k,v)
```

### 函数

```python
def hanshu():
    #dama
    return #返回值默认元祖
	global #全局变量
#返回两个数时
x,y = test(8,3)
def  ll(name:str) #建议类型 
def  zwjs(name,age,dd='中国'): 
    print('我叫{},今年{}岁,来自{}'.format(name,age,dd))
zwjs('张三',19,'山西')
zwjs(age=12,name='历史')#默认参数(放在最后面)
#输入一个列表
nums = []
while True:
    num = input('请输入数字，输入exit退出：')
    if num.lower() != 'exit':
        nums.append(int(num))
    else:
        break
print(nums)
#可变参数  #*args可变位置参数  **kwargs可变关键字参数
def  a(a,b,*args):
    c = a + b
    for i in args:
        c += i
    return c
a = a(1,2,5,4,8,6,4,5)
print(a)
```





















































































