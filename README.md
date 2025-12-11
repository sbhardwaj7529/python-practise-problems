# Python Practice Problems
## Implementation-Focused Exercises for Skill Building

These problems are designed to help you practice Python implementation skills using core data structures, control flow, functions, modules, OOP, and error handling. Each problem should take approximately 30 minutes to complete.

---

## Beginner Level (Warm-up)

### 1. Personal Expense Tracker
**Objective:** Create a program to track daily expenses.

**Detailed Requirements:**

**Data Structure:**
- Use a dictionary where:
  - Key: date string in format "YYYY-MM-DD" (e.g., "2024-01-15")
  - Value: list of dictionaries, each containing:
    - "description": string (e.g., "Groceries", "Coffee")
    - "amount": float (e.g., 25.50)
    - "category": string (e.g., "Food", "Transport", "Entertainment")

**Functions to Implement:**

1. `add_expense(date, description, amount, category)`
   - Parameters: date (string), description (string), amount (float), category (string)
   - Validates date format (must be "YYYY-MM-DD")
   - Validates amount is positive
   - Adds expense to the dictionary
   - Returns True if successful, False otherwise
   - Example: `add_expense("2024-01-15", "Lunch", 12.50, "Food")`

2. `view_expenses(date)`
   - Parameter: date (string)
   - Returns list of expenses for that date
   - If date doesn't exist, returns empty list
   - Displays formatted output like:
     ```
     Expenses for 2024-01-15:
     1. Groceries - $25.50 (Food)
     2. Coffee - $4.00 (Food)
     ```

3. `calculate_total(date)`
   - Parameter: date (string)
   - Returns total amount spent on that date
   - Uses a loop to sum all amounts
   - Returns 0.00 if no expenses found

4. `view_all_expenses()`
   - Displays all expenses grouped by date
   - Uses nested loops to iterate through dictionary
   - Format: Date header, then list of expenses, then total for that date

**Error Handling:**
- Invalid date format: raise ValueError with message "Invalid date format. Use YYYY-MM-DD"
- Negative amounts: raise ValueError with message "Amount must be positive"
- Empty description: raise ValueError with message "Description cannot be empty"
- Use try-except blocks in main program

**Example Usage:**
```python
add_expense("2024-01-15", "Groceries", 25.50, "Food")
add_expense("2024-01-15", "Coffee", 4.00, "Food")
view_expenses("2024-01-15")  # Should display both expenses
total = calculate_total("2024-01-15")  # Should return 29.50
```

**Skills Practiced:** Dictionaries, Lists, Functions, Error Handling, Loops

---

### 2. Student Grade Calculator
**Objective:** Calculate and manage student grades.

**Detailed Requirements:**

**Class Definition:**
- Class name: `Student`
- Attributes:
  - `name`: string (student's full name)
  - `student_id`: string (e.g., "STU001")
  - `grades`: list of floats (scores from 0-100)

**Methods to Implement:**

1. `__init__(self, name, student_id)`
   - Initialize name and student_id
   - Initialize empty grades list
   - Example: `student1 = Student("John Doe", "STU001")`

2. `add_grade(self, grade)`
   - Parameter: grade (float)
   - Validates grade is between 0 and 100
   - Appends grade to self.grades list
   - Raises ValueError if grade is invalid
   - Example: `student1.add_grade(85.5)`

3. `calculate_average(self)`
   - Returns average of all grades (float)
   - Uses a loop to sum grades, then divides by count
   - If grades list is empty, raises ValueError: "No grades available"
   - Example: grades [85, 90, 78] → returns 84.33

4. `get_letter_grade(self)`
   - Returns letter grade based on average
   - Uses if-elif-else:
     - A: 90-100
     - B: 80-89
     - C: 70-79
     - D: 60-69
     - F: 0-59
   - Calls calculate_average() internally
   - Returns string like "A" or "B"

5. `display_info(self)`
   - Prints formatted student information:
     ```
     Student: John Doe
     ID: STU001
     Grades: [85.0, 90.0, 78.0]
     Average: 84.33
     Letter Grade: B
     ```

**Error Handling:**
- Invalid grade range: raise ValueError("Grade must be between 0 and 100")
- Empty grades list: raise ValueError("No grades available to calculate average")
- Use try-except in main program

**Main Program:**
- Create at least 3 student objects
- Add different grades to each
- Display information for all students
- Test error cases (invalid grades, empty list)

**Example Usage:**
```python
student1 = Student("Alice Smith", "STU001")
student1.add_grade(92)
student1.add_grade(88)
student1.add_grade(95)
print(student1.get_letter_grade())  # Should print "A"
student1.display_info()
```

**Skills Practiced:** OOP, Classes, Methods, Control Flow, Error Handling

---

### 3. Simple To-Do List Manager
**Objective:** Build a command-line to-do list application.

**Detailed Requirements:**

**Data Structure:**
- Use a list to store tasks
- Each task is a dictionary with:
  - "task": string (task description)
  - "completed": boolean (True/False)
  - "priority": string ("High", "Medium", "Low")

**Functions to Implement:**

1. `add_task(task_description, priority="Medium")`
   - Parameters: task_description (string), priority (string, default "Medium")
   - Creates dictionary: {"task": task_description, "completed": False, "priority": priority}
   - Validates priority is one of: "High", "Medium", "Low"
   - Appends to tasks list
   - Returns the task dictionary
   - Example: `add_task("Buy groceries", "High")`

2. `remove_task(task_index)`
   - Parameter: task_index (integer, 1-based for user)
   - Removes task at index (convert to 0-based internally)
   - Validates index is valid (not out of range)
   - Raises IndexError if invalid
   - Returns removed task dictionary

3. `mark_complete(task_index)`
   - Parameter: task_index (integer, 1-based)
   - Sets completed to True for task at index
   - Validates index is valid
   - Uses if-else to check if already completed
   - Returns True if marked, False if already complete

4. `view_tasks(filter_type="all")`
   - Parameter: filter_type (string: "all", "completed", "pending")
   - Uses enumerate() to display numbered tasks (starting from 1)
   - Format:
     ```
     1. [ ] Buy groceries (High) - Pending
     2. [X] Finish homework (Medium) - Completed
     ```
   - Uses if-elif-else to filter based on filter_type
   - Uses loops to iterate through tasks

5. `get_statistics()`
   - Returns dictionary with:
     - "total": total number of tasks
     - "completed": number of completed tasks
     - "pending": number of pending tasks
   - Uses loops and if-else to count

**Error Handling:**
- Invalid task index: raise IndexError("Task number does not exist")
- Empty list: print message "No tasks available"
- Invalid priority: raise ValueError("Priority must be High, Medium, or Low")
- Invalid filter: raise ValueError("Filter must be all, completed, or pending")

**Main Program:**
- Create menu-driven interface:
  ```
  1. Add task
  2. Remove task
  3. Mark task as complete
  4. View all tasks
  5. View completed tasks
  6. View pending tasks
  7. Show statistics
  8. Exit
  ```
- Use while loop for menu
- Use if-elif-else for menu selection

**Example Usage:**
```python
add_task("Buy milk", "High")
add_task("Call dentist", "Low")
view_tasks()  # Shows both tasks
mark_complete(1)  # Marks first task complete
view_tasks("pending")  # Shows only pending tasks
```

**Skills Practiced:** Lists, Functions, Loops, Error Handling, Control Flow

---

### 4. Contact Book Application
**Objective:** Create a simple contact management system.

**Detailed Requirements:**

**Data Structure:**
- Use a dictionary where:
  - Key: contact name (string, case-insensitive for searching)
  - Value: dictionary with keys:
    - "phone": string (e.g., "555-1234")
    - "email": string (e.g., "john@email.com")
    - "address": string (e.g., "123 Main St")

**Functions to Implement:**

1. `add_contact(name, phone, email, address)`
   - Parameters: name (string), phone (string), email (string), address (string)
   - Validates name doesn't already exist (case-insensitive check)
   - Validates email contains "@" symbol
   - Validates phone is not empty
   - Creates nested dictionary structure
   - Returns True if added successfully
   - Raises ValueError if contact exists

2. `search_contact(name)`
   - Parameter: name (string)
   - Searches case-insensitively using loops
   - Returns contact dictionary if found, None if not found
   - Displays formatted output:
     ```
     Contact: John Doe
     Phone: 555-1234
     Email: john@email.com
     Address: 123 Main St
     ```

3. `update_contact(name, phone=None, email=None, address=None)`
   - Parameters: name (string), optional phone, email, address
   - Finds contact (case-insensitive)
   - Updates only provided fields (uses if statements to check which fields to update)
   - Raises ValueError if contact not found
   - Returns updated contact dictionary

4. `delete_contact(name)`
   - Parameter: name (string)
   - Removes contact from dictionary (case-insensitive search)
   - Raises KeyError if contact not found
   - Returns deleted contact dictionary

5. `list_all_contacts()`
   - Displays all contacts in formatted way
   - Uses loops to iterate through dictionary
   - Shows numbered list:
     ```
     1. John Doe - 555-1234 - john@email.com
     2. Jane Smith - 555-5678 - jane@email.com
     ```
   - Returns count of contacts

6. `search_by_phone(phone)`
   - Parameter: phone (string)
   - Uses loop to search through all contacts
   - Returns list of contacts with matching phone
   - Uses if statement to check phone match

**Error Handling:**
- Duplicate contact: raise ValueError("Contact already exists")
- Contact not found: raise KeyError("Contact not found")
- Invalid email: raise ValueError("Invalid email format")
- Empty name/phone: raise ValueError("Name and phone are required")
- Use try-except blocks in main program

**Main Program:**
- Create menu:
  ```
  1. Add contact
  2. Search contact
  3. Update contact
  4. Delete contact
  5. List all contacts
  6. Search by phone
  7. Exit
  ```
- Use while loop and if-elif-else for menu

**Example Usage:**
```python
add_contact("John Doe", "555-1234", "john@email.com", "123 Main St")
search_contact("john doe")  # Case-insensitive search
update_contact("John Doe", phone="555-9999")  # Update only phone
list_all_contacts()
```

**Skills Practiced:** Nested Dictionaries, Functions, Loops, Error Handling

---

## Intermediate Level

### 5. Library Management System
**Objective:** Manage books in a library.

**Detailed Requirements:**

**Class 1: Book**
- Attributes:
  - `title`: string
  - `author`: string
  - `isbn`: string (unique identifier)
  - `available`: boolean (True if available, False if borrowed)

- Methods:
  - `__init__(self, title, author, isbn)`: Initialize with available=True
  - `__str__(self)`: Return formatted string: "Title by Author (ISBN: xxx) - Available/Borrowed"

**Class 2: Library**
- Attributes:
  - `books`: list of Book objects

- Methods:

1. `add_book(title, author, isbn)`
   - Creates new Book object
   - Validates ISBN doesn't already exist (use loop to check)
   - Appends to books list
   - Returns Book object
   - Raises ValueError if ISBN exists

2. `remove_book(isbn)`
   - Finds book by ISBN using loop
   - Removes from books list
   - Raises ValueError if book not found
   - Returns removed Book object

3. `borrow_book(isbn)`
   - Finds book by ISBN
   - Uses if-else to check if available
   - Sets available to False
   - Raises ValueError if book not found or not available
   - Returns True if successful

4. `return_book(isbn)`
   - Finds book by ISBN
   - Uses if-else to check if borrowed
   - Sets available to True
   - Raises ValueError if book not found or already available
   - Returns True if successful

5. `search_books(search_term, search_by="title")`
   - Parameters: search_term (string), search_by ("title", "author", or "isbn")
   - Uses list comprehension or loop to filter books
   - Case-insensitive search for title/author
   - Returns list of matching Book objects
   - Example: `search_books("Python", "title")`

6. `list_available_books()`
   - Uses list comprehension or loop to filter available books
   - Returns list of available Book objects
   - Uses if statement to check available attribute

7. `list_borrowed_books()`
   - Returns list of borrowed books
   - Uses loop and if statement

8. `display_all_books()`
   - Displays all books with numbering
   - Uses enumerate() in loop
   - Format: "1. Title by Author (ISBN: xxx) - Status"

**Error Handling:**
- Book not found: raise ValueError("Book not found")
- Book already borrowed: raise ValueError("Book is already borrowed")
- Book already available: raise ValueError("Book is already available")
- Duplicate ISBN: raise ValueError("ISBN already exists")
- Invalid search_by: raise ValueError("search_by must be 'title', 'author', or 'isbn'")

**Main Program:**
- Create Library instance
- Add at least 5 books
- Test borrowing and returning
- Test searching
- Display all books

**Example Usage:**
```python
library = Library()
library.add_book("Python Basics", "John Smith", "ISBN001")
library.add_book("Advanced Python", "Jane Doe", "ISBN002")
library.borrow_book("ISBN001")
library.search_books("Python", "title")  # Should find both
library.list_available_books()  # Should show only ISBN002
```

**Skills Practiced:** OOP, Classes, Lists of Objects, Error Handling, Control Flow

---

### 6. Weather Data Analyzer
**Objective:** Analyze temperature data for a week.

**Detailed Requirements:**

**Data Structure:**
- Dictionary where:
  - Key: day name (string: "Monday", "Tuesday", etc.)
  - Value: temperature in Celsius (float)

**Functions to Implement:**

1. `add_temperature(day, temperature)`
   - Parameters: day (string), temperature (float)
   - Validates day is valid weekday (Monday-Sunday)
   - Validates temperature is reasonable (-50 to 50 Celsius)
   - Adds/updates temperature for that day
   - Returns True if successful
   - Raises ValueError for invalid inputs

2. `calculate_average()`
   - Calculates average temperature for all days
   - Uses loop to sum all temperatures
   - Divides by count of days
   - Returns float rounded to 2 decimal places
   - Raises ValueError if no data available

3. `find_hottest_day()`
   - Uses loop to find maximum temperature
   - Returns tuple: (day, temperature)
   - Uses if statement to compare temperatures
   - Example: ("Wednesday", 28.5)

4. `find_coldest_day()`
   - Uses loop to find minimum temperature
   - Returns tuple: (day, temperature)
   - Uses if statement to compare

5. `categorize_temperature(temperature)`
   - Parameter: temperature (float)
   - Uses if-elif-else:
     - "Hot": >= 30
     - "Warm": 20-29
     - "Moderate": 10-19
     - "Cool": 0-9
     - "Cold": < 0
   - Returns category string

6. `get_daily_categories()`
   - Returns dictionary: {day: category}
   - Uses loop to iterate through temperatures
   - Calls categorize_temperature() for each
   - Example: {"Monday": "Warm", "Tuesday": "Hot"}

7. `display_statistics()`
   - Displays formatted table:
     ```
     Day        Temperature  Category
     --------------------------------
     Monday     25.0         Warm
     Tuesday    32.0         Hot
     ...
     --------------------------------
     Average: 26.5°C
     Hottest: Tuesday (32.0°C)
     Coldest: Friday (15.0°C)
     ```
   - Uses loops to format and display

8. `get_temperature_range()`
   - Returns difference between hottest and coldest
   - Uses find_hottest_day() and find_coldest_day()
   - Returns float

**Error Handling:**
- Invalid day: raise ValueError("Day must be Monday through Sunday")
- Invalid temperature: raise ValueError("Temperature must be between -50 and 50")
- No data: raise ValueError("No temperature data available")
- Use try-except blocks

**Main Program:**
- Add temperatures for a week
- Display statistics
- Test all functions
- Handle error cases

**Example Usage:**
```python
add_temperature("Monday", 25.0)
add_temperature("Tuesday", 32.0)
add_temperature("Wednesday", 18.0)
avg = calculate_average()  # Returns 25.0
hottest = find_hottest_day()  # Returns ("Tuesday", 32.0)
display_statistics()
```

**Skills Practiced:** Dictionaries, Functions, Loops, Control Flow, Error Handling

---

### 7. Password Validator and Generator
**Objective:** Validate and generate secure passwords.

**Detailed Requirements:**

**Import Required Modules:**
- `import random`
- `import string`

**Functions to Implement:**

1. `validate_password(password)`
   - Parameter: password (string)
   - Returns dictionary with validation results:
     ```python
     {
         "valid": True/False,
         "strength": "Weak/Medium/Strong/Very Strong",
         "issues": ["list of problems"],
         "checks": {
             "length": True/False,
             "uppercase": True/False,
             "lowercase": True/False,
             "digit": True/False,
             "special": True/False
         }
     }
     ```
   - Checks:
     - Length >= 8 characters
     - At least one uppercase letter (A-Z)
     - At least one lowercase letter (a-z)
     - At least one digit (0-9)
     - At least one special character (!@#$%^&*)
   - Uses if-elif-else to determine strength:
     - Very Strong: all checks pass + length >= 12
     - Strong: all checks pass
     - Medium: 3-4 checks pass
     - Weak: < 3 checks pass
   - Uses loops to check each character
   - Uses if statements to check each criteria

2. `generate_password(length=12, include_uppercase=True, include_lowercase=True, include_digits=True, include_special=True)`
   - Parameters: length (int, default 12), boolean flags for character types
   - Generates random password with specified requirements
   - Uses `string.ascii_uppercase`, `string.ascii_lowercase`, `string.digits`, `string.punctuation`
   - Uses `random.choice()` in loop to build password
   - Validates length is at least 4
   - Ensures at least one character from each selected type
   - Returns generated password string
   - Raises ValueError if invalid parameters

3. `get_password_feedback(validation_result)`
   - Parameter: validation_result (dictionary from validate_password)
   - Returns formatted feedback string:
     ```
     Password Strength: Strong
     
     Checks:
     ✓ Length (8+ characters)
     ✓ Uppercase letter
     ✓ Lowercase letter
     ✓ Digit
     ✓ Special character
     
     Issues: None
     ```
   - Uses if-else to format checkmarks/X marks
   - Uses loops to format issues list

4. `suggest_password_improvements(password)`
   - Parameter: password (string)
   - Returns list of suggestions:
     - "Add uppercase letters" if missing
     - "Add lowercase letters" if missing
     - "Add digits" if missing
     - "Add special characters" if missing
     - "Make password longer (at least 8 characters)" if too short
   - Uses if statements to check each criteria

**Error Handling:**
- Invalid password type: raise TypeError("Password must be a string")
- Empty password: raise ValueError("Password cannot be empty")
- Invalid length for generator: raise ValueError("Password length must be at least 4")
- Use try-except blocks

**Main Program:**
- Test validate_password with various passwords:
  - "weak" (should be weak)
  - "MediumPass1" (should be medium)
  - "StrongPass123!" (should be strong)
  - "VeryStrongPassword123!" (should be very strong)
- Generate passwords with different requirements
- Display feedback for each

**Example Usage:**
```python
result = validate_password("MyPass123!")
print(get_password_feedback(result))
password = generate_password(length=16)
print(f"Generated: {password}")
```

**Skills Practiced:** Functions, Modules (random, string), Control Flow, Error Handling

---

### 8. Shopping Cart System
**Objective:** Implement an e-commerce shopping cart.

**Detailed Requirements:**

**Class 1: Product**
- Attributes:
  - `name`: string
  - `price`: float (must be positive)
  - `quantity`: integer (must be positive)

- Methods:
  - `__init__(self, name, price, quantity)`: Initialize with validation
  - `__str__(self)`: Return "Name - $price x quantity"
  - `get_total_price(self)`: Return price * quantity

**Class 2: ShoppingCart**
- Attributes:
  - `items`: list of Product objects

- Methods:

1. `add_item(name, price, quantity)`
   - Parameters: name (string), price (float), quantity (int)
   - Validates price > 0 and quantity > 0
   - Checks if product already exists (by name)
   - If exists, updates quantity; if not, creates new Product and adds to list
   - Uses loop to check for existing product
   - Returns Product object
   - Raises ValueError for invalid inputs

2. `remove_item(name)`
   - Parameter: name (string)
   - Finds product by name (case-insensitive, use loop)
   - Removes from items list
   - Raises ValueError if product not found
   - Returns removed Product object

3. `update_quantity(name, new_quantity)`
   - Parameters: name (string), new_quantity (int)
   - Finds product by name
   - Validates new_quantity > 0
   - Updates product quantity
   - Uses if-else to check if product exists
   - Raises ValueError if not found or invalid quantity

4. `calculate_subtotal()`
   - Calculates sum of all item prices (price * quantity)
   - Uses loop to iterate through items
   - Returns float rounded to 2 decimals

5. `apply_discount()`
   - Applies discount based on subtotal:
     - 10% off if subtotal > 200
     - 5% off if subtotal > 100
     - No discount otherwise
   - Uses if-elif-else
   - Returns discount amount (float)

6. `calculate_total()`
   - Returns subtotal - discount
   - Calls calculate_subtotal() and apply_discount()
   - Returns float rounded to 2 decimals

7. `view_cart()`
   - Displays formatted cart:
     ```
     Shopping Cart:
     -------------------------
     1. Laptop - $999.99 x 1 = $999.99
     2. Mouse - $29.99 x 2 = $59.98
     -------------------------
     Subtotal: $1059.97
     Discount (10%): $105.99
     Total: $953.98
     ```
   - Uses enumerate() in loop for numbering
   - Calls calculate methods

8. `get_item_count()`
   - Returns total number of items (sum of all quantities)
   - Uses loop to sum quantities

9. `clear_cart()`
   - Empties the items list
   - Returns number of items cleared

**Error Handling:**
- Invalid price: raise ValueError("Price must be positive")
- Invalid quantity: raise ValueError("Quantity must be positive")
- Product not found: raise ValueError("Product not found in cart")
- Empty cart: raise ValueError("Cart is empty")
- Use try-except blocks

**Main Program:**
- Create ShoppingCart instance
- Add multiple items
- Test updating quantities
- Test removing items
- View cart and verify totals
- Test discount application

**Example Usage:**
```python
cart = ShoppingCart()
cart.add_item("Laptop", 999.99, 1)
cart.add_item("Mouse", 29.99, 2)
cart.update_quantity("Mouse", 3)
cart.view_cart()  # Should show totals and discount
total = cart.calculate_total()
```

**Skills Practiced:** OOP, Lists, Loops, Error Handling, Control Flow

---

### 9. File Organizer Script
**Objective:** Organize files in a directory by extension.

**Detailed Requirements:**

**Import Required Modules:**
- `import os`
- `from pathlib import Path` (optional, but recommended)

**Functions to Implement:**

1. `scan_directory(directory_path)`
   - Parameter: directory_path (string)
   - Uses `os.listdir()` or `Path.iterdir()` to get files
   - Returns dictionary:
     ```python
     {
         ".txt": ["file1.txt", "file2.txt"],
         ".py": ["script1.py", "script2.py"],
         ".jpg": ["photo1.jpg"]
     }
     ```
   - Uses loop to iterate through files
   - Uses `os.path.isfile()` or `Path.is_file()` to check if it's a file (not directory)
   - Uses `os.path.splitext()` or `Path.suffix` to get extension
   - Groups files by extension using dictionary
   - Uses if-else to check if extension key exists, creates list if not
   - Raises FileNotFoundError if directory doesn't exist
   - Raises PermissionError if no access

2. `organize_files(directory_path, organize=False)`
   - Parameters: directory_path (string), organize (boolean, default False)
   - If organize=False: just returns scan results
   - If organize=True: creates subdirectories by extension and moves files
     - Creates folders like "txt_files", "py_files", "jpg_files"
     - Uses `os.makedirs()` to create directories
     - Uses `os.rename()` or `shutil.move()` to move files
   - Returns dictionary of organized files
   - Uses loops to process each file
   - Uses if-else to check organize flag

3. `display_summary(file_dict)`
   - Parameter: file_dict (dictionary from scan_directory)
   - Displays formatted summary:
     ```
     File Organization Summary:
     -------------------------
     .txt files: 5 files
       - document1.txt
       - document2.txt
       ...
     .py files: 3 files
       - script1.py
       ...
     -------------------------
     Total files: 8
     Total extensions: 2
     ```
   - Uses nested loops to display files under each extension
   - Uses if-else to format output
   - Calculates totals

4. `get_file_statistics(file_dict)`
   - Parameter: file_dict (dictionary)
   - Returns dictionary:
     ```python
     {
         "total_files": 8,
         "total_extensions": 2,
         "largest_group": ".txt",
         "file_counts": {".txt": 5, ".py": 3}
     }
     ```
   - Uses loops to calculate statistics
   - Uses if statements to find largest group

5. `filter_by_extension(file_dict, extension)`
   - Parameters: file_dict (dictionary), extension (string, e.g., ".txt")
   - Returns list of files with that extension
   - Uses if statement to check if extension exists
   - Returns empty list if extension not found

**Error Handling:**
- Directory not found: raise FileNotFoundError("Directory not found")
- Permission denied: raise PermissionError("Permission denied to access directory")
- Invalid path: raise ValueError("Invalid directory path")
- Use try-except blocks with specific exceptions

**Main Program:**
- Test with a directory containing various file types
- Display summary
- Test error cases (non-existent directory, permission errors)
- Optionally test organize functionality (be careful with file moving!)

**Example Usage:**
```python
files = scan_directory("/path/to/directory")
display_summary(files)
stats = get_file_statistics(files)
txt_files = filter_by_extension(files, ".txt")
```

**Note:** Be careful when testing the organize feature - it moves actual files!

**Skills Practiced:** Modules (os, pathlib), Dictionaries, Functions, Error Handling, Loops

---

### 10. Restaurant Menu Manager
**Objective:** Manage a restaurant menu with categories.

**Detailed Requirements:**

**Data Structure:**
- Nested dictionary:
  ```python
  {
      "Appetizers": {
          "Spring Rolls": {"price": 5.99, "description": "Crispy vegetable rolls"},
          "Soup": {"price": 4.99, "description": "House special soup"}
      },
      "Main Course": {
          "Pasta": {"price": 12.99, "description": "Creamy pasta"},
          "Pizza": {"price": 14.99, "description": "Margherita pizza"}
      }
  }
  ```

**Functions to Implement:**

1. `add_category(category_name)`
   - Parameter: category_name (string)
   - Adds new category to menu dictionary
   - Initializes with empty dictionary for items
   - Validates category doesn't already exist
   - Raises ValueError if category exists
   - Returns True if successful

2. `add_item(category, item_name, price, description)`
   - Parameters: category (string), item_name (string), price (float), description (string)
   - Validates category exists (raises KeyError if not)
   - Validates price > 0
   - Validates item doesn't already exist in category
   - Adds item to category dictionary
   - Uses if-else to check category and item existence
   - Returns True if successful

3. `remove_item(category, item_name)`
   - Parameters: category (string), item_name (string)
   - Removes item from category
   - Validates category and item exist
   - Raises KeyError if category/item not found
   - Returns removed item dictionary

4. `update_price(category, item_name, new_price)`
   - Parameters: category (string), item_name (string), new_price (float)
   - Updates price for existing item
   - Validates all parameters exist
   - Validates new_price > 0
   - Uses nested if-else to check category then item
   - Raises KeyError or ValueError appropriately

5. `display_menu(category=None)`
   - Parameter: category (string, optional)
   - If category=None: displays entire menu
   - If category specified: displays only that category
   - Uses nested loops to iterate through categories and items
   - Format:
     ```
     ========== RESTAURANT MENU ==========
     
     APPETIZERS
     -------------------------
     Spring Rolls - $5.99
         Crispy vegetable rolls
     Soup - $4.99
         House special soup
     
     MAIN COURSE
     -------------------------
     Pasta - $12.99
         Creamy pasta
     ...
     ```
   - Uses if-elif-else to handle category filtering

6. `search_item(item_name)`
   - Parameter: item_name (string)
   - Searches all categories for item (case-insensitive)
   - Uses nested loops to search
   - Returns tuple: (category, item_info) if found, None if not
   - Uses if statement to check matches

7. `get_items_by_price_range(min_price, max_price)`
   - Parameters: min_price (float), max_price (float)
   - Returns dictionary of items within price range
   - Uses nested loops to check all items
   - Uses if statement to check price range
   - Format: {category: {item_name: item_info}}

8. `get_menu_statistics()`
   - Returns dictionary:
     ```python
     {
         "total_categories": 3,
         "total_items": 10,
         "average_price": 9.50,
         "most_expensive": ("Main Course", "Pizza", 14.99)
     }
     ```
   - Uses nested loops to calculate
   - Uses if statements to find most expensive

**Error Handling:**
- Category not found: raise KeyError("Category not found")
- Item not found: raise KeyError("Item not found in category")
- Invalid price: raise ValueError("Price must be positive")
- Duplicate category/item: raise ValueError("Already exists")
- Use try-except blocks

**Main Program:**
- Create menu with multiple categories
- Add items to each category
- Display full menu
- Test searching and filtering
- Test error cases

**Example Usage:**
```python
add_category("Appetizers")
add_item("Appetizers", "Spring Rolls", 5.99, "Crispy vegetable rolls")
add_item("Appetizers", "Soup", 4.99, "House special soup")
display_menu()  # Shows all
display_menu("Appetizers")  # Shows only appetizers
item = search_item("pizza")  # Case-insensitive search
```

**Skills Practiced:** Nested Dictionaries, Nested Loops, Functions, Error Handling, Control Flow

---

## Advanced Beginner Level

### 11. Bank Account Manager
**Objective:** Create a banking system with multiple accounts.

**Detailed Requirements:**

**Class 1: Account**
- Attributes:
  - `account_number`: string (unique identifier)
  - `balance`: float (initialized to 0.0)
  - `account_type`: string ("Savings" or "Checking")
  - `owner_name`: string

- Methods:

1. `__init__(self, account_number, owner_name, account_type, initial_balance=0.0)`
   - Validates account_type is "Savings" or "Checking"
   - Validates initial_balance >= 0
   - Raises ValueError for invalid inputs

2. `deposit(amount)`
   - Parameter: amount (float)
   - Validates amount > 0
   - Adds amount to balance
   - Returns new balance
   - Raises ValueError if amount <= 0

3. `withdraw(amount)`
   - Parameter: amount (float)
   - Validates amount > 0
   - Uses if-else to check if balance >= amount
   - Subtracts amount from balance if sufficient
   - Raises ValueError if insufficient funds or invalid amount
   - Returns new balance

4. `check_balance()`
   - Returns current balance (float)
   - No parameters needed

5. `transfer(amount, target_account)`
   - Parameters: amount (float), target_account (Account object)
   - Validates amount > 0
   - Uses if-else to check sufficient balance
   - Withdraws from self, deposits to target_account
   - Raises ValueError if insufficient funds or invalid account
   - Returns tuple: (self.balance, target_account.balance)

6. `__str__(self)`
   - Returns formatted string: "Account #12345 (Savings) - Owner: John - Balance: $1000.00"

**Class 2: Bank**
- Attributes:
  - `accounts`: dictionary {account_number: Account object}

- Methods:

1. `create_account(account_number, owner_name, account_type, initial_balance=0.0)`
   - Creates new Account object
   - Validates account_number doesn't exist
   - Adds to accounts dictionary
   - Returns Account object
   - Raises ValueError if account exists

2. `get_account(account_number)`
   - Parameter: account_number (string)
   - Returns Account object if found
   - Raises KeyError if account not found
   - Uses if statement to check existence

3. `delete_account(account_number)`
   - Parameter: account_number (string)
   - Removes account from dictionary
   - Raises KeyError if not found
   - Returns deleted Account object

4. `transfer_between_accounts(from_account, to_account, amount)`
   - Parameters: from_account (string), to_account (string), amount (float)
   - Gets both accounts using get_account()
   - Calls transfer() on source account
   - Handles errors appropriately
   - Returns True if successful

5. `get_total_balance()`
   - Returns sum of all account balances
   - Uses loop to iterate through accounts
   - Returns float

6. `list_all_accounts()`
   - Displays all accounts with details
   - Uses loop to iterate through accounts
   - Format: numbered list with account details

**Error Handling:**
- Insufficient funds: raise ValueError("Insufficient funds")
- Invalid amount: raise ValueError("Amount must be positive")
- Account not found: raise KeyError("Account not found")
- Invalid account type: raise ValueError("Account type must be 'Savings' or 'Checking'")
- Use try-except blocks

**Main Program:**
- Create Bank instance
- Create multiple accounts
- Test deposits and withdrawals
- Test transfers between accounts
- Display all accounts
- Test error cases

**Example Usage:**
```python
bank = Bank()
acc1 = bank.create_account("ACC001", "John Doe", "Savings", 1000.0)
acc2 = bank.create_account("ACC002", "Jane Smith", "Checking", 500.0)
acc1.deposit(200.0)
acc1.withdraw(100.0)
bank.transfer_between_accounts("ACC001", "ACC002", 150.0)
bank.list_all_accounts()
```

**Skills Practiced:** OOP, Error Handling, Control Flow, Dictionaries of Objects

---

### 12. Movie Database System
**Objective:** Manage a collection of movies.

**Detailed Requirements:**

**Class 1: Movie**
- Attributes:
  - `title`: string
  - `director`: string
  - `year`: integer (1900-2024)
  - `genre`: string (e.g., "Action", "Comedy", "Drama")
  - `rating`: float (0.0 to 10.0)

- Methods:
  - `__init__(self, title, director, year, genre, rating)`: Initialize with validation
  - `__str__(self)`: Return formatted string
  - `__repr__(self)`: Return string representation

**Class 2: MovieDatabase**
- Attributes:
  - `movies`: list of Movie objects

- Methods:

1. `add_movie(title, director, year, genre, rating)`
   - Creates new Movie object
   - Validates year is between 1900-2024
   - Validates rating is between 0.0-10.0
   - Checks if movie already exists (by title, case-insensitive)
   - Appends to movies list
   - Returns Movie object
   - Raises ValueError for invalid inputs or duplicates

2. `search_by_genre(genre)`
   - Parameter: genre (string)
   - Returns list of Movie objects matching genre (case-insensitive)
   - Uses list comprehension or loop with if statement
   - Returns empty list if no matches

3. `search_by_year(year)`
   - Parameter: year (integer)
   - Returns list of Movie objects from that year
   - Uses list comprehension or loop
   - Returns empty list if no matches

4. `search_by_director(director)`
   - Parameter: director (string)
   - Returns list of Movie objects by that director (case-insensitive)
   - Uses list comprehension or loop

5. `get_top_rated(n=5)`
   - Parameter: n (integer, default 5)
   - Returns list of top n rated movies
   - Sorts movies by rating (descending)
   - Uses sorted() with key parameter or manual sorting
   - Returns list of Movie objects

6. `filter_by_rating(min_rating)`
   - Parameter: min_rating (float)
   - Returns list of movies with rating >= min_rating
   - Uses list comprehension: `[m for m in self.movies if m.rating >= min_rating]`
   - Returns empty list if no matches

7. `get_average_rating()`
   - Returns average rating of all movies
   - Uses loop to sum ratings, divides by count
   - Returns 0.0 if no movies
   - Returns float rounded to 2 decimals

8. `get_movies_by_genre()`
   - Returns dictionary: {genre: [list of movies]}
   - Groups movies by genre
   - Uses loops and if-else to build dictionary
   - Example: {"Action": [movie1, movie2], "Comedy": [movie3]}

9. `display_all_movies()`
   - Displays all movies in formatted table:
     ```
     Title          Director      Year  Genre    Rating
     --------------------------------------------------
     Inception      Nolan         2010  Action   8.8
     The Matrix     Wachowski     1999  Sci-Fi   8.7
     ```
   - Uses loops to format and display

10. `remove_movie(title)`
    - Parameter: title (string)
    - Removes movie by title (case-insensitive)
    - Uses loop to find and remove
    - Raises ValueError if not found
    - Returns removed Movie object

**Error Handling:**
- Invalid year: raise ValueError("Year must be between 1900 and 2024")
- Invalid rating: raise ValueError("Rating must be between 0.0 and 10.0")
- Movie not found: raise ValueError("Movie not found")
- Duplicate movie: raise ValueError("Movie already exists")
- Use try-except blocks

**Main Program:**
- Create MovieDatabase instance
- Add at least 10 movies with different genres and years
- Test all search and filter methods
- Display top rated movies
- Test error cases
- Create menu-driven interface with if-elif-else

**Example Usage:**
```python
db = MovieDatabase()
db.add_movie("Inception", "Christopher Nolan", 2010, "Action", 8.8)
db.add_movie("The Matrix", "Wachowski", 1999, "Sci-Fi", 8.7)
action_movies = db.search_by_genre("Action")
top_5 = db.get_top_rated(5)
high_rated = db.filter_by_rating(8.5)
```

**Skills Practiced:** OOP, Lists, List Comprehensions, Error Handling, Control Flow

---

### 13. Inventory Management System
**Objective:** Track inventory for a store.

**Detailed Requirements:**

**Class 1: Item**
- Attributes:
  - `name`: string
  - `sku`: string (Stock Keeping Unit, unique identifier)
  - `quantity`: integer (must be >= 0)
  - `price`: float (must be > 0)
  - `category`: string (e.g., "Electronics", "Clothing", "Food")

- Methods:
  - `__init__(self, name, sku, quantity, price, category)`: Initialize with validation
  - `get_total_value(self)`: Return quantity * price
  - `__str__(self)`: Return formatted string

**Class 2: Inventory**
- Attributes:
  - `items`: list of Item objects

- Methods:

1. `add_item(name, sku, quantity, price, category)`
   - Creates new Item object
   - Validates SKU doesn't already exist (use loop to check)
   - Validates quantity >= 0 and price > 0
   - Appends to items list
   - Returns Item object
   - Raises ValueError for invalid inputs or duplicate SKU

2. `update_quantity(sku, new_quantity)`
   - Parameters: sku (string), new_quantity (integer)
   - Finds item by SKU (use loop)
   - Validates new_quantity >= 0
   - Updates item quantity
   - Raises ValueError if item not found or invalid quantity
   - Returns updated Item object

3. `add_stock(sku, amount)`
   - Parameters: sku (string), amount (integer)
   - Adds amount to existing quantity
   - Validates amount > 0
   - Raises ValueError if item not found or invalid amount
   - Returns new quantity

4. `remove_stock(sku, amount)`
   - Parameters: sku (string), amount (integer)
   - Subtracts amount from quantity
   - Uses if-else to check if sufficient stock
   - Validates amount > 0
   - Raises ValueError if insufficient stock or item not found
   - Returns new quantity

5. `low_stock_alert(threshold=10)`
   - Parameter: threshold (integer, default 10)
   - Returns list of items where quantity < threshold
   - Uses list comprehension or loop with if statement
   - Example: `[item for item in self.items if item.quantity < threshold]`
   - Returns list of Item objects

6. `calculate_total_value()`
   - Returns total value of all inventory (sum of quantity * price for all items)
   - Uses loop to iterate through items
   - Returns float rounded to 2 decimals

7. `get_items_by_category(category)`
   - Parameter: category (string)
   - Returns list of items in that category (case-insensitive)
   - Uses list comprehension or loop
   - Returns empty list if no matches

8. `search_item(search_term)`
   - Parameter: search_term (string)
   - Searches by name or SKU (case-insensitive)
   - Returns list of matching Item objects
   - Uses loop and if statement to check matches

9. `generate_category_report()`
   - Returns dictionary: {category: {"count": int, "total_value": float}}
   - Groups items by category
   - Uses loops and if-else to build dictionary
   - Calculates count and total value per category

10. `display_inventory()`
    - Displays formatted inventory table:
      ```
      SKU      Name           Category      Quantity  Price    Total Value
      --------------------------------------------------------------------
      SKU001   Laptop         Electronics   5        999.99   4999.95
      SKU002   T-Shirt        Clothing      20       19.99    399.80
      ```
    - Uses loops to format and display
    - Shows totals at bottom

11. `remove_item(sku)`
    - Parameter: sku (string)
    - Removes item from inventory
    - Uses loop to find and remove
    - Raises ValueError if not found
    - Returns removed Item object

**Error Handling:**
- Invalid quantity: raise ValueError("Quantity must be non-negative")
- Invalid price: raise ValueError("Price must be positive")
- Item not found: raise ValueError("Item not found")
- Duplicate SKU: raise ValueError("SKU already exists")
- Insufficient stock: raise ValueError("Insufficient stock")
- Use try-except blocks

**Main Program:**
- Create Inventory instance
- Add multiple items across different categories
- Test stock updates
- Check low stock alerts
- Generate category reports
- Display full inventory
- Test error cases

**Example Usage:**
```python
inventory = Inventory()
inventory.add_item("Laptop", "SKU001", 5, 999.99, "Electronics")
inventory.add_stock("SKU001", 3)  # Now has 8
inventory.remove_stock("SKU001", 2)  # Now has 6
low_stock = inventory.low_stock_alert(10)  # Returns items with < 10
total_value = inventory.calculate_total_value()
report = inventory.generate_category_report()
```

**Skills Practiced:** OOP, Lists, Loops, Control Flow, Error Handling

---

### 14. Text File Statistics Analyzer
**Objective:** Analyze text files and generate statistics.

**Detailed Requirements:**

**Functions to Implement:**

1. `read_file(file_path)`
   - Parameter: file_path (string)
   - Reads text file using `open()` and `read()` or `readlines()`
   - Handles encoding (use encoding='utf-8')
   - Returns file content as string
   - Raises FileNotFoundError if file doesn't exist
   - Raises UnicodeDecodeError for encoding issues
   - Closes file properly (use `with` statement)

2. `count_words(text)`
   - Parameter: text (string)
   - Counts total number of words
   - Splits text by whitespace using `split()`
   - Filters out empty strings
   - Returns integer
   - Handles empty text (returns 0)

3. `count_lines(text)`
   - Parameter: text (string)
   - Counts number of lines
   - Uses `split('\n')` or `splitlines()`
   - Returns integer
   - Empty file returns 1 (one empty line)

4. `count_characters(text, include_spaces=True)`
   - Parameters: text (string), include_spaces (boolean, default True)
   - Counts total characters
   - Uses if-else to include/exclude spaces
   - If include_spaces=False, removes spaces before counting
   - Returns integer

5. `count_sentences(text)`
   - Parameter: text (string)
   - Counts sentences (ends with . ! ?)
   - Uses loop to check each character
   - Uses if statement to check sentence endings
   - Returns integer

6. `find_most_common_words(text, n=10)`
   - Parameters: text (string), n (integer, default 10)
   - Counts word frequencies using dictionary
   - Converts to lowercase for counting
   - Removes punctuation (optional enhancement)
   - Uses loop to count words
   - Sorts dictionary by values (descending)
   - Returns list of tuples: [("word", count), ...]
   - Example: [("the", 15), ("and", 12), ...]

7. `get_word_frequency(text, word)`
   - Parameters: text (string), word (string)
   - Returns count of specific word (case-insensitive)
   - Uses dictionary or direct counting
   - Returns integer

8. `get_average_word_length(text)`
   - Parameter: text (string)
   - Calculates average length of words
   - Uses loop to sum word lengths
   - Divides by word count
   - Returns float rounded to 2 decimals

9. `get_longest_word(text)`
   - Parameter: text (string)
   - Finds longest word in text
   - Uses loop and if statement to compare lengths
   - Returns tuple: (word, length)
   - Returns None if no words

10. `display_statistics(file_path)`
    - Parameter: file_path (string)
    - Reads file and calculates all statistics
    - Displays formatted output:
      ```
      File Statistics: filename.txt
      =============================
      Total Words: 250
      Total Lines: 15
      Total Characters (with spaces): 1,234
      Total Characters (without spaces): 1,000
      Total Sentences: 12
      Average Word Length: 4.5
      Longest Word: "extraordinary" (13 characters)
      
      Top 10 Most Common Words:
      1. the - 25 occurrences
      2. and - 18 occurrences
      ...
      ```
    - Uses all above functions
    - Handles errors gracefully

**Error Handling:**
- File not found: raise FileNotFoundError("File not found")
- Empty file: print message "File is empty" and return None
- Encoding error: raise UnicodeDecodeError or handle with try-except
- Invalid file path: raise ValueError("Invalid file path")
- Use try-except blocks with specific exceptions

**Main Program:**
- Test with a sample text file
- Display all statistics
- Test with empty file
- Test with non-existent file
- Test error handling

**Example Usage:**
```python
stats = display_statistics("sample.txt")
words = count_words(text)
common = find_most_common_words(text, 5)
longest = get_longest_word(text)
```

**Note:** Create a sample text file for testing, or use an existing file.

**Skills Practiced:** File Handling, Dictionaries, Functions, Loops, Error Handling

---

### 15. Employee Payroll System
**Objective:** Calculate employee salaries and manage payroll.

**Detailed Requirements:**

**Class 1: Employee**
- Attributes:
  - `name`: string
  - `employee_id`: string (unique identifier)
  - `hourly_rate`: float (must be > 0)
  - `hours_worked`: float (must be >= 0)

- Methods:

1. `__init__(self, name, employee_id, hourly_rate, hours_worked=0.0)`
   - Initialize with validation
   - Validates hourly_rate > 0
   - Validates hours_worked >= 0
   - Raises ValueError for invalid inputs

2. `calculate_regular_pay()`
   - Calculates pay for first 40 hours
   - If hours_worked <= 40: returns hours_worked * hourly_rate
   - If hours_worked > 40: returns 40 * hourly_rate
   - Returns float rounded to 2 decimals

3. `calculate_overtime()`
   - Calculates overtime pay (1.5x rate for hours over 40)
   - Uses if-else to check if hours_worked > 40
   - If hours_worked <= 40: returns 0.0
   - If hours_worked > 40: returns (hours_worked - 40) * hourly_rate * 1.5
   - Returns float rounded to 2 decimals

4. `calculate_gross_pay()`
   - Returns regular_pay + overtime_pay
   - Calls calculate_regular_pay() and calculate_overtime()
   - Returns float rounded to 2 decimals

5. `apply_tax(gross_pay)`
   - Parameter: gross_pay (float)
   - Calculates tax based on brackets using if-elif-else:
     - 0-1000: 10%
     - 1001-2000: 15%
     - 2001-5000: 20%
     - 5000+: 25%
   - Returns tax amount (float rounded to 2 decimals)
   - Example: gross_pay = 2500 → tax = 1000*0.10 + 1000*0.15 + 500*0.20 = 350.00

6. `calculate_net_pay()`
   - Calculates net pay (gross_pay - tax)
   - Calls calculate_gross_pay() and apply_tax()
   - Returns float rounded to 2 decimals

7. `update_hours(hours)`
   - Parameter: hours (float)
   - Updates hours_worked
   - Validates hours >= 0
   - Raises ValueError if invalid

8. `__str__(self)`
   - Returns formatted employee info string

**Class 2: Payroll**
- Attributes:
  - `employees`: list of Employee objects

- Methods:

1. `add_employee(name, employee_id, hourly_rate, hours_worked=0.0)`
   - Creates new Employee object
   - Validates employee_id doesn't exist (use loop)
   - Appends to employees list
   - Returns Employee object
   - Raises ValueError if duplicate ID

2. `remove_employee(employee_id)`
   - Parameter: employee_id (string)
   - Removes employee from list
   - Uses loop to find and remove
   - Raises ValueError if not found
   - Returns removed Employee object

3. `calculate_total_payroll()`
   - Returns dictionary:
     ```python
     {
         "total_gross": 15000.00,
         "total_tax": 3000.00,
         "total_net": 12000.00,
         "employee_count": 5
     }
     ```
   - Uses loop to sum all employee pays
   - Calls calculate methods on each employee

4. `generate_payroll_report()`
   - Displays formatted report:
     ```
     PAYROLL REPORT
     ==========================================
     Employee ID  Name          Hours  Gross Pay  Tax      Net Pay
     ------------------------------------------------------------
     EMP001       John Doe      45     950.00     142.50   807.50
     EMP002       Jane Smith    40     800.00     80.00    720.00
     ...
     ------------------------------------------------------------
     Totals:                    85     1750.00    222.50   1527.50
     ```
   - Uses loops to format and display
   - Shows totals at bottom

5. `get_employee(employee_id)`
   - Parameter: employee_id (string)
   - Returns Employee object if found
   - Uses loop to search
   - Raises ValueError if not found

6. `update_employee_hours(employee_id, hours)`
   - Parameters: employee_id (string), hours (float)
   - Updates hours for specific employee
   - Uses get_employee() and update_hours()
   - Returns updated Employee object

**Error Handling:**
- Invalid hourly_rate: raise ValueError("Hourly rate must be positive")
- Invalid hours: raise ValueError("Hours must be non-negative")
- Employee not found: raise ValueError("Employee not found")
- Duplicate employee_id: raise ValueError("Employee ID already exists")
- Use try-except blocks

**Main Program:**
- Create Payroll instance
- Add at least 5 employees with different hours
- Update hours for some employees
- Generate payroll report
- Display totals
- Test error cases

**Example Usage:**
```python
payroll = Payroll()
payroll.add_employee("John Doe", "EMP001", 20.0, 45.0)
payroll.add_employee("Jane Smith", "EMP002", 25.0, 40.0)
payroll.update_employee_hours("EMP001", 50.0)
report = payroll.generate_payroll_report()
totals = payroll.calculate_total_payroll()
```

**Skills Practiced:** OOP, Control Flow, Error Handling, Calculations

---

### 16. Recipe Manager Application
**Objective:** Store and manage cooking recipes.

**Detailed Requirements:**

**Class 1: Recipe**
- Attributes:
  - `name`: string
  - `ingredients`: list of dictionaries, each with:
    - "name": string (ingredient name)
    - "amount": float (quantity)
    - "unit": string (e.g., "cups", "tbsp", "grams")
  - `instructions`: list of strings (step-by-step instructions)
  - `servings`: integer (must be > 0)
  - `prep_time`: integer (minutes, must be >= 0)

- Methods:

1. `__init__(self, name, ingredients, instructions, servings, prep_time)`
   - Initialize with validation
   - Validates servings > 0
   - Validates prep_time >= 0
   - Validates ingredients and instructions are lists
   - Raises ValueError for invalid inputs

2. `add_ingredient(name, amount, unit)`
   - Parameters: name (string), amount (float), unit (string)
   - Creates ingredient dictionary
   - Appends to ingredients list
   - Returns updated ingredients list

3. `add_instruction(instruction)`
   - Parameter: instruction (string)
   - Appends to instructions list
   - Returns updated instructions list

4. `scale_recipe(new_servings)`
   - Parameter: new_servings (integer)
   - Scales all ingredient amounts proportionally
   - Calculates ratio: new_servings / current servings
   - Uses loop to update each ingredient amount
   - Updates servings attribute
   - Validates new_servings > 0
   - Returns scaled Recipe object (or updates self)

5. `get_ingredient_list()`
   - Returns formatted string of ingredients:
     ```
     Ingredients:
     - 2 cups flour
     - 1 tbsp sugar
     - 3 eggs
     ```
   - Uses loop to format each ingredient

6. `get_instructions()`
   - Returns formatted string of instructions:
     ```
     Instructions:
     1. Mix flour and sugar
     2. Add eggs
     3. Bake for 30 minutes
     ```
   - Uses enumerate() in loop for numbering

7. `__str__(self)`
   - Returns formatted recipe summary

**Class 2: RecipeBook**
- Attributes:
  - `recipes`: list of Recipe objects

- Methods:

1. `add_recipe(name, ingredients, instructions, servings, prep_time)`
   - Creates new Recipe object
   - Validates name doesn't already exist (case-insensitive, use loop)
   - Appends to recipes list
   - Returns Recipe object
   - Raises ValueError if duplicate name

2. `search_by_ingredient(ingredient_name)`
   - Parameter: ingredient_name (string)
   - Returns list of recipes containing that ingredient (case-insensitive)
   - Uses nested loops: outer for recipes, inner for ingredients
   - Uses if statement to check ingredient name match
   - Returns list of Recipe objects

3. `search_by_name(name)`
   - Parameter: name (string)
   - Returns Recipe object if found (case-insensitive)
   - Uses loop to search
   - Raises ValueError if not found

4. `display_recipe(name)`
   - Parameter: name (string)
   - Finds recipe by name
   - Displays full recipe:
     ```
     Recipe: Chocolate Cake
     Servings: 8
     Prep Time: 45 minutes
     
     Ingredients:
     - 2 cups flour
     - 1 cup sugar
     ...
     
     Instructions:
     1. Preheat oven to 350°F
     2. Mix dry ingredients
     ...
     ```
   - Uses loops to display ingredients and instructions

5. `list_all_recipes()`
   - Displays list of all recipe names with basic info:
     ```
     Recipes:
     1. Chocolate Cake - 8 servings - 45 min
     2. Apple Pie - 6 servings - 60 min
     ```
   - Uses enumerate() in loop

6. `get_recipes_by_prep_time(max_time)`
   - Parameter: max_time (integer, minutes)
   - Returns list of recipes with prep_time <= max_time
   - Uses list comprehension or loop with if statement
   - Returns list of Recipe objects

7. `remove_recipe(name)`
   - Parameter: name (string)
   - Removes recipe from list
   - Uses loop to find and remove
   - Raises ValueError if not found
   - Returns removed Recipe object

**Error Handling:**
- Invalid servings: raise ValueError("Servings must be positive")
- Invalid prep_time: raise ValueError("Prep time must be non-negative")
- Recipe not found: raise ValueError("Recipe not found")
- Duplicate recipe: raise ValueError("Recipe already exists")
- Invalid ingredient format: raise ValueError("Invalid ingredient format")
- Use try-except blocks

**Main Program:**
- Create RecipeBook instance
- Add at least 5 recipes with multiple ingredients and instructions
- Test searching by ingredient
- Test scaling recipes
- Display recipes
- Test error cases

**Example Usage:**
```python
book = RecipeBook()
ingredients = [
    {"name": "flour", "amount": 2, "unit": "cups"},
    {"name": "sugar", "amount": 1, "unit": "cup"}
]
instructions = ["Mix ingredients", "Bake for 30 min"]
book.add_recipe("Cake", ingredients, instructions, 8, 45)
recipes_with_flour = book.search_by_ingredient("flour")
book.display_recipe("Cake")
```

**Skills Practiced:** OOP, Lists, Loops, Error Handling, Control Flow

---

### 17. Simple Calculator with History
**Objective:** Build a calculator that remembers previous calculations.

**Detailed Requirements:**

**Data Structure:**
- Global list: `calculation_history`
- Each entry is a tuple: (operation, num1, num2, result)
- Example: ("add", 5, 3, 8) or ("multiply", 4, 7, 28)

**Functions to Implement:**

1. `add(num1, num2)`
   - Parameters: num1 (float), num2 (float)
   - Returns sum: num1 + num2
   - Adds tuple to history: ("add", num1, num2, result)
   - Returns float

2. `subtract(num1, num2)`
   - Parameters: num1 (float), num2 (float)
   - Returns difference: num1 - num2
   - Adds tuple to history: ("subtract", num1, num2, result)
   - Returns float

3. `multiply(num1, num2)`
   - Parameters: num1 (float), num2 (float)
   - Returns product: num1 * num2
   - Adds tuple to history: ("multiply", num1, num2, result)
   - Returns float

4. `divide(num1, num2)`
   - Parameters: num1 (float), num2 (float)
   - Returns quotient: num1 / num2
   - Uses if-else to check if num2 == 0
   - Raises ZeroDivisionError if num2 is 0
   - Adds tuple to history: ("divide", num1, num2, result)
   - Returns float

5. `calculate(operation, num1, num2)`
   - Parameters: operation (string), num1 (float), num2 (float)
   - Uses if-elif-else to select operation:
     - "add" or "+": calls add()
     - "subtract" or "-": calls subtract()
     - "multiply" or "*": calls multiply()
     - "divide" or "/": calls divide()
   - Raises ValueError for invalid operation
   - Returns result (float)

6. `display_history()`
   - Displays all calculations in formatted way:
     ```
     Calculation History:
     --------------------
     1. 5.0 + 3.0 = 8.0
     2. 10.0 - 4.0 = 6.0
     3. 7.0 * 2.0 = 14.0
     4. 15.0 / 3.0 = 5.0
     --------------------
     Total calculations: 4
     ```
   - Uses enumerate() in loop for numbering
   - Uses if-elif-else to format operation symbols
   - Returns count of calculations

7. `clear_history()`
   - Clears the calculation_history list
   - Returns number of calculations cleared

8. `get_last_calculation()`
   - Returns last calculation tuple
   - Returns None if history is empty
   - Uses if-else to check if list is empty

9. `get_calculations_by_operation(operation)`
   - Parameter: operation (string: "add", "subtract", etc.)
   - Returns list of calculations with that operation
   - Uses list comprehension or loop with if statement
   - Example: `[calc for calc in history if calc[0] == "add"]`

10. `get_statistics()`
    - Returns dictionary:
      ```python
      {
          "total_calculations": 10,
          "additions": 3,
          "subtractions": 2,
          "multiplications": 2,
          "divisions": 3
      }
      ```
    - Uses loops and if-elif-else to count operations

**Error Handling:**
- Division by zero: raise ZeroDivisionError("Cannot divide by zero")
- Invalid operation: raise ValueError("Invalid operation. Use: add, subtract, multiply, divide")
- Invalid number type: raise TypeError("Numbers must be numeric")
- Use try-except blocks

**Main Program:**
- Test all operations
- Perform multiple calculations
- Display history
- Test statistics
- Test error cases (division by zero, invalid operation)
- Clear history and verify

**Example Usage:**
```python
result1 = add(5, 3)  # Returns 8.0
result2 = multiply(4, 7)  # Returns 28.0
result3 = calculate("divide", 15, 3)  # Returns 5.0
display_history()  # Shows all 3 calculations
stats = get_statistics()
clear_history()
```

**Skills Practiced:** Functions, Lists, Tuples, Error Handling, Control Flow

---

### 18. Event Scheduler
**Objective:** Schedule and manage events.

**Detailed Requirements:**

**Import Required:**
- `from datetime import datetime, date, time`

**Class 1: Event**
- Attributes:
  - `title`: string
  - `date`: date object (use datetime.date)
  - `time`: time object (use datetime.time, optional, default None)
  - `location`: string
  - `description`: string

- Methods:

1. `__init__(self, title, date, location, description="", time=None)`
   - Parameters: title (string), date (date object or string "YYYY-MM-DD"), location (string), description (string, optional), time (time object or string "HH:MM", optional)
   - Converts string dates to date objects if needed
   - Converts string times to time objects if needed
   - Validates date is not in the past (optional check)
   - Raises ValueError for invalid formats

2. `is_past_event()`
   - Returns True if event date is before today
   - Uses if-else to compare dates
   - Returns boolean

3. `__str__(self)`
   - Returns formatted string:
     ```
     Event: Meeting
     Date: 2024-02-15
     Time: 14:30
     Location: Conference Room A
     Description: Team meeting
     ```

**Class 2: Scheduler**
- Attributes:
  - `events`: list of Event objects

- Methods:

1. `add_event(title, date, location, description="", time=None)`
   - Creates new Event object
   - Validates date format
   - Appends to events list
   - Returns Event object
   - Raises ValueError for invalid date/time format

2. `remove_event(title)`
   - Parameter: title (string)
   - Removes event by title (case-insensitive)
   - Uses loop to find and remove
   - Raises ValueError if not found
   - Returns removed Event object

3. `get_events_by_date(target_date)`
   - Parameter: target_date (date object or string "YYYY-MM-DD")
   - Returns list of events on that date
   - Uses list comprehension or loop with if statement
   - Converts string to date if needed
   - Returns list of Event objects

4. `upcoming_events(n=5)`
   - Parameter: n (integer, default 5)
   - Returns list of next n upcoming events (not past)
   - Filters out past events using is_past_event()
   - Sorts by date (ascending)
   - Uses loops and if statements
   - Returns list of Event objects

5. `get_events_by_location(location)`
   - Parameter: location (string)
   - Returns list of events at that location (case-insensitive)
   - Uses list comprehension or loop
   - Returns list of Event objects

6. `display_all_events()`
   - Displays all events in formatted way:
     ```
     All Events:
     -----------
     1. Meeting - 2024-02-15 14:30 - Conference Room A
     2. Party - 2024-02-20 18:00 - Restaurant
     ```
   - Uses enumerate() in loop
   - Sorts by date

7. `display_upcoming_events(n=5)`
   - Displays next n upcoming events
   - Uses upcoming_events() method
   - Formats nicely with numbering

8. `get_events_today()`
   - Returns list of events scheduled for today
   - Uses datetime.date.today()
   - Uses get_events_by_date() with today's date
   - Returns list of Event objects

9. `get_events_this_week()`
   - Returns list of events in current week
   - Calculates week start and end dates
   - Uses loop and if statement to filter
   - Returns list of Event objects

**Error Handling:**
- Invalid date format: raise ValueError("Invalid date format. Use YYYY-MM-DD")
- Invalid time format: raise ValueError("Invalid time format. Use HH:MM")
- Event not found: raise ValueError("Event not found")
- Past event (if validation enabled): raise ValueError("Cannot create event in the past")
- Use try-except blocks

**Main Program:**
- Create Scheduler instance
- Add multiple events with different dates
- Test filtering by date
- Display upcoming events
- Test error cases
- Test date comparisons

**Example Usage:**
```python
scheduler = Scheduler()
scheduler.add_event("Meeting", "2024-02-15", "Office", "Team meeting", "14:30")
scheduler.add_event("Party", "2024-02-20", "Restaurant", "Birthday party", "18:00")
today_events = scheduler.get_events_today()
upcoming = scheduler.upcoming_events(3)
scheduler.display_all_events()
```

**Note:** For date handling, you can use `datetime.strptime()` to parse strings, or accept date objects directly.

**Skills Practiced:** OOP, Lists, Control Flow, Error Handling, Date Handling

---

### 19. Word Counter and Analyzer
**Objective:** Analyze text and provide word statistics.

**Detailed Requirements:**

**Functions to Implement:**

1. `analyze_text(text)`
   - Parameter: text (string)
   - Main function that performs all analysis
   - Returns dictionary with all statistics:
     ```python
     {
         "word_count": 250,
         "sentence_count": 15,
         "character_count": 1234,
         "character_count_no_spaces": 1000,
         "average_word_length": 4.5,
         "longest_word": ("extraordinary", 13),
         "shortest_word": ("a", 1),
         "most_common_words": [("the", 25), ("and", 18), ...],
         "unique_words": 150
     }
     ```
   - Calls other functions internally
   - Uses if-else to validate text is not empty

2. `word_count(text)`
   - Parameter: text (string)
   - Counts total words (split by whitespace)
   - Removes empty strings
   - Returns integer
   - Handles empty text (returns 0)

3. `sentence_count(text)`
   - Parameter: text (string)
   - Counts sentences (ends with . ! ?)
   - Uses loop to check each character
   - Uses if statement to check sentence endings
   - Returns integer

4. `character_count(text, include_spaces=True)`
   - Parameters: text (string), include_spaces (boolean)
   - Counts characters
   - Uses if-else to include/exclude spaces
   - Returns integer

5. `average_word_length(text)`
   - Parameter: text (string)
   - Calculates average length of words
   - Splits text into words
   - Uses loop to sum lengths
   - Divides by word count
   - Returns float rounded to 2 decimals
   - Returns 0.0 if no words

6. `find_longest_word(text)`
   - Parameter: text (string)
   - Finds longest word
   - Uses loop and if statement to compare lengths
   - Returns tuple: (word, length)
   - Returns None if no words

7. `find_shortest_word(text)`
   - Parameter: text (string)
   - Finds shortest word
   - Uses loop and if statement
   - Returns tuple: (word, length)
   - Returns None if no words

8. `count_word_frequencies(text)`
   - Parameter: text (string)
   - Counts frequency of each word
   - Converts to lowercase
   - Removes punctuation (optional: use string methods)
   - Uses dictionary to count
   - Uses loop to process each word
   - Returns dictionary: {word: count}

9. `get_most_common_words(text, n=10)`
   - Parameters: text (string), n (integer, default 10)
   - Calls count_word_frequencies()
   - Sorts by frequency (descending)
   - Returns list of tuples: [("word", count), ...]
   - Returns top n words

10. `get_unique_words(text)`
    - Parameter: text (string)
    - Returns count of unique words
    - Uses set or dictionary keys
    - Returns integer

11. `analyze_from_file(file_path)`
    - Parameter: file_path (string)
    - Reads file using file handling
    - Calls analyze_text() with file content
    - Handles file errors
    - Returns analysis dictionary
    - Raises FileNotFoundError if file doesn't exist

12. `display_analysis(analysis_dict)`
    - Parameter: analysis_dict (dictionary from analyze_text)
    - Displays formatted output:
      ```
      Text Analysis Results:
      =====================
      Word Count: 250
      Sentence Count: 15
      Character Count (with spaces): 1,234
      Character Count (without spaces): 1,000
      Average Word Length: 4.5
      Longest Word: "extraordinary" (13 characters)
      Shortest Word: "a" (1 character)
      Unique Words: 150
      
      Top 10 Most Common Words:
      1. the - 25 occurrences
      2. and - 18 occurrences
      3. is - 15 occurrences
      ...
      ```
    - Uses loops to format output
    - Uses if-else for formatting

**Error Handling:**
- Empty text: raise ValueError("Text cannot be empty")
- File not found: raise FileNotFoundError("File not found")
- Invalid file: raise ValueError("Invalid file")
- Use try-except blocks

**Main Program:**
- Test with sample text string
- Test with text file
- Display analysis results
- Test error cases (empty text, non-existent file)
- Test with different text samples

**Example Usage:**
```python
text = "This is a sample text. It has multiple sentences!"
analysis = analyze_text(text)
display_analysis(analysis)
file_analysis = analyze_from_file("sample.txt")
display_analysis(file_analysis)
```

**Skills Practiced:** String Manipulation, Dictionaries, Functions, Loops, Error Handling

---

### 20. Simple Voting System
**Objective:** Conduct and manage votes.

**Detailed Requirements:**

**Data Structure:**
- Dictionary: `candidates` where:
  - Key: candidate name (string)
  - Value: vote count (integer)
- List: `vote_history` to track all votes (optional, for preventing duplicates)
  - Each entry: voter_id (string) or just track if duplicate prevention needed

**Functions to Implement:**

1. `add_candidate(name)`
   - Parameter: name (string)
   - Adds candidate to dictionary with 0 votes
   - Validates name doesn't already exist (case-insensitive)
   - Raises ValueError if candidate exists
   - Returns True if successful

2. `remove_candidate(name)`
   - Parameter: name (string)
   - Removes candidate from dictionary
   - Validates candidate exists
   - Raises KeyError if not found
   - Returns removed candidate's vote count

3. `cast_vote(candidate_name, voter_id=None)`
   - Parameters: candidate_name (string), voter_id (string, optional)
   - Increments vote count for candidate
   - Validates candidate exists (case-insensitive search)
   - If voter_id provided, checks for duplicate votes (optional feature)
   - Uses if-else to check candidate existence
   - Raises ValueError if candidate not found
   - Raises ValueError if duplicate vote (if voter_id tracking enabled)
   - Returns updated vote count

4. `get_vote_count(candidate_name)`
   - Parameter: candidate_name (string)
   - Returns vote count for candidate
   - Uses case-insensitive search
   - Raises KeyError if candidate not found
   - Returns integer

5. `get_results()`
   - Returns dictionary of all candidates and their votes:
     ```python
     {
         "John Doe": 15,
         "Jane Smith": 23,
         "Bob Johnson": 8
     }
     ```
   - Returns copy of candidates dictionary

6. `declare_winner()`
   - Determines winner(s) - handles ties
   - Uses loop to find maximum votes
   - Uses if-elif-else to handle single winner vs. tie
   - Returns:
     - Single winner: tuple ("John Doe", 25)
     - Tie: list of tuples [("John Doe", 25), ("Jane Smith", 25)]
   - Raises ValueError if no candidates or no votes

7. `display_results()`
   - Displays formatted results:
     ```
     Voting Results:
     ==============
     Candidate        Votes
     ----------------------
     Jane Smith       23
     John Doe         15
     Bob Johnson      8
     ----------------------
     Total Votes: 46
     
     Winner: Jane Smith with 23 votes
     ```
   - Sorts by vote count (descending)
   - Uses loops to format and display
   - Shows winner at bottom
   - Uses if-else to format winner display

8. `get_total_votes()`
   - Returns sum of all votes
   - Uses loop to sum vote counts
   - Returns integer

9. `get_percentage(candidate_name)`
   - Parameter: candidate_name (string)
   - Calculates percentage of total votes
   - Uses get_vote_count() and get_total_votes()
   - Uses if-else to handle division by zero
   - Returns float rounded to 2 decimals
   - Returns 0.0 if no votes

10. `reset_votes()`
    - Resets all vote counts to 0
    - Keeps candidates
    - Uses loop to update all values
    - Returns number of candidates reset

11. `get_statistics()`
    - Returns dictionary:
      ```python
      {
          "total_candidates": 3,
          "total_votes": 46,
          "average_votes": 15.33,
          "winner": ("Jane Smith", 23)
      }
      ```
    - Uses loops to calculate
    - Calls declare_winner()

**Error Handling:**
- Candidate not found: raise KeyError("Candidate not found")
- Duplicate candidate: raise ValueError("Candidate already exists")
- Duplicate vote (if tracking): raise ValueError("Vote already cast by this voter")
- No candidates: raise ValueError("No candidates available")
- No votes: raise ValueError("No votes cast yet")
- Use try-except blocks

**Main Program:**
- Add multiple candidates
- Cast votes for different candidates
- Display results
- Declare winner
- Test statistics
- Test error cases (invalid candidate, duplicate votes if tracking)
- Test tie scenario

**Example Usage:**
```python
add_candidate("John Doe")
add_candidate("Jane Smith")
add_candidate("Bob Johnson")
cast_vote("John Doe")
cast_vote("Jane Smith")
cast_vote("Jane Smith")  # Another vote for Jane
results = get_results()
winner = declare_winner()  # Returns ("Jane Smith", 2)
display_results()
stats = get_statistics()
```

**Skills Practiced:** Dictionaries, Functions, Loops, Control Flow, Error Handling

---

## Tips for Practice

1. **Start Simple:** Begin with beginner problems and gradually move to intermediate
2. **Read Requirements Carefully:** Make sure you understand what's needed before coding
3. **Plan First:** Think about data structures and functions you'll need
4. **Test Thoroughly:** Try edge cases and error scenarios
5. **Refactor:** After getting it working, see if you can improve the code
6. **Add Features:** Once basic requirements are met, add your own enhancements
7. **Use Error Handling:** Always include try-except blocks where appropriate
8. **Format Output:** Make your programs user-friendly with nice formatting

---

## Bonus Challenges (After Completing Above)

- Add file persistence (save/load data) to any of the above programs
- Add a simple GUI using `tkinter` for any application
- Convert any program to use command-line arguments with `argparse`
- Add logging functionality to track program execution
- Create unit tests for your functions using `unittest` or `pytest`

---

**Happy Coding! 🐍**

