from tkinter import *
class LoanCalculator:
    def __init__(self):
        lcr = Tk()
        lcr.title("Loan Calculator")     
        Label(lcr,text="Annual Interest Rate").grid(row=1, column=1, sticky=W)
        Label(lcr,text="Number of Years").grid(row=2, column=1, sticky=W)
        Label(lcr,text="Loan Amount").grid(row=3, column=1, sticky=W)
        Label(lcr,text="Monthly Payment").grid(row=4, column=1, sticky=W)
        Label(lcr,text="Total Payment").grid(row=5, column=1, sticky=W)
        self.annualInterestRateVar = StringVar()
        Entry(lcr, textvariable=self.annualInterestRateVar,justify=LEFT).grid(row=1, column=2)
        self.numberofYearsVar = StringVar()
        Entry(lcr, textvariable=self.numberofYearsVar,justify=LEFT).grid(row=2, column=2)
        self.loanAmountVar = StringVar()
        Entry(lcr, textvariable=self.loanAmountVar,justify=LEFT).grid(row=3, column=2)
        self.monthlyPaymentVar = StringVar()
        lbl_monthly_payment = Label(lcr,textvariable=self.monthlyPaymentVar).grid(row=4, column=2, sticky=E)
        self.totalPaymentVar = StringVar()
        lbl_total_payment = Label(lcr,textvariable=self.totalPaymentVar).grid(row=5, column=2, sticky=E)
        bt_compute_payment = Button(lcr, text="Compute Payment", command=self.computePayment).grid(row=6, column=1, sticky=E)
        bt_clear = Button(lcr, text="Clear",command=self.delete_all).grid(row=6, column=2, padx=14, pady=25, sticky=E)
        lcr.mainloop()
        
    def computePayment(self):
        monthlyPayment = self.getMonthlyPayment(
            float(self.loanAmountVar.get()),
            float(self.annualInterestRateVar.get()) / 1200,
            int(self.numberofYearsVar.get()))
        self.monthlyPaymentVar.set(format(monthlyPayment, "10.2f"))
        totalPayment = float(self.monthlyPaymentVar.get()) * 12 \
            * int(self.numberofYearsVar.get())
        self.totalPaymentVar.set(format(totalPayment, "10.2f"))
    def getMonthlyPayment(self, loanAmount, monthlyInterestRate, numberofYears):
        monthlyPayment = loanAmount * monthlyInterestRate / \
            (1-1/(1 + monthlyInterestRate) ** (numberofYears * 12))
        return monthlyPayment
    def delete_all(self):
        self.monthlyPaymentVar.set("")
        self.loanAmountVar.set("")
        self.annualInterestRateVar.set("")
        self.numberofYearsVar.set("")
        self.totalPaymentVar.set("")     
LoanCalculator()
