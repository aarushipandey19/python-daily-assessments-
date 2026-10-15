# python-daily-assessments-
for i in range(1, 21):
    if i % 2 == 0:
        print(i)

for i in range(1, 21):
    if i % 2 != 0:
        print(i)
for i in range(5, 51, 5):
    print(i)

    sum = 0

for i in range(1, 11):
    sum = sum + i

    print("Sum =", sum)


total = 0

for i in range(2, 101, 2):
    total = total + i

print("Sum of even numbers =", total)


total = 0

for i in range(1, 101, 2):
    total = total + i

print("Sum of odd numbers =", total)

for i in range(1, 11):
    print(7, "x", i, "=", 7 * i)


num = int(input("Enter a number: "))

for i in range(1, 11):
    print(num, "x", i, "=", num * i)

for i in range(1, 101):
    if i % 3 == 0 and i % 5 == 0:
        print(i)

even = 0
odd = 0

for i in range(1, 51):
    if i % 2 == 0:
        even = even + 1
    else:
        odd = odd + 1

print("Even numbers count =", even)
print("Odd numbers count =", odd)

balance = 5000

amount = int(input("Enter withdrawal amount: "))

if amount <= 0:
    print("Invalid withdrawal amount")
elif amount > balance:
    print("Insufficient balance")
else:
    balance = balance - amount
    print("Withdrawal successful!")
    print("Remaining balance =", balance)

sub1 = float(input("Enter marks of Subject 1: "))
sub2 = float(input("Enter marks of Subject 2: "))
sub3 = float(input("Enter marks of Subject 3: "))

total = sub1 + sub2 + sub3
percentage = total / 3

print("Total Marks =", total)
print("Percentage =", percentage, "%")

# Loan Eligibility Program

age = int(input("Enter your age: "))
income = float(input("Enter your monthly income: "))
credit_score = int(input("Enter your credit score: "))

if age >= 21 and income >= 25000 and credit_score >= 650:
    print("Congratulations! You are eligible for a loan.")
else:
    print("Sorry! You are not eligible for a loan.")

    if age < 21:
        print("- Age must be at least 21 years.")
    if income < 25000:
        print("- Monthly income must be at least ₹25,000.")
    if credit_score < 650:
        print("- Credit score must be at least 650.")

# Online Shopping Discount Program

amount = float(input("Enter purchase amount: "))

if amount > 5000:
    discount = amount * 0.20
elif amount > 2000:
    discount = amount * 0.10
else:
    discount = amount * 0.05

final_amount = amount - discount

print("Purchase Amount:", amount)
print("Discount:", discount)
print("Final Amount to Pay:", final_amount)

# Simple Login System

username = input("Enter Username: ")
password = input("Enter Password: ")

# Stored credentials
correct_username = "admin"
correct_password = "1234"

if username == correct_username and password == correct_password:
    print("Login Successful!")
else:
    print("Invalid Username or Password!")

# Movie Ticket Booking System

movie_name = input("Enter Movie Name: ")
ticket_price = 200

num_tickets = int(input("Enter Number of Tickets: "))

total_amount = ticket_price * num_tickets

print("\n----- Booking Details -----")
print("Movie Name:", movie_name)
print("Number of Tickets:", num_tickets)
print("Ticket Price: ₹", ticket_price)
print("Total Amount: ₹", total_amount)

confirm = input("Confirm Booking (yes/no): ")

if confirm.lower() == "yes":
    print("Booking Successful!")
else:
    print("Booking Cancelled!")
units = float(input("Enter the number of units consumed: "))
bill = 0

# Calculate base bill based on slabs
if units <= 100:
    bill = units * 5
elif units <= 200:
    bill = (100 * 5) + (units - 100) * 7
elif units <= 300:
    bill = (100 * 5) + (100 * 7) + (units - 200) * 10
else:
    bill = (100 * 5) + (100 * 7) + (100 * 10) + (units - 300) * 15

# Apply 10% surcharge if the bill exceeds ₹3000
if bill > 3000:
    bill += bill * 0.10

print(f"Total Electricity Bill: ₹{bill:.2f}")


def calculate_bonus(experience, salary, performance):
    # Step 1: Check the minimum experience condition
    if experience < 1:
        return 0  # No bonus if experience is less than 1 year

    # Step 2: Check salary tiers
    if salary >= 50000:
        if performance >= 90:
            return 20
        elif performance >= 75:
            return 10
        else:
            return 5

    else:  # Salary < 50,000
        if performance >= 90:
            return 15
        else:
            return 5

age = 20
has_learner_license = True
driving_test_score = 75

# Checking the conditions using logical AND
if age >= 18 and has_learner_license and driving_test_score >= 60:
    print("Eligible for a Driving License.")
else:
    print("Not eligible for a Driving License.")


def atm_withdrawal(pin_correct, account_active, current_balance, amount, extra_verification_passed=False):
    # 1. Check Security and Account Status
    if not pin_correct:
        return "Transaction Declined: Incorrect PIN."
    if not account_active:
        return "Transaction Declined: Account is inactive."

    # 2. Check Amount Validity
    if amount <= 0:
        return "Transaction Declined: Amount must be positive."
    if amount % 100 != 0:
        return "Transaction Declined: Amount must be a multiple of ₹100."

    # 3. Check Balance and Post-Withdrawal Threshold
    if amount > current_balance:
        return "Transaction Declined: Insufficient balance."
    if (current_balance - amount) < 500:
        return "Transaction Declined: Minimum balance of ₹500 must remain after withdrawal."
