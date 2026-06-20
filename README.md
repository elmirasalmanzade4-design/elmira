# elmira
# This Python project, “Smart Expense Tracker,” analyzes user expenses by category. It calculates total spending, category-wise distribution, and identifies the highest expense area. The project helps develop skills in data analysis, data structuring, and basic programming for real-world financial insights.
from collections import defaultdict

expenses = []
n = int(input("How many expenses? "))
for i in range(n):
    category = input("Enter category: ")
    try:
        amount = float(input("Enter amount: "))
    except ValueError:
        print("Invalid amount, skipping this entry.")
        continue
    expenses.append({"category": category, "amount": amount})

total = 0
category_sum = defaultdict(float)
for item in expenses:
    total += item["amount"]
    category_sum[item["category"]] += item["amount"]

print(f"\nTotal expenses: {total:.2f}")
print("\nBy category:")
for cat, val in category_sum.items():
    print(f"{cat} : {val:.2f}")

if category_sum:
    print("\nMost expensive category:", max(category_sum, key=category_sum.get))
else:
    print("\nNo expenses recorded.")
