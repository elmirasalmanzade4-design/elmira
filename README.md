# elmira
# This Python project, “Smart Expense Tracker,” analyzes user expenses by category. It calculates total spending, category-wise distribution, and identifies the highest expense area. The project helps develop skills in data analysis, data structuring, and basic programming for real-world financial insights.
expenses = [
    {"category": "food", "amount": 12},
    {"category": "transport", "amount": 5},
    {"category": "food", "amount": 20},
    {"category": "study", "amount": 15},
    {"category": "transport", "amount": 10}
]

total = 0
category_sum = {}

for item in expenses:
    amount = item["amount"]
    category = item["category"]

    total += amount

    if category in category_sum:
        category_sum[category] += amount
    else:
        category_sum[category] = amount

print("Total expenses:", total)

print("\nExpenses by category:")
for cat, val in category_sum.items():
    print(cat, ":", val)

most_expensive_category = max(category_sum, key=category_sum.get)
print("\nMost expensive category:", most_expensive_category)
