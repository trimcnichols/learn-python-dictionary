# learn-python-dictionary

Click the snake to see the code and explanation about my code
<!-- 
<details><summary>:snake: </summary>
<p>

```python
   
```
</p>
</details>

*******************************************
-->
<details><summary>:snake: Inventory substitution game</summary>
<p>

```python
 equipped = {'right_hand' : 'Nothing', 'left_hand' : 'Nothing'}

equipped['right_hand'] = 'Dagger'
equipped['left_hand'] = 'Shield'
print(equipped)

print()

backpack = ['gemstone', 'trinket', 'sword']

temp = equipped['right_hand']
equipped['right_hand'] = backpack[2]
backpack[2] = temp
print(equipped)
print(backpack)
print()

money ={'gold' : 5, 'silver' : 13, 'copper':24}
armor = 7
left = 7
if left > money['gold']:
	left -=money['gold']
	money['gold']=0
else:
	money['gold'] -=left
	left = 0
left *=5
if left  > money['silver']:
	left -=money['silver']
	money['silver']= 0
else:
	money['silver'] -= left
	left =0 
left *=10 
if left > money['copper']:
	left -=money['copper']
	money['copper'] = 0
else:
	money['copper'] -= left
	left = 0
print(left)
print(money)
equipped['body'] = 'steel armor'

print(equipped)
print(money)

weapon_left = input("what do you want to hold in your left hand: ")
if weapon_left in backpack:
	backpack.append(equipped['left_hand'])
	equipped['left_hand'] = weapon_left
	backpack.remove(weapon_left)
else:
	print("I dont have that")

print(equipped)
print(backpack)
loot = ['bow','health potion','leather armor']
for i in range(len(loot)):
	backpack.append(loot[i])
print(backpack)

found_money = {'silver': 1, 'copper': 4}
#money['silver'] +=found_money['silver']
#money['copper'] +=found_money['copper']
for token in found_money:
	if token in money:
		money[token] +=found_money[token]
	else:
		money[token] = money[token]

print(money)


  
```
</p>
</details>

<details><summary>:snake: Employee database project</summary>
<p>

```python
jdoe = {"name":"John Doe","age":45, "salary":50000,"job":"Janitor"}
ssmith = {"name":"Susan smith","age":34, "salary":67000,"job":"Secretary"}
kjones = {"name":"Kevin Jones","age":35, "salary":80000,"job":"Teacher"}
employees = {"jdoe":jdoe, "ssmith":ssmith, "kjones":kjones}


#print the age of John Doe
print(employees["jdoe"]["age"])
print(employees["kjones"]["job"])
employees["ssmith"]["salary"] = 70000
print(employees["ssmith"])

#print out the each person
for key in employees:
	print(employees[key])

#print out each employees name
for key in employees:
	print(employees[key]["name"])

#create a dictionary for jrayes, add him into employees
jrayes ={"name":"John Rayes","age":25, "salary":64000,"job":"driver"}


employees["jrayes"] = jrayes
print(employees)

#how  much all the employees salary
salary = 0

for key in employees:
	salary +=employees[key]["salary"]
print(f"Total employees salary is: {salary}")

#add new item, key of "access" value 0f True, to each person's dictionary

for key in employees:
	employees[key]["access"] = True
print(employees)

#change the janitor access to be False

for key in employees:
	if employees[key]["job"]=="janitor" or employees[key]["job"] == "Janitor":
		employees[key]["access"] = False
print(employees)

#access with username
user = input("enter your name: ")
#for key in employees:
if user in employees:

	if employees[user]["access"] == True:
		print("access granted")
	elif employees[user]["access"] == False:
		print("access denied")
else:
	
	print("user unknown")

'''
#1

print(jdoe["age"])
print()

#2
print(kjones["job"])

print()
#3

print(f'{jdoe["name"]} has salary: {jdoe["salary"]}')
print(f'{ssmith["name"]} has salary: {ssmith["salary"]}')
print(f'{kjones["name"]} has salary: {kjones["salary"]}')

#4
print()
Jrayes ={"name": "Jay Rayes"}
enter_age = input(f"what is {Jrayes['name']}'s age: ")
Jrayes["age"] = enter_age

enter_salary = input(f"what is {Jrayes['name']}'s salary: ")
Jrayes["salary"] = enter_salary

enter_job = input(f"what is {Jrayes['name']}'s job: ")
Jrayes["job"] = enter_job

print(Jrayes)

#5
ssmith["salary"]=70000
print(ssmith)
print()
#6
jdoe["job"]= "Lead Janitor"
jdoe["salary"] = 55000
print(jdoe)
print()
# 7

print(jdoe)
print(ssmith)
print(kjones)
print(Jrayes)

'''


   
```
</p>
</details>


<details><summary>:snake: Nested inventory store project</summary>
<p>

```python
all_stores={
	'Store 1':{'Item A' :10, 'Item B': 2},
	'Store 2' :{'Item A' : 8, 'Item C': 6, 'Item D': 4},
	'Store 3' : {'Item B' : 7, 'Item D' : 5}
}


print(f" Store 2 has : {all_stores['Store 2']['Item A']} item A")

print(f" Store 3 has : {all_stores['Store 3']['Item D']} item D")
Store2_item = 0


for item in all_stores['Store 2']:
	Store2_item += all_stores['Store 2'][item]

print(f"Store 2 items : {Store2_item}")
itemA = 0 
for store in all_stores:
	if 'Item A' in all_stores[store]:
		itemA = itemA + all_stores[store]['Item A']

print(f" total Item A in all stores  {itemA}")

total = 0
for store in all_stores:
	for item in all_stores[store]:
		total += all_stores[store][item]

print(f"Total item : {total}")
#new distionary : inventory, and list all the itemin all_stores
inventory = {}
for store in all_stores:
	for item in all_stores[store]:
		if item not in inventory:
			inventory.update({item:all_stores[store][item]})
		else:
			inventory.update({item : inventory[item] + all_stores[store][item]})
print(inventory)

   
```
</p>
</details>


<details><summary>:snake: Animal's legs project</summary>
<p>

```python
 animals = {"dog": 4,"bird": 2, "fish" : 0, "cat": 4, "human" : 2}

for animal in animals:
	print(animal)
print()
for animal in animals:
	print(f" A {animal} has {animals[animal]} legs")

print()

for animal in animals:
	if animals[animal] == 2:
		print(f" A {animal} has 2 legs")

print()

animals.update({"octopus":8})
print(animals)
		
newAn = input("enter a new animal: ")


if newAn in animals:
	
	print(f" this {newAn} has {animals[animal]} legs")

else:

	newLegs = input(f"please enter {newAn} legs: ")
	animals.update({newAn:newLegs})
print(animals)
print()

new_animals = ['ant','spider','worm','llama']
for newAnimal in new_animals:
	newAnLegs = input(f"please enter {newAnimal} legs: ")
	animals.update({newAnimal:newAnLegs})
print(animals)

  
```
</p>
</details>

<details><summary>:snake: Phone carrier project </summary>
<p>

```python
students = {
"16023" :{'name': 'Susan Smith', 'phone':'(555) 987-6543'},
"19832" :{'name': 'John Doe', 'phone':'(555) 123-4567', 'carrier' : 'Verison'},
"74351" :{'name': 'Bob Roon', 'phone':'(555) 152-8123', 'carrier' : 'Sprint'},
"38592" :{'name': 'Tina Lee', 'phone':'(555) 943-9234'},
"98278" :{'name': 'Jack Torrence', 'phone':'(555) 467-8254'},

}
'''
print(students)
#student = input("enter your user id : ")

for id in students:
	#for item in students[id]:
		
	if 'carrier' in students[id]: 
		print(f"hello {students[id]['name']} to the number {students[id]['phone']} with {students[id]['carrier']}")
	else:
		prov = input(f"what is your carrier {students[id]['name']} : ")
		students[id]['carrier'] = prov
		print(f"hello {students[id]['name']} to the number {students[id]['phone']} with {students[id]['carrier']}")
'''
for id in students:
	if 'carrier' not in students[id]:
		prov = input(f"what is your carrier {students[id]['name']} : ")
		students[id]['carrier'] = prov

print(students)

for id in students:
	print(f"Hello {students[id]['name']} to the number {students[id]['phone']} with {students[id]['carrier']}")	
   
```
</p>
</details>
<details><summary>:snake: Store inventory project</summary>
<p>

```python
store1 = {'Item A': 250, 'Item B': 75, 'Item C': 125}
store2 = {'Item A': 100, 'Item B': 70, 'Item C': 80}

inventory = {}
order= 0
total = 0
total1= 0
total2 = 0

for item in store1:
	total1 += store1[item]

for item in store2:
	total2 += store2[item]
total = total1 + total2
print(f"Inventoris : {total}")
for item in store1:	
	if store1[item] <151:
		order = 150 - (store1[item])
		
		print(f"we should add more {item} : {order}")

	else:
		print(f"We do not need add more: {item}")

for item in store1:
	inventory.update({item:(store1[item]+store2[item])})
print(inventory)

store3 ={'Item A': 200, 'Item C': 100}

for item in store3:
	if item in inventory:
		inventory.update({item:(store3[item]+inventory[item])})
print(inventory)

store4 ={ 'Item B': 70, 'Item D': 150}

for item in store4:
	if item in inventory:
		inventory.update({item:(store4[item]+inventory[item])})
	else:
		inventory[item]=store4[item]

print(inventory)

   
```
</p>
</details>

<details><summary>:snake: Increment dictionary</summary>
<p>

```python
  names = {"John":0, "Steve": 0, "Bob":0, "Susan" : 0}

while True:
	
	user = input('enter your name(if you want to end enter stop): ')
	if user == 'stop':
		break
	if user not in names:
		names.update({user: 1})
	else:
		names.update({user: names[user] +1})
		
	print(names) 
```
</p>
</details>

<details><summary>:snake: Retrieve key and value from dictionary</summary>
<p>

```python
english_to_french={"black":"noir","green":"vert","yellow":"jaune","white":"blanc"}
'''
for color in english_to_french:
	print(color)
print()
for color in english_to_french:
	print(english_to_french[color])
input = input("enter a color: ")
print()
if input in english_to_french:
	print(english_to_french[input])
else:
	print(" I don't know")
print()
'''
'''
french_color= input("enter a french color: ")
if french_color in english_to_french.values():
	for key in english_to_french:
		if english_to_french[key] == french_color:
			print(key)
else:
	print("I don't know")
'''
count = 0
while True:
	if count == 0:
		count +=1
		color = input("enter a color: ")
	else:
		print("do you want to enter another color? ")
		bol = input()
		if bol == "yes" or bol == "Yes":
			color = input("enter a color: ")
		else:
			break
	 		
	if color in english_to_french:
		print(english_to_french[color])

	else:
		print("not in dictionary: ")

		color_fr = input("please enter the french word : ")
		english_to_french.update({color:color_fr})
		print(english_to_french)

   
```
</p>
</details>


<details><summary>:snake: Delete and append value</summary>
<p>

```python
  keys = ["Ten", "twenty","thirty"]
value = [10,20,30]
val_num = {}
for i in range(len(keys)):
    val_num[keys[i]] = value[i]
print(val_num)
more_items= {"Fourty": 40 , "Fifty": 50, "Sixty": 60}
for key in more_items:
    val_num[key] = more_items[key]
print(val_num)
# new_keys = []
# new_values = []
#
# for key in val_num:
#
#     new_keys.append(key)
#     new_values.append(val_num[key])
# print(new_keys)
# print(new_values)
#with delete value , need to make list helper to hold the keys
delete_me = [20,40]
#another solution more eficient, less time looping
delete_me_key= []
for key in val_num:
    if val_num[key] in delete_me:
        delete_me_key.append(key)
for word in delete_me_key:
    val_num.pop(word)

# for num in delete_me:
#     for key in val_num:
#         if  num == val_num[key]:
#             val_num.pop(key)
#             break
# print(val_num)
#delete_me_key = []
# for i in range(len(delete_me)):
#     for key in val_num:
#         if delete_me[i] == val_num[key] :
#             delete_me_key.append(key)
# print(delete_me_key)
# for i in range(len(delete_me_key)):
#     val_num.pop(delete_me_key[i])
# print(val_num)

#with delete key
# delete_me = ["twenty","Fourty"]
# for i in range(len(delete_me)):
#     val_num.pop(delete_me[i])
# print(val_num)

# for list in delete_me:
#     for key in val_num:
#         if list == key:
#             val_num.pop[key]
#         else:
#             print(" not in the dictionary")
#check if in the dict
# key1 =""
# key2 = ""
# for key in val_num:
#     for i in range(len(delete_me)):
#         if delete_me[i]  == val_num[key]:
#
#                 key1 = key
#         elif val_num[key] == 40:
#                 key2 = key
#         else:
#             print(" the number is not in dictionary")
# val_num.pop(key1)
# val_num.pop(key2)
#print(val_num)

 
```
</p>
</details>
<details><summary>:snake: Dictionary</summary>
<p>

```python
people = {"hn":"Harrison", "jd":"John", "ss":"Susan"}
print(people)
print(people["hn"])
print(people.get("hn"))

people["jd"] = "jerry"
print(people)

people["ar"] = "Anne"
print(people)

people.pop("hn")
print(people)

for key in people:
	print(key)
	print(people[key])

for key in people:
	if people[key] == "Susan":
		print("Susan")

		print(key)

for initials in people:
	print(initials)
	print(people[initials])

if "jerry" in people:
	print("Foo")
else: 
	print("Bar")
if "jerry" in people.values():
	print("Foo")
else: 
	print("Bar")

if "ss" in people or "ss" in people.values():
	print("Foo")
else:
	print("Bar")
   
```
</p>
</details>
