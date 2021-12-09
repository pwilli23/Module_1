# Problem 1

First, let's start with some calculations on a list of prices for 5 loans.
    1. Use the `len` function to calculate the total number of loans in the list.
**  To answer the first part of the question, I used the len function to find the total amount of loans in the loan_cost list.  I then printed the variable number_of_loans with a f string **

'number_of_loans = len(loan_costs)
print(f"There are {number_of_loans} total loans")'

    2. Use the `sum` function to calculate the total of all loans in the list.
    3. Using the sum of all loans and the total number of loans, calculate the average loan price.
    4. Print all calculations with descriptive messages.
** To answer the second half of the question, I set the variable total_loan_amount euqal to the sum of all loans in the list by using the sum function. I then printed the total value with a f string. **

'total_loan_amount = sum(loan_costs)
print(f"The total value of all loans is: ${total_loan_amount}")'

** After calculating the sum of the loan list, I used the variable average_loan_amount to calculate the average loan price: **

'average_loan_amount = total_loan_amount/number_of_loans
print(f"The average loan price is: ${average_loan_amount}"'

## Problem 2:

Part 1: Use get() on the dictionary of additional information to extract the Future Value and Remaining Months on the loan.
Print each variable.

** I used the get() on the dictionary to pull the variables out of the dictionary. I used an f string to print the name of the variables and their values **

'future_value = loan["future_value"]
print(f"The future value amount is: ${future_value}")

remaining_months = loan["remaining_months"]
print(f"Total remaining months is {remaining_months}")

loan_price = loan["loan_price"]
print(f"The current loan price is {loan_price} ")'

Part 2:  Use the formula for Present Value to calculate a "fair value" of the loan.
Use a minimum required return of 20% as the discount rate.
** I created the variable present_value to represent the present value formula for the loan.  I then printed the value of present value with a f string.**
'present_value = future_value/ (1+0.2/12)** remaining_months

print(f"The present value of this loan is: ${present_value} ")'

Part 3: Write a conditional statement (an if-else statement) to decide if the present value represents the loan's fair value.
If the present value of the loan is greater than or equal to the cost, then print a message that says the loan is worth at least the cost to buy it.
Else, the present value of the loan is less than the loan cost, then print a message that says that the loan is too expensive and not worth the price.
** I created an if else statement that determined whether or not the loan is worth buying: **

'if present_value >= loan_price:
    print("This loan is at least worth the cost of buying it")
else:
    print("This loan is not worth the cost of buying it")'

###Problem 3: 

 Define a new function that will be used to calculate present value.
    a. This function should include parameters for future_value, remaining_months, and the annual_discount_rate
    b. The function should return the present_value for the loan.
2. Use the function to calculate the present value of the new loan given below.
    a. Use an annual_discount_rate of 0.2 for this new loan calculation.
** I was able to create a function named calculate_present_value that included the future_value, remaining_months, and annual_discount_rate parameters.  In the function body I created a formula for present value and named the variable total.  I then ran a print statement that would print the value of new loan.  After that, I ran a function call that included the values from new_loan. **
'def calculate_present_value(future_value, annual_discount_rate, remaining_months):
    total= future_value / (1 +(annual_discount_rate/12)) ** remaining_months
    print("The present value of new loan is $", total)

calculate_present_value(future_value= 1000, annual_discount_rate =0.20, remaining_months= 12)'

#### Problem 4:
1. Create a new, empty list called `inexpensive_loans`.
2. Use a for loop to select each loan from a list of loans.
    a. Inside the for loop, write an if-statement to determine if the loan_price is less than or equal to 500
    b. If the loan_price is less than or equal to 500 then append that loan to the `inexpensive_loans` list.
3. Print the list of inexpensive_loans.
** I created an empty list called inexpensive_loans.. I then created a loop that included a if statement that would determine if a loan's was less than or equal to $500 in the loan dictionary.  I used the append() function to add loans under $500 to the new inexpensive_loans list. ** 

 'for item in loans:
    if item["loan_price"] <= 500:
        inexpensive_loans.append(item)'

print(inexpensive_loans)'

##### Problem 5:
** I created headers for the inexpensive_loans csv file and then set the output file path to "loan_output.csv".  I then used the csvwriter function to add the headers and inexpensive loan data tomy newly created csv file.**

'header = ["loan_price", "remaining_months", "repayment_interval", "future_value"]

 Set the output file path
csvpath = Path("loan_output.csv")

print("Writing the datav to a csv file...")

 @TODO: Use the csv library and `csv.writer` to write the header row
 and each row of `loan.values()` from the `inexpensive_loans` list.

with open(csvpath, "w") as csvfile:
    csvwriter = csv.writer(csvfile, delimiter=",")

    #Write header row first
    csvwriter.writerow(header)

    #Data rows:
    for row in inexpensive_loans:
        csvwriter.writerow(row.values())'


















