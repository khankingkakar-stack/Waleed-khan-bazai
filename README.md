# Waleed-khan-bazai
Assignment no 7 sql
# Python Assignment: Lists, Dictionaries, Loops, and Conditional Statements
# Author: Your Name
# Description: Solutions to Questions 1–6.

# ============================================================
# QUESTION 1: Working with Lists
# ============================================================

# Create a list containing at least 8 integers.
numbers = [12, 7, 24, 15, 8, 31, 42, 19]

print("\nQUESTION 1: Working with Lists")
print("Numbers in the list:")

# Print each number and calculate the sum using a loop.
total = 0
for number in numbers:
    print(number)
    total += number

print("Sum of all numbers:", total)

# Print only even numbers using a conditional statement.
print("Even numbers:")
for number in numbers:
    if number % 2 == 0:
        print(number)


# ============================================================
# QUESTION 2: Dictionary Basics
# ============================================================

# The marks value is a list containing three marks.
student = {
    "name": "Ali",
    "age": 20,
    "course": "Python Programming",
    "marks": [75, 82, 68]
}

print("\nQUESTION 2: Dictionary Basics")
print("Student details:")

# Display every key and its value.
for key, value in student.items():
    print(f"{key}: {value}")

# Calculate the average using a loop.
marks_total = 0
for mark in student["marks"]:
    marks_total += mark

average = marks_total / len(student["marks"])
print(f"Average marks: {average:.2f}")

# Decide whether the student passed or failed.
if average >= 50:
    print("Result: Passed")
else:
    print("Result: Failed")


# ============================================================
# QUESTION 3: List of Dictionaries
# ============================================================

# Each employee is represented by a dictionary.
employees = [
    {"name": "Ayesha", "department": "HR", "salary": 65000},
    {"name": "Bilal", "department": "Finance", "salary": 72000},
    {"name": "Sara", "department": "IT", "salary": 80000}
]

print("\nQUESTION 3: List of Dictionaries")
print("Employee details:")

total_salary = 0
highest_paid_employee = employees[0]

# Process all employees, calculate total salary, and find the highest salary.
for employee in employees:
    print(
        f"Name: {employee['name']}, "
        f"Department: {employee['department']}, "
        f"Salary: Rs. {employee['salary']:,}"
    )

    total_salary += employee["salary"]

    if employee["salary"] > highest_paid_employee["salary"]:
        highest_paid_employee = employee

print(
    f"Employee with the highest salary: "
    f"{highest_paid_employee['name']} "
    f"(Rs. {highest_paid_employee['salary']:,})"
)
print(f"Total salary expense: Rs. {total_salary:,}")


# ============================================================
# QUESTION 4: While Loop with User Input
# ============================================================

print("\nQUESTION 4: While Loop with User Input")
print("Enter numbers one by one. Enter -1 to stop.")

user_numbers = []

while True:
    try:
        user_input = int(input("Enter a number (-1 to stop): "))
    except ValueError:
        print("Invalid input. Please enter a whole number.")
        continue

    # -1 is the stopping value and is not added to the list.
    if user_input == -1:
        break

    user_numbers.append(user_input)

print("Complete list:", user_numbers)

# Avoid min() and max() errors if the user enters -1 immediately.
if user_numbers:
    largest = user_numbers[0]
    smallest = user_numbers[0]

    for number in user_numbers:
        if number > largest:
            largest = number
        if number < smallest:
            smallest = number

    print("Largest number:", largest)
    print("Smallest number:", smallest)
else:
    print("No numbers were entered, so largest and smallest cannot be calculated.")


# ============================================================
# QUESTION 5: Word Frequency Counter
# ============================================================

print("\nQUESTION 5: Word Frequency Counter")
sentence = input("Enter a sentence: ")

# Convert the sentence to lowercase and split it into words.
words = sentence.lower().split()
word_frequency = {}

# Count each word using a dictionary.
for word in words:
    # Remove common punctuation from the beginning and end of each word.
    word = word.strip(".,!?;:\"'()[]{}")
    

    if word:  # Ignore empty strings.
        if word in word_frequency:
            word_frequency[word] += 1
        else:
            word_frequency[word] = 1

print("Word frequency:")
if word_frequency:
    for word, count in word_frequency.items():
        print(f"{word}: {count}")
else:
    print("No words were entered.")


# ============================================================
# QUESTION 6: Nested Loops – Multiplication Table
# ============================================================

print("\nQUESTION 6: Multiplication Table (1 to 5)")

# The outer loop selects the row; the inner loop prints each product.
for row in range(1, 6):
    for column in range(1, 6):
        print(f"{row * column:4}", end="")
    print()  # Move to the next line after each row.
