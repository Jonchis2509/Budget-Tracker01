# 💰 Budget Tracker – Python Console App

This is a simple console-based **Budget Tracker** application written in Python. It allows users to input their **income** and **expenses**, calculates the remaining balance, and stores all the data in a text file for future reference.

This project is part of my **50-Day Python Learning Challenge**, focused on building real-world skills like **file handling**, **exception management**, and **practical input/output** operations.

---

## 🚀 Features

- ✍️ Write and store your income and expenses in a file.
- ➕ Automatically calculate your free budget (remaining balance).
- 📂 Save entries into a human-readable `.txt` file.
- 🔒 Includes error handling for file reading/writing issues.

---

## 📁 File Structure


---

## 🧠 Technologies Used

- Python 3.x
- `open()` for file handling
- Exception handling (`try`, `except`, `finally`)
- `float()` for numerical input
- Formatted strings (f-strings)

---

## 📜 Code

```python
# Budget Tracker

# Create the budget tracker file
budget_tracker = "Budget Tracker.txt"

def create_file():
    with open(budget_tracker, "w") as file:
        title = file.write("--- Welcome to the Budget Tracker file! --- \n")
        return print(title)

# Add income and expenses
def write_file():
    with open(budget_tracker, "w") as file:
        income = float(input("Enter the income: $ "))
        result_1 = file.write(f"Your incomes: ${income:.2f}\n")

        expenses = float(input("Enter the expenses: $ "))
        result_2 = file.write(f"Your expenses: ${expenses:.2f}\n")

        total_free = income - expenses
        result_3 = file.write(f"You have free: ${total_free:.2f}\n")

    return (result_1, result_2, result_3)

# Show current balance
def show_file():
    try:
        with open(budget_tracker, "r") as file:
            content = file.read()
            print(content)
    except FileNotFoundError:
        print("❌ ERROR: The file doesn’t exist.")
    except IOError:
        print("❌ ERROR: The file can’t be read.")
    finally:
        print("✅ File operation completed.")

# Run the program
create_file()
write_file()
show_file()
