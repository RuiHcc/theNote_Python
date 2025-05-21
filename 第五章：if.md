# 5.1 条件测试
每条 if 语句的核心都是一个值为 True 或 False 的表达式,这种表达式称为**条件测试**。Python 根据条件测试的值是 True 还是 False 来决定是否执行 if 语句中的代码。
```
cars = ['audi', 'bmw', 'subaru', 'toyota']  
for car in cars: 
if car == 'bmw': 
	print(car.upper()) 
else: 
	print(car.title())
```

**检查是否相等：**
```
car == 'bmw'
```
**如何在检查是否相等时忽略大小写：**
```
car.lower() == 'audi'  # 验证码忽略大小写
```

**检查是否不等：**
```
requested_topping = 'mushrooms'  
if requested_topping != 'anchovies': 
	print("Hold the anchovies!")
```
**数值比较：** `age == 18`

**检查多个条件：** `and`  `or`

**检查特定的值是否在列表中：** 要判断特定的值是否在列表中,可使用关键字 `in`
```
requested_toppings = ['mushrooms', 'onions', 'pineapple'] 
'mushrooms' in requested_toppings 
>>>True
```
**检查特定的值是否不在列表中：** 还有些时候,确定特定的值不在列表中很重要。在这种情况下,可使用关键字 `not in`。

# 5.3 if 语句
**简单的 if 语句**
**if-else 语句**
**if-elif-else 语句**
**使用多个 elif 代码块**
**省略 else 代码块**
**测试多个条件（多个if）**

# 5.3 使用 if 语句处理列表