# 7.1 input()函数
**工作原理：** input() 函数让程序**暂停运行**,等待用户输入一些文本。获取用户输 后,Python 将其赋给一个变量,以便使用。
```
message = input("Tell me something, and I will repeat it back to you: ") print(message)
>>> Tell me something, and I will repeat it back to you: Hello everyone! Hello everyone!
```
input() 函数接受一个参数,即要向用户显示的提示(prompt),
python会先打印提示，然后暂停等待输入

**使用 int() 来获取数值输入：** 值得注意的是，用户输入的数值其实是以字符串表示的
	如果只想打印输入,  这一点儿问题都没有;但如果试图将输入作为数来使用,就会引发错误:
	可使用函数` int() `将输入的字符串转换为数值

**求模运算符：** 
在处理数值信息时,求模运算符(`%`)是个很有用的工具,它将两个数相除并返回余数:
最常见的，利用这一点来判断一个数是**奇数还是偶数**:
```
if num % 2 == 0:
	print(f"\nThe number {num} is even.")
else:
	print(f"\nThe number {num} is odd.")
```

# 7.2 while循环
**forandwhile：** for 循环用于针对集合中的**每个元素**执行一个代码块,而 while 循环则不断地运行,直到指定的**条件**不再满足为止。

**使用标志：** 在复杂的程序中,有很多不同的事件会导致程序停止运行。
	可定义一个变量,用于判断整  个程序是否处于活动状态。这个变量称为标志(flag)。
	可以让程序在标志为 True 时继续运行,并在任何事件导致标志的  值为 False 时让程序停止运行。这样,在 while 语句中就只需检查条件:标志的当前值是否为 True。
```
	active = True 
	❶ while active:
		if 条件1 or 条件2：
			active = false
```

**使用 break 退出循环：** `break` 立即退出 while 循环
**在循环中使用 continue：** 返回循环开头,并根据条件测试的结果决定是否继续执行循环
	continue只是不执行当次循环下面的代码

# 7.3 使用 while 循环处理列表和字典
**在列表之间移动元素：** 假设有一个列表包含新注册但还未验证的网站用户。验证这些用户后,如何将他们移到已验证用户列表中呢?
```
unconfirmed_users = ['alice', 'brian', 'candace'] 
confirmed_users = []

while unconfirmed_users: 
	❸current_user = unconfirmed_users.pop()  
	print(f"Verifying user: {current_user.title()}")
	confirmed_users.append(current_user)
```

**删除为特定值的所有列表元素：** 
要删除所有这些元素,可不断运行一个 while 循环,直到列表中不再包含值 'cat',如下所示:
```
pets = ['dog', 'cat', 'dog', 'goldfish', 'cat', 'rabbit', 'cat'] 

while 'cat' in pets: 
	pets.remove('cat')
```
**注意：** 这里有一个细节，进入这个循环后,`remove`每次只会删除第一个 'cat' 并返回 while 

**使用用户输入填充字典：** 可以使用 while 循环提示用户输入任意多的信息。
```
responses = {}

while polling_active: 
	name = input("\nWhat is your name? ") 
	response = input("Which mountain would you like to climb someday? ")

	responses[name] = response # 构建键值对name-response

for name, response in responses.items(): 
	print(f"{name} would like to climb {response}.")
```