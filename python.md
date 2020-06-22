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
以0b开头的数是二进制   bin()转化成二进制
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

```
.startswith('a') 是不是以a开头
.endswith('a') 是不是以a结尾
.isalpha()   是不是字母
.isdigit()   是不是数字
.isalunm()    是不是字母和数字
.isspace()    是不是空格
.replace('a','b')  将字符中的a换成b
.split('-'，x) 将字符串以-分隔   rsplit为从右往左
.partition('x'),以x分割分成三段

  
```

