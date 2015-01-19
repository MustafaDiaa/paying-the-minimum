"""paying-the-minimum
program to calculate the credit card balance after one year if a person only pays the minimum monthly payment required by the credit card company each month."""

balance = 4213              #credit card original balance
annualInterestRate = 0.2              #constant annual interest rate
monthlyPaymentRate = 0.04              #monthly pay rate constant at each month
monthlyInterestRate = annualInterestRate / 12.0              #interest rate each month
totalPaid = 0.0              #initial value for totalPaid
count = 1              #begining loop variable

for count in range(1, 13):              #calculating (remainingBalance & totalPaid) after 12 months
    minMonthlyPayment = monthlyPaymentRate * balance              #minMonthlyPayment for each month
    monthlyUnpBalance = balance - minMonthlyPayment              #unpaidBalance for each month
    remainingBalance = monthlyUnpBalance + (monthlyInterestRate * monthlyUnpBalance)          #remainingBalance after each month
    balance = remainingBalance              #assign old remainingBalance to balance
    totalPaid = totalPaid + minMonthlyPayment              #totalPaid for each month
    print 'Month: ' + str(count)
    print 'Minimum monthly payment: ' + str(round(minMonthlyPayment, 2))
    print 'Remaining balance: ' + str(round(remainingBalance, 2))
print 'Total paid: ' + str(round(totalPaid, 2))              #totalPaid after 12 months
print 'Remaining balance: ' + str(round(remainingBalance, 2))              #remainingBalance after 12 months
