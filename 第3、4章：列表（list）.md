# 3.1 列表
列表(list)由一系列按特定顺序排列的元素组成。在 Python 中,用方括号`[]`表示列表,用逗号分隔其中的元素。

**访问列表元素：**
```
bicycles = ['trek', 'cannondale', 'redline', 'specialized'] print(bicycles[0])
>>> trek
```
当请求获取列表元素时,Python 只返回该元素,而不包括方括号
还可以对任意列表元素调用第 2 章介绍的字符串方法。例如,可使用  `title() `方法让元素 'trek' 的格式更标准:
```
print(bicycles[0].title())
>>> Trek
```

**索引从 0 而不是 1 开始：**

**使用列表中的各个值：** 可以像使用其他变量一样使用列表中的各个值。例如,可以使用 f 字符串  根据列表中的值来创建消息。
```
bicycles = ['trek', 'cannondale', 'redline', 'specialized'] 
message = f"My first bicycle was a {bicycles[0].title()}."  
print(message)
>>> My first bicycle was a Trek.
```


# 3.2 修改、添加和删除元素
你创建的大多数列表将是**动态**的,这意味着列表创建后,将随着程序的运 行增删元素。
**修改列表元素：**
```
motorcycles[0] = 'ducati'
```
**在列表中添加元素：**
- **1、在列表末尾添加元素：** 将元素追加(`append`)到列表末尾。
```
motorcycles = ['honda', 'yamaha', 'suzuki'] 
motorcycles.append('ducati') 
print(motorcycles)

>>> ['honda', 'yamaha', 'suzuki', 'ducati']
```
`append() `方法让**动态地创建列表**更简单：先创建一个空列表，在使用一系列函数调用 `append()` 添加元素:
```
motorcycles = []  
motorcycles.append('honda') 
motorcycles.append('yamaha') 
motorcycles.append('suzuki')  

print(motorcycles)
>>> ['honda', 'yamaha', 'suzuki']
```
- **2、在列表中插入元素：** `insert() `方法可在列表的任意位置添加新元素。为此,需要指  定新元素的索引和值:
```
motorcycles = ['honda', 'yamaha', 'suzuki']  
motorcycles.insert(0, 'ducati') 
print(motorcycles)
>>> ['ducati', 'honda', 'yamaha', 'suzuki']
```


**从列表中删除元素：**
- **1、使用 del 语句删除元素**
```
motorcycles = ['honda', 'yamaha', 'suzuki'] 
del motorcycles[0] 
print(motorcycles)
>>> ['yamaha', 'suzuki']
```
- **2、使用 pop() 方法删除元素**
`pop() `方法删除列表末尾的元素,并让你能够接着使用它。术语**弹出  (pop)** 源自这样的类比:列表就像一个栈,而删除列表末尾的元素相  当于弹出栈顶元素。
```
❶motorcycles = ['honda', 'yamaha', 'suzuki'] 
print(motorcycles)  
❷popped_motorcycle = motorcycles.pop() 
❸ print(motorcycles)  
❹ print(popped_motorcycle)
```
从这个列表中弹出一个值,并将其赋给变量 `popped_motorcycle`(⻅❷)
- **3、删除列表中任意位置的元素**
实际上,也可以使用 pop() 删除列表中任意位置的元素,只需要在括号中指定要删除的元素的索引即可。
```
motorcycles = ['honda', 'yamaha', 'suzuki']  first_owned = motorcycles.pop(0) 
```
**注：** 如果要从列表中删除一个元素,且不再以任何方式使用它,就  使用 `del` 语句;如果要在删除元素后继续使用它,就使用 `pop()` 方法。
- **4、根据值删除元素**
如果只知道要删除的元素的值,可使用 `remove()` 方法。
```
motorcycles.remove('ducati')
```
**注意**:`remove() `方法只删除第一个指定的值。如果要删除的值可能在列表中出现多次,就需要使用循环,确保将每个值都删除。


# 3.3 管理列表
**使用 sort() 方法对列表进行永久排序：** Python 方法 `sort() `让你能够较为轻松地对列表进行排序。假设你有一个汽⻋列表,并要让其中的汽⻋按字母顺序排列。
还可以按与字母**顺序相反**的顺序排列列表元素,只需向 sort() 传递参数 `reverse=True` 即可。
```
cars = ['bmw', 'audi', 'toyota', 'subaru'] 
cars.sort() 
print(cars)
>>> ['audi', 'bmw', 'subaru', 'toyota']

cars.sort(reverse=True)

```

**使用 sorted() 函数对列表进行临时排序：** 要保留列表元素原来的排列顺序,并以特定的顺序呈现它们,可使用  `sorted() `函数。

**反向打印列表：** 要反转列表元素的排列顺序,可使用 `reverse()` 方法。
注意,`reverse()` 不是按与字母顺序相反的顺序排列列表元素,只是反转列表元素的排列顺序：`reverse()` 方法会永久地修改列表元素的排列顺序,但可随时恢复到原来的排列顺序,只需对列表再次调用 `reverse() `即可。

**确定列表的⻓度：**
```
cars = ['bmw', 'audi', 'toyota', 'subaru'] 
len(cars)
```
注意:Python 在计算列表元素数时从 1 开始,因此你在确定列表⻓度时应该不会遇到差一错误。

**索引 -1 总是返回最后一个列表元素**


# 4.1 遍历整个列表
使用 `for` 循环,可让 Python 去处理每个元素,从而避免这  些问题。
```
magicians = ['alice', 'david', 'carolina'] 
for magician in magicians: 
	print(magician)
```

# 4.2 避免缩进错误
**Python 根据缩进来判断代码行与程序其他部分的关系。** 在前面的示例中,  向各位魔术师显示消息的代码行是 for 循环的一部分,因为它们缩进了。

# 4.3 创建数值列表
列表非常适合用于存储数值集合,而 Python 提供了很多工具,可帮助你高效地处理数值列表。
**使用 range() 函数：**
```
for value in range(1, 5): 
	print(value)
>>> 1
>>> 2
>>> 3
>>> 4
```
`range() `只打印数 1〜4   `range() `函数让 Python 从指定的第一个值开始数,并在到达指定的第二个值时停止,因此输出不包含第二个值(这里为 5)
在调用 range() 函数时,也可只指定一个参数,这样它将从 0 开始

**使用 range() 创建数值列表：**
要创建数值列表,可使用 `list() `函数将` range() `的结果直接转换为列表。如果将 `range() `作为 `list()` 的参数,输出将是一个数值列表。
**注：** range创建的类型（type）就是range（1,5）
```
numbers = list(range(1, 6)) 
print(numbers)
>>> [1, 2, 3, 4, 5]
```
在使用 range() 函数时,还可指定步⻓。为此,可以给这个函数指定第三个参数,Python 将根据这个步⻓来生成数。
```
even_numbers = list(range(2, 11, 2)) 
```

**对数值列表执行简单的统计计算：**
- `min()`
- `max()`
- `sum()`

**列表推导式：** 较为实用
列表推导式(list comprehension)  将 for 循环和创建新元素的代码合并成一行,并自动追加新元素。
```
squares = [value**2 for value in range(1, 11)] 
print(squares)
>>> [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

# 4.4 使用列表的一部分
**切片：** 
输出列表中的前三个元素,需要指定索引 0 和 3,这将返回索引分别为  0、1 和 2 的元素。
```
players = ['charles', 'martina', 'michael', 'florence', 'eli'] print(players[0:3])
print(players[:4])
print(players[2:])
```
如果没有指定第一个索引,Python 将自动从列表开头开始，要让切片终止于列表末尾,也可使用类似的语法。
如果要输出名单上最后三名队员的名字,可使用切片 `players[-3:]`
**注意:** 可在表示切片的方括号内指定第三个值。这个值告诉 Python 在  指定范围内每隔多少元素提取一个。

**复制列表:**
```
friend_foods = my_foods[:]
```
在不指定任何索引的情况下,从列表  my_foods 中提取一个切片,从而创建这个列表的副本,再将该副本赋给变量 friend_foods
但是不通过切片，直接赋值是行不通的
```
# 这是行不通的:  
friend_foods = my_foods
```
**注意：** 这种语法实际上是让 Python 将新变量  friend_foods 关联到已与 my_foods 相关联的列表,因此这**两个变量指向同一个列表**。

# 4.5 元组（tuple)
列表非常适合用于存储在程序运行期间可能变化的数据集。Python  将不能修改的值称为不可变的,而不可变的列表称为元组(tuple)。

**定义元组：**
使用圆括号而不是方括号来标识。定义元组后,  就可使用索引来访问其元素,就像访问列表元素一样。
```
dimensions = (200, 50) 
print(dimensions[0]) 
print(dimensions[1])
```

**遍历元组中的所有值：** 和列表类似

**修改元组变量**：虽然不能修改元组的元素,但可以给表示元组的变量赋值。即重新定义
相比于列表,元组是更简单的数据结构。如果需要存储一组在程序的整个生命周期内都不变的值,就可以使用元组。