# python
import array 
integer_number = 10
float_number = float(integer_number)

print(f"Original integer: {integer_number}")
print(f"Casted to float: {float_number}")

#TYPE() FUNCTION:
X = 5
print(type(X))   

#LIST FUNCTION:
fruits = ["apple", "banana", "cherry"]

# Access by index
print(fruits[0])  
print(fruits[-1])

# Slicing 
print(fruits[1:3]) 

numbers = [1, 2, 3]

# Loop through items
for num in numbers:
    print(num * 2)  

    #Adding items
colors = ["red", "green"]
colors = ["red", "green"]
colors.append("blue")
colors.insert(1, "yellow")  
print(colors)

#Removing Items:
nums = [10, 20, 30, 40, 50]

# Remove by value
nums.remove(30)  

# Remove by index (and get the value)
popped = nums.pop(1)  
print(nums)
#CLEAR
nums.clear()
print(nums)

#Sorting List:
numbers = [3, 1, 4, 2]

# Sort in-place (modifies original)
numbers.sort() 
print(numbers)

# Sort in descending order
numbers.sort(reverse=True)
print(numbers)

#Copying a list:
thislist = ["apple", "banana", "cherry"]
mylist = thislist.copy()
print(mylist)

# Create a list of squares
squares = [x**2 for x in range(5)] 
print(squares)

# Filter even numbers
evens = [x for x in range(10) if x % 2 == 0] 
print(evens)

# Nested list comprehension
matrix = [[1, 2], [3, 4]]
flattened = [num for row in matrix for num in row] 
print(matrix)

#TUPLE
this_tuple = ("apple", "banana", "cherry")
print(this_tuple)

#accessing the last item.
this_tuple = ("apple", "banana", "cherry")
print(this_tuple[-1])                       #negative index means last item.

#Range of index:
thistuple = ("apple", "banana", "cherry", "orange", "kiwi", "melon", "mango")
print(thistuple[2:5])   

#LOOPS
tuple1 = ("ali", "sara", "babar")
for x in tuple1:
  print(x)

#JOINING TUPLE
tuple1 = ("python is")
tuple2 = (" easy")

tuple3 = tuple1 + tuple2
print(tuple3)

#UPDATE:
x = ("dog", "cat", "rabit")
y = list(x)
y[1] = "hen"
y.append(" Pigeons")
x = tuple(y)
print(x)

#UNPACKING:
animals = ("lion", "cow", "camel")

(lion, cow, camel) = animals

print(lion)
print(cow)
print(camel)
 
 #SETS:
fruits = {'apple', 'banana'}
fruits.add('orange')
print(fruits)

#UPDATE
fruits.update(['mango'])
print(fruits)

#REMOVE
fruits.remove('orange')
print(fruits)

#POP
numbers = {1, 2, 3}
popped = numbers.pop()
print(popped)  
print(numbers)

#CLEAR
numbers.clear()
print(numbers)

#ARRAY
int_array = array.array('i', [1, 2, 3, 4, 5])
print(int_array)
float_array = array.array('f', [1.5, 2.5, 3.5])
print(float_array)

#METHODS
print(int_array[0])
print(int_array[1:3]) 
int_array[0] = 10
print(int_array) 
print(len(int_array))
int_array.append(6)
print(int_array) 
int_array.remove(3)
print(int_array)

import random
import math

print(math.sqrt(16))  # Output: 4.0 (square root)
print(math.pi)        # Output: 3.141592653589793 (value of pi)

print(math.factorial(5)) 

# Generate a random integer between 1 and 10
random_num = random.randint(1, 10)
print(random_num)  

# Shuffle
my_list = [1, 2, 3, 4, 5]
random.shuffle(my_list)
print(my_list)  


def shopping_list_manager():
    # Initialize the shopping list
    shopping_list = ["Mill", "Bread", "Eggs", "Butter", "Juice", 
                    "Sugar", "Salt", "Biscuit", "Tea", "Coffee"]
    
    def display_list():
        print("\nShopping List:")
        if not shopping_list:
            print("(Empty)")
        else:
            for i, item in enumerate(shopping_list, 1):
                print(f"{i}. {item}")
    
    # Display initial list
    display_list()
    
    # Add items phase
    while True:
        choice = input("\nAdd an item? (yes/no): ").lower().strip()
        if choice == 'yes':
            new_item = input("Item to add: ").strip().capitalize()
            if not new_item:
                print("Please enter a valid item name.")
                continue
                
            if new_item in shopping_list:
                print(f"'{new_item}' is already in your list!")
            else:
                shopping_list.append(new_item)
                print(f"'{new_item}' added!")
                display_list()
        elif choice == 'no':
            break
        else:
            print("Please answer 'yes' or 'no'.")
    
    # Remove items phase (improved)
    while True:
        if not shopping_list:
            print("\nYour shopping list is empty - nothing to remove!")
            break
            
        display_list()
        choice = input("\nRemove an item? (yes/no): ").lower().strip()
        if choice == 'yes':
            print("\nOptions:")
            print("1. Remove by item name")
            print("2. Remove by item number")
            print("3. Cancel")
            
            method = input("Choose removal method (1-3): ").strip()
            
            if method == '1':
                item_to_remove = input("Enter item name to remove: ").strip().capitalize()
                if item_to_remove in shopping_list:
                    shopping_list.remove(item_to_remove)
                    print(f"'{item_to_remove}' removed!")
                else:
                    print(f"'{item_to_remove}' not found in list!")
                    
            elif method == '2':
                try:
                    item_num = int(input("Enter item number to remove: "))
                    if 1 <= item_num <= len(shopping_list):
                        removed_item = shopping_list.pop(item_num - 1)
                        print(f"'{removed_item}' removed!")
                    else:
                        print("Invalid item number!")
                except ValueError:
                    print("Please enter a valid number!")
                    
            elif method == '3':
                continue
            else:
                print("Invalid option!")
                
        elif choice == 'no':
            break
        else:
            print("Please answer 'yes' or 'no'.")
    
    # Final display
    print("\n--- Final Shopping List ---")
    display_list()

# Call the function
shopping_list_manager()

#ODD EVEN FUNCTION:
def check_even_odd():
    num = int(input("Enter a number: "))
    # Check if number is even or odd
    if num % 2 == 0:
        print(f"{num} is an even number")
    else:
        print(f"{num} is an odd number")

# Call the function
check_even_odd()
