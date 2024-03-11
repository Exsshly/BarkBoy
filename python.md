# Python

### Chap 1 起步

### Chap 2 变量和简单数据类型

#### 数值运算

`+`, `-`, `*`, `/`

`**` : 乘方
eg: `3**3=27`

#### 修改字符串

```
name = "ada lovelace"
print(name.title())
```

`Ada Lovelace`

```
name = "Ada Lovelace"
print(name.upper())
print(name.lower())
```

`ADA LOVELACE`
`ada lovelace`

#### 合并字符串

```
first_name = "ada"
last_name = "lovelace"
full_name = first_name + " " + last_name
print(full_name)
```

`ada lovelace`

```
first_name = "ada"
last_name = "lovelace"
full_name = first_name + " " + last_name
print("Hello, " + full_name.title() + "!")
```

`Hello, Ada Lovelace!`

#### 制表符&换行符

`\t` `\n`

#### 删除空白

```
favorite_language = 'python '
favorite_language 
```

`'python ' `

```
favorite_language.rstrip()
```

`'python' `

```
favorite_language
```

`'python ' `

```
favorite_language = favorite_language.rstrip()
favorite_language
```

`'python'`

```
favorite_language = ' python '
favorite_language.rstrip()
```

`' python' `

```
favorite_language.lstrip()
```

`'python ' `

```
favorite_language.strip() 
```

`'python' `

### Chap 3 列表

#### 列表

```
bicycles = ['trek', 'cannondale', 'redline', 'specialized']
print(bicycles)
```

`['trek', 'cannondale', 'redline', 'specialized']`

```
print(bicycles[0])
```

`trek`

```
bicycles = ['trek', 'cannondale', 'redline', 'specialized']
print(bicycles[0].title())
```

`Trek`

```
print(bicycles[-1])
```

`specialized`

##### 使用列表

```
bicycles = ['trek', 'cannondale', 'redline', 'specialized']
message = "My first bicycle was a " + bicycles[0].title() + "."
print(message)
```

`My first bicycle was a Trek.`

##### 修改列表

```
motorcycles = ['honda', 'yamaha', 'suzuki']
print(motorcycles)
motorcycles[0] = 'ducati'
print(motorcycles)
```

`['honda', 'yamaha', 'suzuki']`
`['ducati', 'yamaha', 'suzuki']`

##### 创建空表

`motorcycles = []`

##### 添加元素

```
motorcycles = ['honda', 'yamaha', 'suzuki']
print(motorcycles)
motorcycles.append('ducati')
print(motorcycles)
```

`['honda', 'yamaha', 'suzuki']`
`['honda', 'yamaha', 'suzuki', 'ducati']`

##### 删除元素1

```
motorcycles = ['honda', 'yamaha', 'suzuki']
print(motorcycles)
del motorcycles[0]
print(motorcycles)
```

`['honda', 'yamaha', 'suzuki']`
`['yamaha', 'suzuki']`

##### 删除元素2

```
motorcycles = ['honda', 'yamaha', 'suzuki']
print(motorcycles)
popped_motorcycle = motorcycles.pop()
print(motorcycles)
print(popped_motorcycle)
```

`['honda', 'yamaha', 'suzuki']`
`['honda', 'yamaha']`
`suzuki`

```
motorcycles = ['honda', 'yamaha', 'suzuki']
last_owned = motorcycles.pop()
print("The last motorcycle I owned was a " + last_owned.title() + ".")
```

`The last motorcycle I owned was a Suzuki.`

```
first_owned = motorcycles.pop(0)
print('The first motorcycle I owned was a ' + first_owned.title() + '.')
```

`The first motorcycle I owned was a Honda.`

##### 删除元素3

```
motorcycles = ['honda', 'yamaha', 'suzuki', 'ducati']
print(motorcycles)
motorcycles.remove('ducati')
print(motorcycles)
```

`['honda', 'yamaha', 'suzuki', 'ducati']`
`['honda', 'yamaha', 'suzuki']`

```
motorcycles = ['honda', 'yamaha', 'suzuki', 'ducati']
print(motorcycles)
too_expensive = 'ducati'
motorcycles.remove(too_expensive)
print(motorcycles)
print("\nA " + too_expensive.title() + " is too expensive for me.")
```

`['honda', 'yamaha', 'suzuki', 'ducati']`
`['honda', 'yamaha', 'suzuki']`
`A Ducati is too expensive for me.`

#### 永久排序

```
cars = ['bmw', 'audi', 'toyota', 'subaru']
cars.sort()
print(cars)
cars.sort(reverse=True)
print(cars)
```

`['audi', 'bmw', 'subaru', 'toyota']`
`['toyota', 'subaru', 'bmw', 'audi']`

#### 临时排序

```
cars = ['bmw', 'audi', 'toyota', 'subaru']
print("Here is the original list:")
print(cars)
print("\nHere is the sorted list:")
// cars.sorted(reverse=True)?
print("\nHere is the original list again:")
print(cars)
```

`Here is the original list:`
`['bmw', 'audi', 'toyota', 'subaru']`
`Here is the sorted list:`
`['audi', 'bmw', 'subaru', 'toyota']`
`Here is the original list again:`
`['bmw', 'audi', 'toyota', 'subaru']`

#### 元素倒序打印

```
cars = ['bmw', 'audi', 'toyota', 'subaru']
print(cars)
cars.reverse()
print(cars)
```

`['bmw', 'audi', 'toyota', 'subaru']`
`['subaru', 'toyota', 'audi', 'bmw']`

#### 确定列表长度

```
cars = ['bmw', 'audi', 'toyota', 'subaru']
len(cars)
```

`4`

### Chap 4 操作列表

#### 遍历列表

```
magicians = ['alice', 'david', 'carolina']
for magician in magicians:
	print(magician)
```

`alice`
`david`
`carolina`

```
magicians = ['alice', 'david', 'carolina']
for magician in magicians:
	print(magician.title() + ", that was a great trick!")
```

`Alice, that was a great trick!`
`David, that was a great trick!`
`Carolina, that was a great trick!`

```
magicians = ['alice', 'david', 'carolina']
for magician in magicians:
	print(magician.title() + ", that was a great trick!")
	print("I can't wait to see your next trick, " + magician.title() + ".\n")
```

`Alice, that was a great trick!`
`I can't wait to see your next trick, Alice.`
`David, that was a great trick!`
`I can't wait to see your next trick, David.`
`Carolina, that was a great trick!`
`I can't wait to see your next trick, Carolina.`

#### 创建数值列表

##### 函数range()

```
for value in range(1,5):
	print(value)
```

`1`
`2`
`3`
`4`

##### 使用range()创建列表

```
numbers = list(range(1,6))
print(numbers)
```

`[1, 2, 3, 4, 5]`

```
even_numbers = list(range(2,11,2))
print(even_numbers)
```

`[2, 4, 6, 8, 10]`

```
squares = []
for value in range(1,11):
	square = value**2
	squares.append(square) // squares.append(value**2)
	print(squares)
```

`[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]`

##### 对列表进行简单统计计算

```
digits = [1, 2, 3, 4, 5, 6, 7, 8, 9, 0]
print(min(digits))
print(max(digits))
print(sum(digits))
```

`0`
`9`
`45`

##### 列表解析

```
squares = [value**2 for value in range(1,11)]
print(squares)
```

`[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]`

#### 使用列表的一部分

##### 切片

```
players = ['charles', 'martina', 'michael', 'florence', 'eli']
print(players[0:3])
print(players[1:4])
print(players[:4])
print(players[2:])
print(players[-3:])
```

1. `['charles', 'martina', 'michael']`
2. `['martina', 'michael', 'florence']`
3. `['charles', 'martina', 'michael', 'florence']`
4. `['michael', 'florence', 'eli']`
5. `['michael', 'florence', 'eli']`

##### 遍历切片

```
players = ['charles', 'martina', 'michael', 'florence', 'eli']
print("Here are the first three players on my team:")
for player in players[:3]:
	print(player.title())
```

`Here are the first three players on my team:`
`Charles`
`Martina`
`Michael`

##### 复制列表

```
my_foods = ['pizza', 'falafel', 'carrot cake']
friend_foods = my_foods[:]

print("My favorite foods are:")
print(my_foods)

print("\nMy friend's favorite foods are:")
print(friend_foods)
```

`My favorite foods are:`
`['pizza', 'falafel', 'carrot cake']`
`My friend's favorite foods are:`
`['pizza', 'falafel', 'carrot cake']`

```
my_foods = ['pizza', 'falafel', 'carrot cake']
friend_foods = my_foods[:]

my_foods.append('cannoli')
friend_foods.append('ice cream')

print("My favorite foods are:")
print(my_foods)

print("\nMy friend's favorite foods are:")
print(friend_foods)
```

`My favorite foods are:`
`['pizza', 'falafel', 'carrot cake', 'cannoli']`
`My friend's favorite foods are:`
`['pizza', 'falafel', 'carrot cake', 'ice cream']`

#### 元组(不可修改)

##### 定义元组

```
dimensions = (200, 50)
print(dimensions[0])
print(dimensions[1])
```

`200`
`50`

##### 遍历元组

```
dimensions = (200, 50)
for dimension in dimensions:
	print(dimension)
```

`200`
`50`

##### 给元组赋值

```
dimensions = (200, 50)
print("Original dimensions:")
for dimension in dimensions:
	print(dimension)

dimensions = (400, 100)
print("\nModified dimensions:")
for dimension in dimensions:
	print(dimension)
```

`Original dimensions:`
`200`
`50`
`Modified dimensions:`
`400`
`100`

### Chap 5 if语句

#### 前置

`==` 检查是否相等

`!=` 检查是否不相等

`==` `>` `<` `>=` `<=` 比较数字



`and` 检查条件

```
age_0 = 22
age_1 = 18
age_0 >= 21 and age_1 >= 21
```

`False`

```
age_1 = 22
age_0 >= 21 and age_1 >= 21
```

`True`


`or` 检查条件

```
age_0 = 22 
age_1 = 18 
age_0 >= 21 or age_1 >= 21 
```

`True `

```
age_0 = 18 
age_0 >= 21 or age_1 >= 21 
```

`False`

`in` 检查特定值是否包含在列表中

```
requested_toppings = ['mushrooms', 'onions', 'pineapple']
'mushrooms' in requested_toppings
```

`True`

```
'pepperoni' in requested_toppings
```

`False`

`not in` 检查特定值是否不包含在列表中

```
banned_users = ['andrew', 'carolina', 'david'
user = 'marie'
if user not in banned_users:
	print(user.title() + ", you can post a response if you wish.")
```

`Marie, you can post a response if you wish.`

#### if-else语句

```
age = 17
if age >= 18:
	print("You are old enough to vote!")
	print("Have you registered to vote yet?")
else:
	print("Sorry, you are too young to vote.")
	print("Please register to vote as soon as you turn 18!")
```

`Sorry, you are too young to vote.`
`Please register to vote as soon as you turn 18!`

```
age = 12 

if age < 4: 
	price = 0 
elif age < 18: 
	price = 5 
else: 
	price = 10 

print("Your admission cost is $" + str(price) + ".")
```

`Your admission cost is $5.`

#### if-else测试多个条件

```
requested_toppings = ['mushrooms', 'extra cheese']

if 'mushrooms' in requested_toppings:
	print("Adding mushrooms.")
if 'pepperoni' in requested_toppings:
	print("Adding pepperoni.")
if 'extra cheese' in requested_toppings:
	print("Adding extra cheese.")

print("Finished making your pizza!"
```

`Adding mushrooms.`
`Adding extra cheese.`
`Finished making your pizza!`

#### 使用if语句处理列表

##### 检查特殊元素

```
requested_toppings = ['mushrooms', 'green peppers', 'extra cheese']

for requested_topping in requested_toppings:
	if requested_topping == 'green peppers':
		print("Sorry, we are out of green peppers right now.")
	else:
		print("Adding " + requested_topping + ".")

print("Finished making your pizza!")
```

`Adding mushrooms.`
`Sorry, we are out of green peppers right now.`
`Adding extra cheese.`
`Finished making your pizza!`

##### 确定列表非空

```
requested_toppings = []

if requested_toppings:
	for requested_topping in requested_toppings:
		print("Adding " + requested_topping + ".")
			print("\nFinished making your pizza!")
else:
	print("Are you sure you want a plain pizza?")
```

`Are you sure you want a plain pizza?`

##### 使用多个列表

```
available_toppings = ['mushrooms', 'olives', 'green peppers', 
'pepperoni', 'pineapple', 'extra cheese']

requested_toppings = ['mushrooms', 'french fries', 'extra cheese']

for requested_topping in requested_toppings:
	if requested_topping in available_toppings:
		print("Adding " + requested_topping + ".")
	else:
		print("Sorry, we don't have " + requested_topping + ".")

print("\nFinished making your pizza!")
```

`Adding mushrooms.`
`Sorry, we don't have french fries.`
`Adding extra cheese.`
`Finished making your pizza!`

### Chap 6 字典

#### 一个简单的字典

```
alien_0 = {'color': 'green', 'points': 5}
print(alien_0['color'])
print(alien_0['points'])
```

`green`
`5`

#### 使用字典

##### 访问字典中的值

```
alien_0 = {'color': 'green', 'points': 5}
print(alien_0['color'])

new_points = alien_0['points']
print("You just earned " + str(new_points) + " points!")
```

`green`
`You just earned 5 points!`

##### 添加键-值对

```
alien_0 = {'color': 'green', 'points': 5}
print(alien_0)

alien_0['x_position'] = 0
alien_0['y_position'] = 25

print(alien_0)
```

`{'color': 'green', 'points': 5}`
`{'color': 'green', 'points': 5, 'y_position': 25, 'x_position': 0}`

##### 创建空字典

```
alien_0 = {}
alien_0['color'] = 'green'
alien_0['points'] = 5

print(alien_0)
```

`{'color': 'green', 'points': 5}`

##### 修改字典中的值

```
alien_0 = {'color': 'green'}
print("The alien is " + alien_0['color'] + ".")

alien_0['color'] = 'yellow'
print("The alien is now " + alien_0['color'] + ".")
```

`The alien is green.`
`The alien is now yellow.`

##### 删除键-值对

```
alien_0 = {'color': 'green', 'points': 5}
print(alien_0

del alien_0['points']
print(alien_0)
```

`{'color': 'green', 'points': 5}`
`{'color': 'green'}`

##### 由类似对象组成的字典

```
favorite_languages = {
	'jen': 'python',
	'sarah': 'c++',
	'edward': 'rust',
	'phil': 'python',
 }
 
 print("Sarah's favorite language is " +
 	favorite_languages['sarah'].title() +
	".")
```

`Sarah's favorite language is C++.`

​		确定需要使用多行来定义字典时，在输入左花括号后按回车键，再在下一行缩进四个空格，指定第一个键—值对，并在它后面加上一个逗号。此后你再次按回车键时，文本编辑器将自动缩进后续键—值对，且缩进量与第一个键—值对相同。
​		定义好字典后，在最后一个键—值对的下一行添加一个右花括号，并缩进四个空格，使其与字典中的键对齐。另外一种不错的做法是在最后一个键—值对后面也加上逗号，为以后在下一行添加键—值对做好准备。

#### 遍历字典

##### 遍历所有键-值对

```
user_0 = {
	'username': 'efermi',
	'first': 'enrico',
	'last': 'fermi',
	}
for key, value in user_0.items():  //for k, v in user_0.items()
	print("\nKey: " + key)
	print("Value: " + value)
```

`Key: last`
`Value: fermi`
`Key: first`
`Value: enrico`
`Key: username`
`Value: efermi`

​		注意，即便遍历字典时，键—值对的返回顺序也与存储顺序不同。Python不关心键-值对的存储顺序，而只跟踪键和值之间的关联关系。

##### 遍历所有键

```
favorite_languages = {
	'jen': 'python',
	'sarah': 'c++',
	'edward': 'rust',
	'phil': 'python',
	}
for name in favorite_languages.keys():
	print(name.title())
```

`Jen`
`Sarah`
`Phil`
`Edward`

##### 按顺序遍历所有的键

```
for name in sorted(favorite_languages.keys()):
	print(name.title() + ", thank you for taking the poll.")
```

`Edward, thank you for taking the poll.`
`Jen, thank you for taking the poll.`
`Phil, thank you for taking the poll.`
`Sarah, thank you for taking the poll.`

##### 遍历所有值

```
print("The following languages have been mentioned:")
for language in favorite_languages.values():
	print(language.title())
```

`The following languages have been mentioned:`
`Python`
`C++`
`Python`
`Rust`

​		这种做法提取字典中所有的值，而没有考虑是否重复。涉及的值很少时，这也许不是问题，但如果被调查者很多，最终的列表可能包含大量的重复项。为剔除重复项，可使用集合（set）。
​		集合类似于列表，但每个元素都必须是独一无二的：

```
print("The following languages have been mentioned:")
for language in set(favorite_languages.values()):
	print(language.title())
```

`The following languages have been mentioned:`
`Python`
`C ++`
`Rust`

#### 嵌套

##### 字典列表

```
alien_0 = {'color': 'green', 'points': 5}
alien_1 = {'color': 'yellow', 'points': 10}
alien_2 = {'color': 'red', 'points': 15}

aliens = [alien_0, alien_1, alien_2]

for alien in aliens:
	print(alien)
```

##### 在字典中存储列表

 pizza = { 
 'crust': 'thick', 
 'toppings': ['mushrooms', 'extra cheese'], 
 } 

```
pizza = {
	'crust': 'thick',
	'toppings': ['mushrooms', 'extra cheese'],
	}

print("You ordered a " + pizza['crust'] + "-crust pizza " +
	"with the following toppings:")

for topping in pizza['toppings']:
	print("\t" + topping)
```

`You ordered a thick-crust pizza with the following toppings:`
&ensp;&ensp;&ensp;&ensp;`mushrooms`
&ensp;&ensp;&ensp;&ensp;`extra cheese`

```
favorite_languages = {
	'jen': ['python', 'ruby'],
	'sarah': ['c'],
	'edward': ['ruby', 'go'],
	'phil': ['python', 'haskell'],
	}

for name, languages in favorite_languages.items(): 
	print("\n" + name.title() + "'s favorite languages are:") 
	for language in languages: 
		print("\t" + language.title())
```

`Jen's favorite languages are:`
&ensp;&ensp;&ensp;&ensp;`Python`
&ensp;&ensp;&ensp;&ensp;`Ruby`
`Sarah's favorite languages are:`
&ensp;&ensp;&ensp;&ensp;`C++`
`Phil's favorite languages are:`
&ensp;&ensp;&ensp;&ensp;`Python`
&ensp;&ensp;&ensp;&ensp;`Haskell`
`Edward's favorite languages are:`
&ensp;&ensp;&ensp;&ensp;`Rust`
&ensp;&ensp;&ensp;&ensp;`Go`

##### 在字典中存储字典

```
users = {
	'aeinstein': {
		'first': 'albert',
		'last': 'einstein',
		'location': 'princeton',
		},
		
	'mcurie': {
		'first': 'marie',
		'last': 'curie',
		'location': 'paris',
		},
	}

for username, user_info in users.items():
	print("\nUsername: " + username)
	full_name = user_info['first'] + " " + user_info['last']
	location = user_info['location']

	print("\tFull name: " + full_name.title()) 
	print("\tLocation: " + location.title())
```

`Username: aeinstein`
`Full name: Albert Einstein`
`Location: Princeton`
`Username: mcurie`
`Full name: Marie Curie`
`Location: Paris`

### Chap 7 输入和while语句

#### 函数input()

```
message = input("Tell me something, and I will repeat it back to you: ")
print(message)
```

`Tell me something, and I will repeat it back to you:` **Hello everyone!**
`Hello everyone!`

```
name = input("Please enter your name: ")
print("Hello, " + name + "!")
```

`Please enter your name:`**Eric**

`Hello, Eric!`

```
prompt = "If you tell us who you are, we can personalize the messages you see."
prompt += "\nWhat is your first name? "

name = input(prompt)
print("\nHello, " + name + "!")
```

`If you tell us who you are, we can personalize the messages you see.`
`What is your first name? `**Eric**

`Hello, Eric!`

使用函数input()时，Python将用户输入解读为字符串。

```
height = input("How tall are you, in inches? ")
height = int(height)

if height >= 36:
	print("\nYou're tall enough to ride!")
else:
	print("\nYou'll be able to ride when you're a little older.")
```

`How tall are you, in inches?`

**71**

`You're tall enough to ride!`

#### 求模运算符 %

它将两个数相除并返回余数

如：4%3=1，6%3=0

#### while循环

```
current_number = 1
while current_number <= 5:
	print(current_number)
	current_number += 1
```

`1`
`2`
`3`
`4`
`5`

```
prompt = "\nTell me something, and I will repeat it back to you:" 
prompt += "\nEnter 'quit' to end the program. " 

message = ""
while message != 'quit':
	message = input(prompt)
	print(message)
```

`Tell me something, and I will repeat it back to you:`
`Enter 'quit' to end the program. Hello everyone!`
`Hello everyone!`

`Tell me something, and I will repeat it back to you:`
`Enter 'quit' to end the program. Hello again.`
`Hello again.`

`Tell me something, and I will repeat it back to you:`
`Enter 'quit' to end the program. quit`
`quit`

```
prompt = "\nTell me something, and I will repeat it back to you:"
prompt += "\nEnter 'quit' to end the program. "

message = "" 
while message != 'quit': 
	message = input(prompt)

	if message != 'quit':
		print(message)
```

`Tell me something, and I will repeat it back to you:`
`Enter 'quit' to end the program. Hello everyone!`
`Hello everyone!`

`Tell me something, and I will repeat it back to you:`
`Enter 'quit' to end the program. Hello again.`
`Hello again.`

`Tell me something, and I will repeat it back to you:`
`Enter 'quit' to end the program. quit`

```
prompt = "\nTell me something, and I will repeat it back to you:" 
prompt += "\nEnter 'quit' to end the program. "

active = True
while active:
	message = input(prompt)

	if message == 'quit':
		active = False
	else:
		print(message)
```

```
prompt = "\nPlease enter the name of a city you have visited:"
prompt += "\n(Enter 'quit' when you are finished.) "

while True:
	city = input(prompt)

	if city == 'quit':
		break

	else:
		print("I'd love to go to " + city.title() + "!")
```

`Please enter the name of a city you have visited:`
`(Enter 'quit' when you are finished.) New York`
`I'd love to go to New York!`

`Please enter the name of a city you have visited:`
`(Enter 'quit' when you are finished.) San Francisco`
`I'd love to go to San Francisco!`

`Please enter the name of a city you have visited:`
`(Enter 'quit' when you are finished.) quit`

#### continue在循环中的使用

```
current_number = 0
while current_number < 10:
	current_number += 1
	if current_number % 2 == 0:
		continue

	print(current_number)
```

`1`
`3`
`5`
`7`
`9`

#### 使用 while 循环来处理列表和字典

```
unconfirmed_users = ['alice', 'brian', 'candace']
confirmed_users = []

while unconfirmed_users:
	current_user = unconfirmed_users.pop()
	print("Verifying user: " + current_user.title())
	confirmed_users.append(current_user)

print("\nThe following users have been confirmed:") 
for confirmed_user in confirmed_users: 
	print(confirmed_user.title())
```

`Verifying user: Candace`
`Verifying user: Brian`
`Verifying user: Alice`

`The following users have been confirmed:`
`Candace`
`Brian`
`Alice`

#### 删除包含特定值的所有列表元素

```
pets = ['dog', 'cat', 'dog', 'goldfish', 'cat', 'rabbit', 'cat']
print(pets)

while 'cat' in pets:
	pets.remove('cat')

print(pets)
```

`['dog', 'cat', 'dog', 'goldfish', 'cat', 'rabbit', 'cat']`
`['dog', 'dog', 'goldfish', 'rabbit']`

```
responses = {}
polling_active = True

while polling_active:
name = input("\nWhat is your name? ")
	response = input("Which mountain would you like to climb someday? ")
	responses[name] = response

	repeat = input("Would you like to let another person respond? (yes/ no) ") 
	if repeat == 'no': 
		polling_active = False 

print("\n--- Poll Results ---") 
for name, response in responses.items(): 
	print(name + " would like to climb " + response + ".")
```

`What is your name? Eric`
`Which mountain would you like to climb someday? Denali`
`Would you like to let another person respond? (yes/ no) yes`

`What is your name? Lynn`
`Which mountain would you like to climb someday? Devil's Thumb`
`Would you like to let another person respond? (yes/ no) no`

`--- Poll Results ---`
`Lynn would like to climb Devil's Thumb.`
`Eric would like to climb Denali.`

### Chap 8 函数

#### 定义函数

```
def greet_user():
	print("Hello!")

greet_user()
```

`Hello!`

#### 传递实参

```
def greet_user(username):
	print("Hello, " + username.title() + "!")

greet_user('jesse')
```

`Hello, Jesse!`

#### 位置实参

```
def describe_pet(animal_type, pet_name):
	print("\nI have a " + animal_type + ".")
	print("My " + animal_type + "'s name is " + pet_name.title() + ".")

describe_pet('hamster', 'harry')
```

`I have a hamster.`
`My hamster's name is Harry.`

```
def describe_pet(animal_type, pet_name):
	print("\nI have a " + animal_type + ".")
	print("My " + animal_type + "'s name is " + pet_name.title() + ".")

describe_pet(animal_type='hamster', pet_name='harry')
```

`describe_pet(animal_type='hamster', pet_name='harry')`
`describe_pet(pet_name='harry', animal_type='hamster')`

#### 关键字实参

```
def describe_pet(animal_type, pet_name):
	print("\nI have a " + animal_type + ".")
	print("My " + animal_type + "'s name is " + pet_name.title() + ".")

describe_pet(animal_type='hamster', pet_name='harry')
```

`describe_pet(animal_type='hamster', pet_name='harry')`
`describe_pet(pet_name='harry', animal_type='hamster')`

#### 默认值

```
def describe_pet(pet_name, animal_type='dog'): 
	print("\nI have a " + animal_type + ".") 
	print("My " + animal_type + "'s name is " + pet_name.title() + ".")

describe_pet(pet_name='willie')
```

`I have a dog.`
`My dog's name is Willie.`

#### 返回值

##### 返回简单值

```
def get_formatted_name(first_name, last_name):
	full_name = first_name + ' ' + last_name
	return full_name.title()

musician = get_formatted_name('jimi', 'hendrix')
	print(musician)
```

`Jimi Hendrix`

```
def get_formatted_name(first_name, middle_name, last_name):

	full_name = first_name + ' ' + middle_name + ' ' + last_name 
	return full_name.title()

musician = get_formatted_name('john', 'lee', 'hooker')
	print(musician)
```

`John Lee Hooker`

##### 让实参变成可选

​		然而，并非所有的人都有中间名，但如果你调用这个函数时只提供了名和姓，它将不能正确
地运行。为让中间名变成可选的，可给实参middle_name指定一个默认值——空字符串，并在用
户没有提供中间名时不使用这个实参。为让get_formatted_name()在没有提供中间名时依然可行，
可给实参middle_name指定一个默认值——空字符串，并将其移到形参列表的末尾：

```
def get_formatted_name(first_name, last_name, middle_name=''):
	if middle_name:
		full_name = first_name + ' ' + middle_name + ' ' + last_name
	else:
		full_name = first_name + ' ' + last_name
	return full_name.title()

musician = get_formatted_name('jimi', 'hendrix')
print(musician)

musician = get_formatted_name('john', 'hooker', 'lee')
print(musician)
```

`Jimi Hendrix`
`John Lee Hooker`

##### 返回字典

```
def build_person(first_name, last_name):
	person = {'first': first_name, 'last': last_name}
	return person

musician = build_person('jimi', 'hendrix')
print(musician)
```

`{'first': 'jimi', 'last': 'hendrix'}`

```
def build_person(first_name, last_name, age=''):
	person = {'first': first_name, 'last': last_name}
	if age:
		person['age'] = age
	return person

musician = build_person('jimi', 'hendrix', age=27)
print(musician)
```

##### 结合使用函数和while循环

```
def get_formatted_name(first_name, last_name):
	full_name = first_name + ' ' + last_name
	return full_name.title()

while True:
	print("\nPlease tell me your name:")
	print("(enter 'q' at any time to quit)")

 	f_name = input("First name: ")
 	if f_name == 'q':
 		break

 	l_name = input("Last name: ")
 	if l_name == 'q':
 		break

 	formatted_name = get_formatted_name(f_name, l_name)
	print("\nHello, " + formatted_name + "!")
```

`Please tell me your name:`
`(enter 'q' at any time to quit)`
`First name: eric`
`Last name: matthes`
`Hello, Eric Matthes!`
`Please tell me your name:`
`(enter 'q' at any time to quit)`
`First name: q`

#### 传递列表

```
def greet_users(names):
	for name in names:
		msg = "Hello, " + name.title() + "!"
		print(msg)

usernames = ['hannah', 'ty', 'margot']
greet_users(usernames)
```

`Hello, Hannah!`
`Hello, Ty!`
`Hello, Margot!`

##### 在函数中修改列表

```
unprinted_designs = ['iphone case', 'robot pendant', 'dodecahedron']
completed_models = []

while unprinted_designs: 
	current_design = unprinted_designs.pop() 

 	print("Printing model: " + current_design)
 	completed_models.append(current_design)

print("\nThe following models have been printed:")
for completed_model in completed_models:
	print(completed_model)
```

`Printing model: dodecahedron`
`Printing model: robot pendant`
`Printing model: iphone case`

`The following models have been printed:`
`dodecahedron`
`robot pendant`
`iphone case`

```
def print_models(unprinted_designs, completed_models):
	while unprinted_designs:
	current_design = unprinted_designs.pop()
	print("Printing model: " + current_design)
	completed_models.append(current_design)

def show_completed_models(completed_models):
	print("\nThe following models have been printed:")
	for completed_model in completed_models:
	print(completed_model)
 
unprinted_designs = ['iphone case', 'robot pendant', 'dodecahedron']
completed_models = []

print_models(unprinted_designs, completed_models)
show_completed_models(completed_models)
```

##### 禁止函数修改列表

​		有时候，需要禁止函数修改列表。例如，假设像前一个示例那样，你有一个未打印的设计列表，并编写了一个将这些设计移到打印好的模型列表中的函数。你可能会做出这样的决定：即便打印所有设计后，也要保留原来的未打印的设计列表，以供备案。但由于你将所有的设计都移出unprinted_designs，这个列表变成了空的，原来的列表没有了。为解决这个问题，可向函数传递列表的副本而不是原件；这样函数所做的任何修改都只影响副本，而丝毫不影响原件。要将列表的副本传递给函数，可以像下面这样做：

`function_name(list_name[:])`

切片表示法[:]创建列表的副本。在代码中，如果不想清空未打印的设计列表，可像下面这样调用

`print_models():`
`print_models(unprinted_designs[:], completed_models)`

这样函数依然能够完成其工作，因为它获得了所有未打印的设计的名称，但它使用的是列表unprinted_designs的副本，而不是列表unprinted_designs本身。

#### 传递任意数量的实参

```
def make_pizza(*toppings):
	print("\nMaking a pizza with the following toppings:")
	for topping in toppings:
		print("- " + )

make_pizza('pepperoni')
make_pizza('mushrooms', 'green peppers', 'extra cheese')
```

形参名 `*toppings` 中的星号让Python创建一个名为toppings的空元组，并将收到的所有值都封装到这个元组中。函数体内的print语句通过生成输出来证明Python能够处理使用一个值调用函数的情形，也能处理使用三个值来调用函数的情形。它以类似的方式处理不同的调用，注意，Python将实参封装到一个元组中，即便函数只收到一个值也如此。

`Making a pizza with the following toppings:`
`- pepperoni`

`Making a pizza with the following toppings:`
`- mushrooms`
`- green peppers`
`- extra cheese`

##### 结合使用位置实参和任意数量实参

```
def make_pizza(size, *toppings):
	print("\nMaking a " + str(size) + 
		"-inch pizza with the following toppings:") 
	for topping in toppings: 
		print("- " + topping) 

make_pizza(16, 'pepperoni') 
make_pizza(12, 'mushrooms', 'green peppers', 'extra cheese')
```

`Making a 16-inch pizza with the following toppings:`
`- pepperoni`

`Making a 12-inch pizza with the following toppings:`
`- mushrooms`
`- green peppers`
`- extra cheese`

##### 使用任意数量的关键字实参

```
def build_profile(first, last, **user_info): 
	profile = {} 
	profile['first_name'] = first 
	profile['last_name'] = last 
	for key, value in user_info.items():
		profile[key] = value
 	return profile

user_profile = build_profile('albert', 'einstein',
							location='princeton',
							field='physics')
print(user_profile)
```

`{'first_name': 'albert', 'last_name': 'einstein',`
`'location': 'princeton', 'field': 'physics'}`

#### 将函数存储在模块中

##### 导入整个模块

import *module_name*

需使用句点

##### 导入特定的函数

from *module_name* import *function_name*

from *module_name* import *function_0, function_1, function_2*

**无需使用句点**

##### 使用as给函数指定别名

from *module_name* import *function_name* as *fn*

##### 使用as给模块指定别名

import *module_name* as *mn*

##### 导入模块中所有函数

from *module_name* import *

**无需使用句点**

### Chap 9 类

#### 创建和使用类

##### 创建Dog类

```
class Dog():

	def __init__(self, name, age):
		self.name = name
		self.age = age

	def sit(self):
		print(self.name.title() + " is now sitting.")

	def roll_over(self):
		print(self.name.title() + " rolled over!")
```

##### 根据类创建实例

```
class Dog():
 --上面的Dog类--

my_dog = Dog('willie', 6)

print("My dog's name is " + my_dog.name.title() + ".")
print("My dog is " + str(my_dog.age) + " years old.")
```

TO BE CONTINUED>>>