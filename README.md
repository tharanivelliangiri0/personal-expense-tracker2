expenses = []


def add_expense():
    date = input("Enter date (DD-MM-YYYY): ")
    category = input("Enter category: ")
    description = input("Enter description: ")
    amount = float(input("Enter amount: ₹"))
    payment_mode = input("Enter payment mode: ")

    expense = {
        "date": date,
        "category": category,
        "description": description,
        "amount": amount,
        "payment_mode": payment_mode
    }

    expenses.append(expense)
    print("\nExpense added successfully!")


def view_expenses():
    if len(expenses) == 0:
        print("\nNo expenses found.")
        return

    print("\n----- EXPENSE RECORDS -----")

    for i, expense in enumerate(expenses, start=1):
        print("\nExpense ID:", i)
        print("Date:", expense["date"])
        print("Category:", expense["category"])
        print("Description:", expense["description"])
        print("Amount: ₹", expense["amount"])
        print("Payment Mode:", expense["payment_mode"])


def search_expense():
    category = input("Enter category to search: ")

    found = False

    for i, expense in enumerate(expenses, start=1):
        if expense["category"].lower() == category.lower():
            print("\nExpense ID:", i)
            print("Date:", expense["date"])
            print("Category:", expense["category"])
            print("Description:", expense["description"])
            print("Amount: ₹", expense["amount"])
            print("Payment Mode:", expense["payment_mode"])
            found = True

    if not found:
        print("\nNo expense found in this category.")