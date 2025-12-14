# Python Fundamental Practice Problems
## Building Strong Basics - One Concept at a Time

These problems focus on **one fundamental Python concept** at a time. Each concept has 3 variants that progressively build your understanding. Complete these before moving to the advanced problem list.

---

## 1. Variables and Data Types

### Problem 1.1: Simple Variable Operations
**Focus:** Understanding different data types and basic operations

**Task:**
Create a program that stores and displays information about a person:
- Store name as a string
- Store age as an integer
- Store height in meters as a float
- Store whether they are a student as a boolean
- Store their favorite colors as a list of strings (at least 3 colors)

**Requirements:**
- Print each variable with a descriptive label
- Use `type()` function to display the data type of each variable
- Calculate and display: age in months (age * 12)
- Calculate and display: height in centimeters (height * 100)
- Format the output nicely with labels

**Example Output:**
```
Name: John Doe (type: <class 'str'>)
Age: 25 years (300 months) (type: <class 'int'>)
Height: 1.75 meters (175.0 cm) (type: <class 'float'>)
Is Student: True (type: <class 'bool'>)
Favorite Colors: ['Blue', 'Green', 'Red'] (type: <class 'list'>)
```

---

### Problem 1.2: Type Conversion Practice
**Focus:** Converting between different data types

**Task:**
Create a program that demonstrates type conversions:
- Ask user for input (or use hardcoded values):
  - A number as string: "42"
  - A decimal as string: "3.14"
  - A boolean as string: "True"
  - A number: 100
  - A decimal: 5.7

**Requirements:**
- Convert string "42" to integer and display
- Convert string "3.14" to float and display
- Convert string "True" to boolean and display
- Convert integer 100 to string and display
- Convert float 5.7 to integer (what happens?) and display
- Convert integer 100 to float and display
- Perform operations: add the converted integer and float
- Display all conversions with explanations

**Example Output:**
```
Original: "42" (string) -> Converted: 42 (integer)
Original: "3.14" (string) -> Converted: 3.14 (float)
Original: "True" (string) -> Converted: True (boolean)
Original: 100 (integer) -> Converted: "100" (string)
Original: 5.7 (float) -> Converted: 5 (integer) - Note: decimal part removed
Sum of 42 + 3.14 = 45.14
```

---

### Problem 1.3: Variable Swapping and Multiple Assignment
**Focus:** Understanding variable assignment and swapping

**Task:**
Create a program that demonstrates variable operations:
- Initialize three variables: a = 10, b = 20, c = 30
- Swap values: a and b (using temporary variable)
- Swap values: b and c (using Python's tuple unpacking method)
- Use multiple assignment to set: x, y, z = 1, 2, 3
- Swap x and y using tuple unpacking (no temporary variable)

**Requirements:**
- Display values before and after each swap
- Show both methods: temporary variable method and tuple unpacking
- Demonstrate multiple assignment with 3+ variables
- Calculate and display: sum of all variables after swaps
- Create a scenario: swap first and last items in a list [1, 2, 3, 4, 5]

**Example Output:**
```
Initial values: a=10, b=20, c=30
After swapping a and b (temp method): a=20, b=10, c=30
After swapping b and c (tuple method): a=20, b=30, c=10
Multiple assignment: x=1, y=2, z=3
After swapping x and y: x=2, y=1, z=3
Sum of all: 20 + 30 + 10 + 2 + 1 + 3 = 66
```

---

## 2. Lists

### Problem 2.1: Basic List Operations
**Focus:** Creating, accessing, and modifying lists

**Task:**
Create a program that works with a shopping list:
- Create a list with 5 items: ["Bread", "Milk", "Eggs", "Butter", "Cheese"]
- Display the entire list
- Display the first item (index 0)
- Display the last item (using negative index)
- Display items from index 1 to 3 (slicing)
- Add "Apples" to the end of the list
- Insert "Bananas" at index 2
- Remove "Butter" from the list
- Display the updated list

**Requirements:**
- Use `append()` to add item
- Use `insert()` to add at specific position
- Use `remove()` to remove by value
- Use `len()` to display list length
- Display list before and after each operation

**Example Output:**
```
Original list: ['Bread', 'Milk', 'Eggs', 'Butter', 'Cheese']
First item: Bread
Last item: Cheese
Items 1-3: ['Milk', 'Eggs', 'Butter']
After adding 'Apples': ['Bread', 'Milk', 'Eggs', 'Butter', 'Cheese', 'Apples']
After inserting 'Bananas' at index 2: ['Bread', 'Milk', 'Bananas', 'Eggs', 'Butter', 'Cheese', 'Apples']
After removing 'Butter': ['Bread', 'Milk', 'Bananas', 'Eggs', 'Cheese', 'Apples']
Final list length: 6
```

---

### Problem 2.2: List Methods and Operations
**Focus:** Using list methods (sort, reverse, count, index)

**Task:**
Create a program that demonstrates list methods:
- Create a list of numbers: [5, 2, 8, 1, 9, 3, 5, 2, 7]
- Create a list of names: ["Alice", "Bob", "Charlie", "Alice", "David"]

**Requirements:**
- Sort the numbers list (ascending) and display
- Reverse the sorted list and display
- Count how many times 5 appears in numbers list
- Find the index of first occurrence of 2 in numbers list
- Count how many times "Alice" appears in names list
- Find index of "Charlie" in names list
- Remove duplicates from numbers (convert to set and back, or use loop)
- Display all results with explanations

**Example Output:**
```
Original numbers: [5, 2, 8, 1, 9, 3, 5, 2, 7]
Sorted (ascending): [1, 2, 2, 3, 5, 5, 7, 8, 9]
Reversed: [9, 8, 7, 5, 5, 3, 2, 2, 1]
Count of 5: 2 times
Index of first 2: 1
Names list: ['Alice', 'Bob', 'Charlie', 'Alice', 'David']
Count of 'Alice': 2 times
Index of 'Charlie': 2
Numbers without duplicates: [1, 2, 3, 5, 7, 8, 9]
```

---

### Problem 2.3: List Slicing and Advanced Operations
**Focus:** Slicing, copying, and combining lists

**Task:**
Create a program that demonstrates advanced list operations:
- Create list: [10, 20, 30, 40, 50, 60, 70, 80, 90, 100]
- Create another list: [1, 2, 3]

**Requirements:**
- Display first 3 elements using slicing
- Display last 3 elements using slicing
- Display every 2nd element (step slicing: [::2])
- Display elements in reverse order using slicing
- Create a copy of the list (not reference)
- Combine both lists using `+` operator
- Extend first list with second list using `extend()`
- Display all results with clear labels

**Example Output:**
```
Original list: [10, 20, 30, 40, 50, 60, 70, 80, 90, 100]
First 3 elements: [10, 20, 30]
Last 3 elements: [80, 90, 100]
Every 2nd element: [10, 30, 50, 70, 90]
Reversed: [100, 90, 80, 70, 60, 50, 40, 30, 20, 10]
Copy of list: [10, 20, 30, 40, 50, 60, 70, 80, 90, 100]
Combined with +: [10, 20, 30, 40, 50, 60, 70, 80, 90, 100, 1, 2, 3]
After extend: [10, 20, 30, 40, 50, 60, 70, 80, 90, 100, 1, 2, 3]
```

---

## 3. Dictionaries

### Problem 3.1: Creating and Accessing Dictionaries
**Focus:** Basic dictionary operations

**Task:**
Create a program that works with a student's information:
- Create a dictionary with:
  - "name": "John Doe"
  - "age": 20
  - "grade": "A"
  - "subjects": ["Math", "Science", "English"]

**Requirements:**
- Display the entire dictionary
- Access and display each value using keys
- Display all keys using `.keys()`
- Display all values using `.values()`
- Display all key-value pairs using `.items()`
- Add a new key "school" with value "High School"
- Update "age" to 21
- Check if "grade" key exists using `in` operator
- Display the number of key-value pairs using `len()`

**Example Output:**
```
Student Info: {'name': 'John Doe', 'age': 20, 'grade': 'A', 'subjects': ['Math', 'Science', 'English']}
Name: John Doe
Age: 20
Grade: A
Subjects: ['Math', 'Science', 'English']
Keys: dict_keys(['name', 'age', 'grade', 'subjects'])
Values: dict_values(['John Doe', 20, 'A', ['Math', 'Science', 'English']])
Items: dict_items([('name', 'John Doe'), ('age', 20), ...])
After adding 'school': {'name': 'John Doe', 'age': 21, 'grade': 'A', 'subjects': [...], 'school': 'High School'}
'grade' exists: True
Number of keys: 5
```

---

### Problem 3.2: Dictionary Methods and Operations
**Focus:** Using dictionary methods (get, pop, update, clear)

**Task:**
Create a program that demonstrates dictionary methods:
- Create dictionary: {"apple": 5, "banana": 3, "orange": 8, "grape": 12}

**Requirements:**
- Use `.get("apple")` to get value (safe method)
- Use `.get("mango", 0)` to get value with default (key doesn't exist)
- Use `.pop("banana")` to remove and return value
- Display dictionary after pop
- Use `.update()` to add multiple items: {"mango": 6, "kiwi": 4}
- Use `.popitem()` to remove last item (Python 3.7+)
- Create a copy using `.copy()`
- Use `.clear()` on the copy (not original)
- Display all results with explanations

**Example Output:**
```
Original: {'apple': 5, 'banana': 3, 'orange': 8, 'grape': 12}
Get 'apple': 5
Get 'mango' (doesn't exist, default 0): 0
Pop 'banana': 3
After pop: {'apple': 5, 'orange': 8, 'grape': 12}
After update: {'apple': 5, 'orange': 8, 'grape': 12, 'mango': 6, 'kiwi': 4}
Popitem (last item): ('kiwi', 4)
After popitem: {'apple': 5, 'orange': 8, 'grape': 12, 'mango': 6}
Copy cleared, original unchanged: {'apple': 5, 'orange': 8, 'grape': 12, 'mango': 6}
```

---

### Problem 3.3: Nested Dictionaries and Advanced Operations
**Focus:** Working with nested dictionaries

**Task:**
Create a program that works with nested dictionary structure:
- Create a dictionary of students:
  ```python
  {
      "student1": {"name": "Alice", "age": 20, "grades": [85, 90, 88]},
      "student2": {"name": "Bob", "age": 21, "grades": [78, 82, 80]},
      "student3": {"name": "Charlie", "age": 19, "grades": [92, 95, 90]}
  }
  ```

**Requirements:**
- Access and display each student's name
- Access and display each student's age
- Calculate and display average grade for each student
- Add a new student "student4" with name "Diana", age 20, grades [88, 85, 87]
- Update student1's age to 21
- Add a new key "school" to student2 with value "University"
- Display all student names in a list
- Display student with highest average grade

**Example Output:**
```
Student 1: Alice, Age: 20, Average Grade: 87.67
Student 2: Bob, Age: 21, Average Grade: 80.0
Student 3: Charlie, Age: 19, Average Grade: 92.33
After adding student4: Diana, Age: 20, Average Grade: 86.67
After updating student1 age: 21
Student2 now has 'school': University
All student names: ['Alice', 'Bob', 'Charlie', 'Diana']
Highest average: Charlie with 92.33
```

---

## 4. Tuples

### Problem 4.1: Basic Tuple Operations
**Focus:** Understanding tuples and immutability

**Task:**
Create a program that demonstrates tuple basics:
- Create a tuple: (10, 20, 30, 40, 50)
- Create a tuple with mixed types: ("apple", 5, 3.14, True)
- Create a single-element tuple (note the comma)

**Requirements:**
- Display each tuple
- Access elements by index (first, last, middle)
- Use slicing on tuple
- Try to modify a tuple (show that it raises TypeError)
- Convert tuple to list, modify, convert back to tuple
- Display length of tuple using `len()`
- Check if value exists using `in` operator
- Count occurrences of a value using `.count()`

**Example Output:**
```
Tuple 1: (10, 20, 30, 40, 50)
First element: 10
Last element: 50
Middle elements (slice): (20, 30, 40)
Mixed tuple: ('apple', 5, 3.14, True)
Single element tuple: (42,)
Length: 5
Is 30 in tuple? True
Count of 20: 1
Cannot modify tuple directly (immutable)
After converting to list, modifying, and back: (10, 20, 35, 40, 50)
```

---

### Problem 4.2: Tuple Packing and Unpacking
**Focus:** Packing and unpacking tuples

**Task:**
Create a program that demonstrates tuple packing and unpacking:
- Pack three values into a tuple: name, age, city
- Unpack the tuple into three separate variables
- Create a function that returns multiple values (as tuple)
- Unpack function return values
- Swap two variables using tuple unpacking
- Unpack with asterisk for remaining values

**Requirements:**
- Demonstrate packing: `person = ("John", 25, "New York")`
- Demonstrate unpacking: `name, age, city = person`
- Create function `get_coordinates()` that returns (x, y)
- Unpack function return: `x, y = get_coordinates()`
- Swap: `a, b = 10, 20` then `a, b = b, a`
- Extended unpacking: `first, *middle, last = (1, 2, 3, 4, 5)`

**Example Output:**
```
Packed tuple: ('John', 25, 'New York')
Unpacked: name=John, age=25, city=New York
Function returns: (10, 20)
Unpacked coordinates: x=10, y=20
Before swap: a=10, b=20
After swap: a=20, b=10
Extended unpacking: first=1, middle=[2, 3, 4], last=5
```

---

### Problem 4.3: Tuple Operations and Use Cases
**Focus:** Practical tuple usage

**Task:**
Create a program that uses tuples for:
- Coordinates: (x, y) points
- RGB colors: (red, green, blue) values
- Date: (year, month, day)

**Requirements:**
- Create list of coordinate tuples: [(0, 0), (3, 4), (5, 12), (8, 15)]
- Calculate distance from origin (0, 0) for each point using formula: √(x² + y²)
- Create RGB color tuples: red=(255, 0, 0), green=(0, 255, 0), blue=(0, 0, 255)
- Mix colors by averaging RGB values
- Create date tuples: (2024, 1, 15), (2024, 12, 25)
- Compare dates (which comes first?)
- Display all results

**Example Output:**
```
Coordinates: [(0, 0), (3, 4), (5, 12), (8, 15)]
Distance from origin:
  (0, 0): 0.0
  (3, 4): 5.0
  (5, 12): 13.0
  (8, 15): 17.0
RGB Colors:
  Red: (255, 0, 0)
  Green: (0, 255, 0)
  Blue: (0, 0, 255)
Mixed (red + green): (127, 127, 0) - Yellow
Date 1: (2024, 1, 15)
Date 2: (2024, 12, 25)
Date 1 comes before Date 2: True
```

---

## 5. Sets

### Problem 5.1: Basic Set Operations
**Focus:** Creating and basic set operations

**Task:**
Create a program that demonstrates set basics:
- Create a set: {1, 2, 3, 4, 5}
- Create a set from a list with duplicates: [1, 2, 2, 3, 3, 3, 4, 5]
- Create an empty set (not `{}` which is a dict)

**Requirements:**
- Display each set
- Add element 6 to the set
- Remove element 3 from the set
- Check if 5 is in the set using `in`
- Display set length using `len()`
- Try adding duplicate (show it doesn't change set)
- Clear the set using `.clear()`
- Display all operations with explanations

**Example Output:**
```
Set 1: {1, 2, 3, 4, 5}
Set from list (duplicates removed): {1, 2, 3, 4, 5}
Empty set: set()
After adding 6: {1, 2, 3, 4, 5, 6}
After removing 3: {1, 2, 4, 5, 6}
Is 5 in set? True
Length: 5
Adding duplicate 2 (no change): {1, 2, 4, 5, 6}
After clear: set()
```

---

### Problem 5.2: Set Operations (Union, Intersection, Difference)
**Focus:** Set mathematical operations

**Task:**
Create a program that demonstrates set operations:
- Create two sets:
  - set1 = {1, 2, 3, 4, 5}
  - set2 = {4, 5, 6, 7, 8}

**Requirements:**
- Union: combine both sets (all unique elements)
- Intersection: common elements
- Difference: elements in set1 but not in set2
- Symmetric difference: elements in either set but not both
- Check if set1 is subset of set2 using `.issubset()`
- Check if set1 is superset using `.issuperset()`
- Display all results with clear labels

**Example Output:**
```
Set 1: {1, 2, 3, 4, 5}
Set 2: {4, 5, 6, 7, 8}
Union (all elements): {1, 2, 3, 4, 5, 6, 7, 8}
Intersection (common): {4, 5}
Difference (set1 - set2): {1, 2, 3}
Symmetric Difference (either but not both): {1, 2, 3, 6, 7, 8}
Is set1 subset of set2? False
Is {4, 5} subset of set1? True
```

---

### Problem 5.3: Practical Set Applications
**Focus:** Using sets for real-world problems

**Task:**
Create a program that uses sets to solve problems:
- Two groups of students:
  - Math class: {"Alice", "Bob", "Charlie", "Diana"}
  - Science class: {"Bob", "Diana", "Eve", "Frank"}

**Requirements:**
- Find students in both classes (intersection)
- Find students only in Math class
- Find students only in Science class
- Find all unique students (union)
- Find students in exactly one class (symmetric difference)
- Check if "Alice" is in Math class
- Add a new student "George" to Math class
- Remove "Frank" from Science class
- Display all results

**Example Output:**
```
Math class: {'Alice', 'Bob', 'Charlie', 'Diana'}
Science class: {'Bob', 'Diana', 'Eve', 'Frank'}
In both classes: {'Bob', 'Diana'}
Only in Math: {'Alice', 'Charlie'}
Only in Science: {'Eve', 'Frank'}
All students: {'Alice', 'Bob', 'Charlie', 'Diana', 'Eve', 'Frank'}
In exactly one class: {'Alice', 'Charlie', 'Eve', 'Frank'}
Is Alice in Math? True
After adding George to Math: {'Alice', 'Bob', 'Charlie', 'Diana', 'George'}
After removing Frank from Science: {'Bob', 'Diana', 'Eve'}
```

---

## 6. Strings and String Manipulation

### Problem 6.1: Basic String Operations
**Focus:** String methods and basic operations

**Task:**
Create a program that demonstrates string operations:
- Create strings: "Hello World", "python programming", "  SPACES  "

**Requirements:**
- Convert to uppercase using `.upper()`
- Convert to lowercase using `.lower()`
- Capitalize first letter using `.capitalize()`
- Title case using `.title()`
- Remove leading/trailing spaces using `.strip()`
- Replace "World" with "Python" using `.replace()`
- Split string into words using `.split()`
- Join list of words using `.join()`
- Check if string starts with "Hello" using `.startswith()`
- Check if string ends with "ing" using `.endswith()`

**Example Output:**
```
Original: "Hello World"
Uppercase: HELLO WORLD
Lowercase: hello world
Capitalize: Hello world
Title: Hello World
Strip spaces: "  SPACES  " -> "SPACES"
Replace: Hello Python
Split: ['Hello', 'World']
Join: Hello-World-Python
Starts with 'Hello': True
Ends with 'ing': False (for "python programming": True)
```

---

### Problem 6.2: String Formatting and Slicing
**Focus:** String formatting methods and slicing

**Task:**
Create a program that demonstrates string formatting:
- Variables: name = "John", age = 25, score = 87.5

**Requirements:**
- Format using `.format()`: "My name is {} and I am {} years old"
- Format using f-strings: f"My name is {name}..."
- Format with precision: display score with 2 decimals
- String slicing: extract first 5 characters
- String slicing: extract last 5 characters
- String slicing: reverse a string using slicing
- String slicing: get every 2nd character
- Check if substring exists using `in`
- Find index of substring using `.find()`
- Count occurrences using `.count()`

**Example Output:**
```
Using .format(): My name is John and I am 25 years old
Using f-string: My name is John and I am 25 years old. My score is 87.50
First 5 chars of "Hello World": Hello
Last 5 chars: World
Reversed: dlroW olleH
Every 2nd char: HloWrd
Is "World" in string? True
Index of "World": 6
Count of 'l': 3
```

---

### Problem 6.3: Advanced String Manipulation
**Focus:** Complex string operations

**Task:**
Create a program that processes text:
- String: "Python is a great programming language. Python is versatile."

**Requirements:**
- Count total words in the string
- Find longest word
- Find shortest word
- Count occurrences of "Python"
- Replace all "Python" with "Java"
- Split into sentences (split by period)
- Remove all vowels from string
- Check if string is alphanumeric using `.isalnum()`
- Check if all characters are letters using `.isalpha()`
- Check if all characters are digits using `.isdigit()`
- Reverse each word in the string

**Example Output:**
```
Original: "Python is a great programming language. Python is versatile."
Total words: 9
Longest word: programming (11 characters)
Shortest word: a (1 character)
Occurrences of 'Python': 2
After replace: "Java is a great programming language. Java is versatile."
Sentences: ['Python is a great programming language', ' Python is versatile', '']
Without vowels: "Pythn s  grt prgrmmng lngg. Pythn s vrsatl."
Is alphanumeric? False (has spaces and punctuation)
Reverse each word: "nohtyP si a taerg gnimmargorp .egaugnal nohtyP si .elbisrev"
```

---

## 7. If-Else Statements (Control Flow)

### Problem 7.1: Basic If-Else Conditions
**Focus:** Simple conditional statements

**Task:**
Create a program that uses if-else for decision making:
- Variables: age = 20, temperature = 25, score = 85

**Requirements:**
- Check if age >= 18, print "Adult" else "Minor"
- Check if temperature > 30, print "Hot", else if > 20 print "Warm", else "Cold"
- Check if score >= 90, print "A", else if >= 80 print "B", else if >= 70 print "C", else "F"
- Check if number is positive, negative, or zero
- Check if year is leap year (divisible by 4, but not 100 unless also 400)
- Display all results with clear labels

**Example Output:**
```
Age 20: Adult
Temperature 25: Warm
Score 85: Grade B
Number 10: Positive
Number -5: Negative
Number 0: Zero
Year 2024: Leap year
Year 2023: Not a leap year
```

---

### Problem 7.2: Multiple Conditions and Logical Operators
**Focus:** Using and, or, not operators

**Task:**
Create a program that uses logical operators:
- Variables: age = 25, has_license = True, has_car = False, balance = 150

**Requirements:**
- Check if person can drive: age >= 18 AND has_license
- Check if person can buy car: age >= 18 AND balance >= 1000 OR has_car
- Check if person is teenager: age >= 13 AND age <= 19
- Check if number is between 10 and 20 (inclusive)
- Check if string is not empty AND length > 5
- Use NOT operator to check opposite conditions
- Display all results with explanations

**Example Output:**
```
Age: 25, Has License: True
Can drive? True (age >= 18 AND has_license)
Can buy car? False (needs age >= 18 AND balance >= 1000 OR has_car)
Is teenager? False (age must be 13-19)
Number 15 between 10-20? True
String "Hello" not empty and length > 5? False (length is 5, not > 5)
NOT can drive? False
```

---

### Problem 7.3: Nested If-Else and Complex Conditions
**Focus:** Nested conditions and complex logic

**Task:**
Create a program with nested conditions:
- Variables: weather = "sunny", temperature = 25, is_weekend = True

**Requirements:**
- Determine activity:
  - If weekend AND sunny: "Go to beach"
  - Else if weekend AND not sunny: "Stay home and read"
  - Else if not weekend AND sunny: "Go for a walk after work"
  - Else: "Stay indoors"
- Determine clothing:
  - If temperature > 30: "Wear light clothes"
  - Else if temperature > 20: "Wear normal clothes"
  - Else if temperature > 10: "Wear jacket"
  - Else: "Wear heavy coat"
- Check password strength (length >= 8 AND has uppercase AND has digit)
- Display all decisions

**Example Output:**
```
Weather: sunny, Temperature: 25, Weekend: True
Activity: Go to beach
Clothing: Wear normal clothes
Password "MyPass123": Strong (length >= 8, has uppercase, has digit)
Password "weak": Weak (doesn't meet all criteria)
```

---

## 8. Loops (For and While)

### Problem 8.1: Basic For Loops
**Focus:** Iterating with for loops

**Task:**
Create a program that demonstrates for loops:
- List: [1, 2, 3, 4, 5]
- String: "Python"
- Range: range(1, 11)

**Requirements:**
- Loop through list and print each number
- Loop through string and print each character
- Loop through range and print numbers 1-10
- Calculate sum of numbers 1-10 using loop
- Print multiplication table for 5 (5 x 1 = 5, 5 x 2 = 10, ...)
- Loop through list and print index and value using `enumerate()`
- Display all results

**Example Output:**
```
Looping through list: 1 2 3 4 5
Looping through string: P y t h o n
Numbers 1-10: 1 2 3 4 5 6 7 8 9 10
Sum of 1-10: 55
Multiplication table for 5:
  5 x 1 = 5
  5 x 2 = 10
  ...
  5 x 10 = 50
With enumerate: (0, 1) (1, 2) (2, 3) (3, 4) (4, 5)
```

---

### Problem 8.2: While Loops and Loop Control
**Focus:** While loops, break, continue

**Task:**
Create a program that demonstrates while loops:
- Counter from 1 to 10
- User input validation (simulate with hardcoded attempts)
- Finding first number divisible by 7

**Requirements:**
- Use while loop to count from 1 to 10
- Use while loop with condition to keep asking until valid input (simulate)
- Use while True with break to find first number divisible by 7 in range 1-100
- Use continue to skip even numbers and print only odds
- Use while loop to calculate factorial of 5 (5! = 5 × 4 × 3 × 2 × 1)
- Display all results

**Example Output:**
```
While loop count: 1 2 3 4 5 6 7 8 9 10
Input validation (simulated):
  Attempt 1: Invalid, trying again...
  Attempt 2: Valid input received!
First number divisible by 7: 7
Odd numbers only: 1 3 5 7 9 11 13 ...
Factorial of 5: 120
```

---

### Problem 8.3: Nested Loops and Advanced Iteration
**Focus:** Nested loops and complex iterations

**Task:**
Create a program that uses nested loops:
- Print pattern: 
  ```
  *
  **
  ***
  ****
  *****
  ```
- Create multiplication table (1-5)
- Find all pairs in list that sum to 10: [1, 2, 3, 4, 5, 6, 7, 8, 9]

**Requirements:**
- Use nested for loops to print star pattern
- Use nested loops to create 5x5 multiplication table
- Use nested loops to find pairs that sum to target
- Loop through 2D list (list of lists) and print all elements
- Use loop with zip() to iterate through two lists simultaneously
- Display all results

**Example Output:**
```
Star pattern:
*
**
***
****
*****

Multiplication table:
  1  2  3  4  5
  2  4  6  8 10
  3  6  9 12 15
  4  8 12 16 20
  5 10 15 20 25

Pairs that sum to 10: (1, 9), (2, 8), (3, 7), (4, 6), (5, 5)
2D list elements: 1 2 3 4 5 6
Using zip: (1, 'a') (2, 'b') (3, 'c')
```

---

## 9. Functions

### Problem 9.1: Basic Function Definition and Calling
**Focus:** Creating and calling simple functions

**Task:**
Create a program with basic functions:
- Function to greet a person
- Function to add two numbers
- Function to calculate area of rectangle

**Requirements:**
- Create `greet(name)` function that takes name and prints greeting
- Create `add(a, b)` function that returns sum of two numbers
- Create `calculate_area(length, width)` function that returns area
- Call each function with different arguments
- Create function with default parameter: `multiply(a, b=2)` where b defaults to 2
- Display all function results

**Example Output:**
```
greet("Alice"): Hello, Alice! Nice to meet you.
add(5, 3): 8
calculate_area(5, 4): 20
multiply(5): 10 (using default b=2)
multiply(5, 3): 15 (using provided b=3)
```

---

### Problem 9.2: Function Parameters and Return Values
**Focus:** Different parameter types and return values

**Task:**
Create a program with various function types:
- Function that returns multiple values
- Function with variable arguments (*args)
- Function with keyword arguments

**Requirements:**
- Create `get_name_age()` that returns (name, age) as tuple
- Create `sum_numbers(*args)` that accepts any number of arguments and returns sum
- Create `create_profile(name, age, **kwargs)` that accepts name, age, and any other keyword arguments
- Unpack return values from function
- Call functions with different argument types
- Display all results

**Example Output:**
```
get_name_age(): ('John', 25)
Unpacked: name=John, age=25
sum_numbers(1, 2, 3): 6
sum_numbers(10, 20, 30, 40): 100
create_profile("Alice", 30, city="NYC", job="Engineer"):
  Name: Alice, Age: 30, City: NYC, Job: Engineer
```

---

### Problem 9.3: Function Scope and Advanced Concepts
**Focus:** Local vs global scope, lambda functions

**Task:**
Create a program that demonstrates:
- Global and local variables
- Lambda functions
- Functions as arguments

**Requirements:**
- Create global variable `count = 0`
- Create function that modifies global variable using `global` keyword
- Create function with local variable (same name as global)
- Create lambda function to square a number: `square = lambda x: x**2`
- Create lambda function to add two numbers
- Create `apply_operation(a, b, operation)` that takes function as parameter
- Pass lambda functions to `apply_operation`
- Display all results

**Example Output:**
```
Global count: 0
After increment_global(): 1
Local variable example: global=0, local=10
Lambda square(5): 25
Lambda add(3, 4): 7
apply_operation(10, 5, lambda x, y: x + y): 15
apply_operation(10, 5, lambda x, y: x * y): 50
```

---

## 10. List Comprehensions

### Problem 10.1: Basic List Comprehensions
**Focus:** Simple list comprehension syntax

**Task:**
Create a program that converts loops to list comprehensions:
- Square numbers 1-10
- Extract first letter of words
- Filter even numbers

**Requirements:**
- Using loop: create list of squares [1, 4, 9, 16, ...]
- Convert to list comprehension: `[x**2 for x in range(1, 11)]`
- Using loop: extract first letters from ["apple", "banana", "cherry"]
- Convert to list comprehension: `[word[0] for word in words]`
- Using loop: filter even numbers from [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
- Convert to list comprehension: `[x for x in numbers if x % 2 == 0]`
- Show both loop and comprehension versions

**Example Output:**
```
Squares (loop): [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
Squares (comprehension): [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
First letters (loop): ['a', 'b', 'c']
First letters (comprehension): ['a', 'b', 'c']
Even numbers (loop): [2, 4, 6, 8, 10]
Even numbers (comprehension): [2, 4, 6, 8, 10]
```

---

### Problem 10.2: List Comprehensions with Conditions
**Focus:** Comprehensions with if conditions

**Task:**
Create a program with conditional list comprehensions:
- Filter and transform data
- Multiple conditions

**Requirements:**
- Create list of numbers 1-20, filter multiples of 3: `[x for x in range(1, 21) if x % 3 == 0]`
- Create list of words, filter words longer than 5 characters: `[word for word in words if len(word) > 5]`
- Create list of numbers, square only even numbers: `[x**2 for x in range(1, 11) if x % 2 == 0]`
- Create list comprehension with if-else: `["Even" if x % 2 == 0 else "Odd" for x in range(1, 11)]`
- Filter numbers between 10 and 20: `[x for x in range(1, 31) if 10 <= x <= 20]`
- Display all results

**Example Output:**
```
Multiples of 3: [3, 6, 9, 12, 15, 18]
Words longer than 5: ['banana', 'cherry']
Squares of evens: [4, 16, 36, 64, 100]
Even/Odd labels: ['Odd', 'Even', 'Odd', 'Even', ...]
Numbers 10-20: [10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20]
```

---

### Problem 10.3: Nested List Comprehensions
**Focus:** Complex list comprehensions

**Task:**
Create a program with nested comprehensions:
- Flatten 2D list
- Create multiplication table
- Nested conditions

**Requirements:**
- Flatten 2D list: `[[1, 2, 3], [4, 5, 6], [7, 8, 9]]` to `[1, 2, 3, 4, 5, 6, 7, 8, 9]`
  - Comprehension: `[item for sublist in matrix for item in sublist]`
- Create 5x5 multiplication table using nested comprehension
- Create list of tuples: `[(x, y) for x in range(3) for y in range(3)]`
- Filter nested structure: find all numbers > 5 in 2D list
- Display all results

**Example Output:**
```
2D list: [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
Flattened: [1, 2, 3, 4, 5, 6, 7, 8, 9]
Multiplication table: [[1, 2, 3, 4, 5], [2, 4, 6, 8, 10], ...]
Coordinate pairs: [(0, 0), (0, 1), (0, 2), (1, 0), (1, 1), ...]
Numbers > 5: [6, 7, 8, 9]
```

---

## 11. Error Handling (Try-Except)

### Problem 11.1: Basic Try-Except Blocks
**Focus:** Catching and handling errors

**Task:**
Create a program that handles common errors:
- Division by zero
- Invalid type conversion
- Index out of range

**Requirements:**
- Try to divide by zero, catch ZeroDivisionError
- Try to convert "abc" to int, catch ValueError
- Try to access list index that doesn't exist, catch IndexError
- Try to access dictionary key that doesn't exist, catch KeyError
- Display error messages in user-friendly way
- Use else clause to execute code when no error occurs
- Display all scenarios

**Example Output:**
```
Dividing 10 by 0: Error - Cannot divide by zero
Converting "abc" to int: Error - Invalid literal for int()
Accessing list[10] (list has 5 items): Error - List index out of range
Accessing dict['missing_key']: Error - Key 'missing_key' not found
Successful division 10/2: 5.0 (no errors)
```

---

### Problem 11.2: Multiple Exception Handling
**Focus:** Handling different exception types

**Task:**
Create a program that handles multiple exception types:
- Function that can raise different errors
- Handle each error type specifically

**Requirements:**
- Create function `safe_divide(a, b)` that handles division
- Create function `get_list_item(lst, index)` that handles index errors
- Create function `convert_to_int(value)` that handles conversion errors
- Use multiple except blocks for different errors
- Use single except with multiple exception types: `except (ValueError, TypeError)`
- Use `except Exception as e` to catch any error and print error message
- Display all scenarios

**Example Output:**
```
safe_divide(10, 2): 5.0
safe_divide(10, 0): Error - Division by zero
safe_divide(10, "2"): Error - Unsupported operand type
get_list_item([1, 2, 3], 1): 2
get_list_item([1, 2, 3], 10): Error - Index out of range
convert_to_int("123"): 123
convert_to_int("abc"): Error - Invalid integer value
```

---

### Problem 11.3: Finally Block and Custom Exceptions
**Focus:** Finally clause and raising exceptions

**Task:**
Create a program that demonstrates:
- Finally block (always executes)
- Raising custom exceptions
- Exception chaining

**Requirements:**
- Create function with try-except-finally
- Show that finally always executes (even if error occurs)
- Create custom exception class: `class CustomError(Exception)`
- Raise custom exception in function
- Use `raise` to re-raise exception
- Create function that validates input and raises ValueError if invalid
- Display all scenarios

**Example Output:**
```
Trying to divide:
  Result: 5.0
  Finally block executed (always runs)
Trying invalid operation:
  Error occurred
  Finally block executed (always runs)
Custom exception raised: CustomError - This is a custom error
Validation function:
  Valid input "123": Success
  Invalid input "": Error - Input cannot be empty
```

---

## 12. File Handling

### Problem 12.1: Reading and Writing Files
**Focus:** Basic file operations

**Task:**
Create a program that reads and writes files:
- Write data to a file
- Read data from a file
- Append data to a file

**Requirements:**
- Write "Hello, World!" to file "output.txt" using `open()` and `write()`
- Read entire file using `read()`
- Read file line by line using `readlines()`
- Append "New line" to file using append mode
- Use `with` statement for file handling (recommended)
- Display file contents after each operation
- Handle FileNotFoundError when reading non-existent file

**Example Output:**
```
Writing to file...
File contents: Hello, World!
Appending to file...
File contents:
Hello, World!
New line
Reading line by line:
  Line 1: Hello, World!
  Line 2: New line
```

---

### Problem 12.2: Processing File Data
**Focus:** Reading and processing file content

**Task:**
Create a program that processes a text file:
- Count lines in file
- Count words in file
- Find longest line
- Write processed data to new file

**Requirements:**
- Read a text file (create sample file with multiple lines)
- Count total lines using `readlines()` or loop
- Count total words (split each line)
- Find line with maximum length
- Write statistics to new file "statistics.txt"
- Use try-except for file errors
- Display all statistics

**Example Output:**
```
Reading file: sample.txt
Total lines: 5
Total words: 25
Longest line (50 chars): This is the longest line in the file...
Statistics written to statistics.txt
```

---

### Problem 12.3: Advanced File Operations
**Focus:** CSV-like processing and file management

**Task:**
Create a program that handles structured file data:
- Read file with structured data (name, age format)
- Parse and process data
- Write formatted output

**Requirements:**
- Create file "data.txt" with format:
  ```
  John,25
  Alice,30
  Bob,22
  ```
- Read file and parse each line (split by comma)
- Store data in list of dictionaries
- Calculate average age
- Write formatted report to "report.txt"
- Use context manager (`with`) for all file operations
- Handle file errors gracefully

**Example Output:**
```
Reading data.txt...
Parsed data:
  {'name': 'John', 'age': 25}
  {'name': 'Alice', 'age': 30}
  {'name': 'Bob', 'age': 22}
Average age: 25.67
Report written to report.txt
```

---

## 13. Classes and Objects (OOP Basics)

### Problem 13.1: Basic Class Definition
**Focus:** Creating classes and objects

**Task:**
Create a simple class:
- Create `Dog` class with attributes and methods
- Create multiple objects

**Requirements:**
- Create class `Dog` with:
  - Attributes: name, age, breed
  - Method `__init__()` to initialize
  - Method `bark()` that prints "Woof!"
  - Method `get_info()` that returns dog information
- Create 3 Dog objects with different attributes
- Call methods on each object
- Display all dog information

**Example Output:**
```
Dog 1: Buddy, 3 years old, Golden Retriever
  Bark: Woof!
Dog 2: Max, 5 years old, German Shepherd
  Bark: Woof!
Dog 3: Luna, 2 years old, Labrador
  Bark: Woof!
```

---

### Problem 13.2: Class Methods and Attributes
**Focus:** Instance vs class attributes and methods

**Task:**
Create a class with both instance and class attributes:
- Create `Car` class
- Track total number of cars created

**Requirements:**
- Create class `Car` with:
  - Class attribute: `total_cars = 0` (shared by all instances)
  - Instance attributes: make, model, year
  - `__init__()` that increments `total_cars`
  - Instance method `start_engine()` that prints message
  - Class method `get_total_cars()` that returns total count
  - Method `__str__()` for string representation
- Create 3 Car objects
- Display each car's info
- Display total cars created

**Example Output:**
```
Car 1: 2020 Toyota Camry
  Starting engine: Vroom!
Car 2: 2021 Honda Civic
  Starting engine: Vroom!
Car 3: 2022 Ford Mustang
  Starting engine: Vroom!
Total cars created: 3
```

---

### Problem 13.3: Encapsulation and Properties
**Focus:** Private attributes and property decorators

**Task:**
Create a class with encapsulation:
- Create `BankAccount` class
- Protect balance with private attribute
- Use property for controlled access

**Requirements:**
- Create class `BankAccount` with:
  - Private attribute `_balance` (use underscore prefix)
  - Public method `deposit(amount)` to add money
  - Public method `withdraw(amount)` to remove money (check sufficient balance)
  - Property `balance` to get balance (read-only or controlled access)
  - Method `get_balance()` that returns balance
  - Validate amounts (must be positive)
- Create account object
- Test deposit and withdraw
- Try to access `_balance` directly (show it's possible but not recommended)
- Display all operations

**Example Output:**
```
Creating account with initial balance: 1000
Depositing 500: New balance: 1500
Withdrawing 200: New balance: 1300
Trying to withdraw 2000: Error - Insufficient funds
Current balance: 1300
Accessing _balance directly (not recommended): 1300
```

---

## Practice Tips

1. **Complete in Order:** Work through concepts sequentially
2. **Master Each Concept:** Don't move on until you're comfortable
3. **Experiment:** Try variations and modifications
4. **Read Error Messages:** They tell you what went wrong
5. **Test Edge Cases:** Try empty lists, zero values, etc.
6. **Compare Solutions:** Try solving same problem different ways
7. **Build Gradually:** Each variant builds on the previous

---

## Progress Checklist

- [ ] Variables and Data Types (3 problems)
- [ ] Lists (3 problems)
- [ ] Dictionaries (3 problems)
- [ ] Tuples (3 problems)
- [ ] Sets (3 problems)
- [ ] Strings (3 problems)
- [ ] If-Else (3 problems)
- [ ] Loops (3 problems)
- [ ] Functions (3 problems)
- [ ] List Comprehensions (3 problems)
- [ ] Error Handling (3 problems)
- [ ] File Handling (3 problems)
- [ ] Classes and Objects (3 problems)

**Total: 39 Fundamental Problems**

Once you complete all these, you'll be ready for the 20 advanced problems! 🚀

---

**Happy Learning! 🐍**

