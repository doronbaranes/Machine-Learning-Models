# Bank-Account-Python-Project
Created on Mon Jan  3 07:15:34 2022

@author: Doron Baranes
"""
import statistics
ils_cash = int()
main_nevigator = int()
total_ils_deposits = int()
total_dolar_deposits = int()
total_ils_withdrawals = int()
total_dolar_withdrawals = int()
currency_type = int()
dolar_deposit_amount = int()
dolar_withdrawals_amount = int()
ils_deposit_amount = int()
ils_withdrawals_amount = int()
main_nevigator = int()
all_name_account = []
name = str()

class bank_account:
    def __init__(self, name, i_d, password, email, date_of_birth, physical_address, bank_account_number, phone_number, grandmother_name, total_ils_deposits=0, total_dolar_deposits = 0, total_ils_withdrawals=0, total_dolar_withdrawals=0, counter_account_actions = 0, action_saver = list([0]), dolar_deposit_action_saver = list([0]), ils_deposit_action_saver = list([0]), dolar_withdrawal_action_saver = list([0]), ils_withdrawal_action_saver = list([0]), st_sheet = list([0])):
        self.name = name
        self.i_d = i_d
        self.email = email
        self.password = password
        self.bank_account_number = bank_account_number
        self.date_of_birth = date_of_birth
        self.physical_address = physical_address
        self.phone_number = phone_number
        self.grandmother_name = grandmother_name
        self.total_ils_deposits = total_ils_deposits
        self.total_dolar_deposits = total_dolar_deposits
        self.total_ils_withdrawals = total_ils_withdrawals
        self.total_dolar_withdrawals = total_dolar_withdrawals    
        self.counter_account_actions = counter_account_actions
        self.action_saver = []
        self.dolar_deposit_action_saver = [0]
        self.ils_deposit_action_saver = [0]
        self.dolar_withdrawal_action_saver = [0]
        self.ils_withdrawal_action_saver = [0]  
        self.st_sheet = []
       
    def balance_inquiry(self, x):
        ils_cash = all_name_account[x].total_ils_deposits - all_name_account[x].total_ils_withdrawals
        dolar_cash = all_name_account[x].total_dolar_deposits - all_name_account[x].total_dolar_withdrawals
        print(f"""your cash balance on account name {all_name_account[x].name} is: \n{ils_cash} ILS \n{dolar_cash} dolars""")
       
    def deposit(self, x):
        ils_deposit_amount = str()
        dolar_deposit_amount = str()
        currency_type = str(input("""Which currency you wish to deposit (dollar/ILS):
press 1 for deposit dolars
press 2 for deposit ILS
If your answer is out of the options the default is in ILS
Enter you choise here: """))
        if currency_type == "1":
            t=0
            while t<6:
                try:
                    dolar_deposit_amount = int(input("Please enter your dolar deposit amount: "))
                    print(f"{dolar_deposit_amount} dolars added to account name: {all_name_account[x].name}")
                    all_name_account[x].total_dolar_deposits += dolar_deposit_amount
                    print("The total deposit amount is: ", all_name_account[x].total_dolar_deposits)
                    if not dolar_deposit_amount == 0:
                        all_name_account[x].action_saver.append(str(dolar_deposit_amount))
                        all_name_account[x].action_saver.append("$")
                        all_name_account[x].action_saver[-1] = all_name_account[x].action_saver[-2] +" "+ all_name_account[x].action_saver.pop(-1)
                        all_name_account[x].counter_account_actions += 1
                    break
                except:
                    print("you made no deposit\nplease try to insert the exact deposit numbers you wish.")
                    print(f"you have {5-t} tries left")
                    t+=1
               
        else:
            t=0
            while t < 6:
                try:
                    ils_deposit_amount = int(input("Please enter your ILS deposit amount: "))
                    print(f"{ils_deposit_amount} ILS added to account name: {all_name_account[x].name}")
                    all_name_account[x].total_ils_deposits += ils_deposit_amount
                    print("The total deposit amount is: ", all_name_account[x].total_ils_deposits)
                    if not ils_deposit_amount == 0:
                        all_name_account[x].action_saver.append(str(ils_deposit_amount))
                        all_name_account[x].action_saver.append("₪")
                        all_name_account[x].action_saver[-1] = all_name_account[x].action_saver[-2] +" "+ all_name_account[x].action_saver.pop(-1)
                        all_name_account[x].counter_account_actions += 1
                    break
                except:
                    print("you made no deposit\nplease try to insert the exact deposit numbers you wish.")
                    print(f"you have {5-t} tries left")
                    t+=1
   
       
                   
    def cash_withdrawals(self, x):
        dolar_withdrawals_amount = str()
        ils_withdrawals_amount = str()
        currency_type = str(input("""Which currency you wish to withdrawal (dollar/ILS):
press 1 for withdrawal dolars
press 2 for withdrawal ILS
If your answer is out of the options the default is in ILS
Enter you choise here: """))
        if currency_type == "1":
            t=0
            while t<6:
                try:
                    dolar_withdrawals_amount = int(input("Please enter your dolar withdrawal amount: "))
                    print(f"{dolar_withdrawals_amount} dolars drawn from account name: {all_name_account[x].name}")
                    all_name_account[x].total_dolar_withdrawals += dolar_withdrawals_amount
                    print("The total withdrawal amount is: ", all_name_account[x].total_dolar_withdrawals)
                    if not dolar_withdrawals_amount == 0:
                        all_name_account[x].action_saver.append(str(dolar_withdrawals_amount))
                        all_name_account[x].action_saver.append("$")
                        all_name_account[x].action_saver[-1] = "-" + all_name_account[x].action_saver[-2] +" "+ all_name_account[x].action_saver.pop(-1)
                        all_name_account[x].counter_account_actions += 1
                    break
                except:
                    print("you made no withdrawal\nplease try to insert the exact withdrawal numbers you wish.")
                    print(f"you have {5-t} tries left")
                    t+=1
               
        else:
            t=0
            while t < 6:
                try:
                    ils_withdrawals_amount = int(input("Please enter your ILS withdrawal amount: "))
                    print(f"{ils_withdrawals_amount} ILS drawn to account name: {all_name_account[x].name}")
                    all_name_account[x].total_ils_withdrawals += ils_withdrawals_amount
                    print("The total withdrawal amount is: ", all_name_account[x].total_ils_withdrawals)
                    if not ils_withdrawals_amount == 0:
                        all_name_account[x].action_saver.append(str(ils_withdrawals_amount))
                        all_name_account[x].action_saver.append("₪")
                        all_name_account[x].action_saver[-1] = "-" + all_name_account[x].action_saver[-2] +" "+ all_name_account[x].action_saver.pop(-1)
                        all_name_account[x].counter_account_actions += 1
                    break
                except:
                    print("you made no withdrawal\nplease try to insert the exact withdrawal numbers you wish.")
                    print(f"you have {5-t} tries left")
                    t+=1
           
    def add_action(self, x, value):
        print("All Transactions Ordered by Newest Transactions First ")
        for i in range(value):
            print(f"transaction NO.{i+1} is: {all_name_account[x].action_saver[-1-i]}")
           
    def balance_sheet(self, x):
        action_loop = 1
        while action_loop == 1:
            v = int(input("how many action wish you like to see? "))
            if len(all_name_account[x].action_saver) == 0:
                print("you have no actions to show")
                action_loop = 0
               
            elif v>len(all_name_account[x].action_saver):
                print(f"your max actions is: {len(all_name_account[x].action_saver)}\nPlease enter a number no greater than {len(all_name_account[x].action_saver)}")
                to_exit_transactions = input("If you wish to exit press 9\nelse press ok or every other key: ")
                if to_exit_transactions == "9":
                    action_loop = 0
                   
            else:
                all_name_account[x].add_action(x, v)
                to_download = input("do you wish to download the printed transactions? \nfor yes press 'y' and than 'ok' \notherwise, press any other key and than 'ok'\nyour answer is: ")
                if to_download == "y":
                    all_name_account[x].download_balance_sheet(x,v)
                action_loop = 0
   
    def download_balance_sheet(self, x, v):
        print(f"All Transactions Downloaded and Ordered by Newest Transactions First to cvs file name: Balance Sheet of {all_name_account[x].name}")
        with open(f"Balance Sheet {all_name_account[x].name}.csv", 'w') as f:
            f.writelines(f"DB Investing Bank\nBalance Sheet for {all_name_account[x].name}\naccount NO.: {all_name_account[x].bank_account_number}\n")
            f.writelines(f"Address: {all_name_account[x].physical_address}\n")
            f.writelines(f"Phone Number: {all_name_account[x].phone_number}\n")
            all_lines = [f"transaction NO.{i+1}:,{all_name_account[x].action_saver[-1-i]}" + "\n" for i in range(v)]
            f.writelines(all_lines)
   
    def downloader(self, x):
        action_loop = 1
        while action_loop == 1:
            v = int(input("how many action wish you like to see? "))
            if len(all_name_account[x].action_saver) == 0:
                print("you have no actions to show")
                action_loop = 0
               
            elif v>len(all_name_account[x].action_saver):
                print(f"your max actions is: {len(all_name_account[x].action_saver)}\nPlease enter a number no greater than {len(all_name_account[x].action_saver)}")
                to_exit_transactions = input("If you wish to exit press 9\nelse press ok or every other key: ")
                if to_exit_transactions == "9":
                    action_loop = 0
                   
            else:
                all_name_account[x].add_action(x, v)
                all_name_account[x].download_balance_sheet(x,v)
               
    def download_statistics(self, x):
        print(f"statistic {all_name_account[x].name} downloaded")
        with open(f"statistic for {all_name_account[x].name}.csv", 'w') as f:
            f.writelines(f"statistcs for acount name:, {all_name_account[x].name}\n")
            f.writelines(f"Address:, {all_name_account[x].physical_address}\n")
            f.writelines(f"Phone Number:, {all_name_account[x].phone_number}\n")
            for l in range(len(all_name_account[x].st_sheet)):
                if l%2 == 0:
                    f.writelines((f"{all_name_account[x].st_sheet[l]}, {all_name_account[x].st_sheet[l+1]}\n"))
   
    def statistics(self, x):
        for i in range(len(all_name_account[x].action_saver)):
            for j in range(len(all_name_account[x].action_saver[i])):
               
                if all_name_account[x].action_saver[i][j] == "₪":
                    if all_name_account[x].action_saver[i][0] == "-":
                        all_name_account[x].ils_withdrawal_action_saver.append(float(all_name_account[x].action_saver[i][:-2]))
                    else:
                        all_name_account[x].ils_deposit_action_saver.append(float(all_name_account[x].action_saver[i][:-2]))
               
                if all_name_account[x].action_saver[i][j] == "$":
                    if all_name_account[x].action_saver[i][0] == "-":
                        all_name_account[x].dolar_withdrawal_action_saver.append(float(all_name_account[x].action_saver[i][:-2]))
                    else:
                        all_name_account[x].dolar_deposit_action_saver.append(float(all_name_account[x].action_saver[i][:-2]))

        all_name_account[x].st_sheet.extend([            
        "Your Total Dolar Deposits: ", round(sum([k for k in all_name_account[x].dolar_deposit_action_saver]),2),
        "Your Total ils Deposits: ", round(sum([k for k in all_name_account[x].ils_deposit_action_saver]),2),
        "Your Total Dolar withdrawals: ", round(sum([k for k in all_name_account[x].dolar_withdrawal_action_saver]),2),
        "Your Total ils withdrawals: ", round(sum([k for k in all_name_account[x].ils_withdrawal_action_saver]),2),
        "Your Average for all Dolar Deposits: ", round(statistics.mean(all_name_account[x].dolar_deposit_action_saver),2),
        "Your Average for all ils Deposits: ", round(statistics.mean(all_name_account[x].ils_deposit_action_saver),2),
        "Your Average for all Dolar Withdrawals: ", round(statistics.mean(all_name_account[x].dolar_withdrawal_action_saver),2),
        "Your Average for all ils Withdrawals: ", round(statistics.mean(all_name_account[x].ils_withdrawal_action_saver),2),
        "Your total Cash balance (dolar + ils) in ils: ", round(sum([sum([(lambda x: x*3.15)(l) for l in all_name_account[x].dolar_deposit_action_saver]),
                                                                     sum([(lambda x: x*3.15)(l) for l in all_name_account[x].dolar_withdrawal_action_saver]),
                                                                     sum([t for t in all_name_account[x].ils_deposit_action_saver]),
                                                                     sum([t for t in all_name_account[x].ils_withdrawal_action_saver])]),2)])
        for l in range(len(all_name_account[x].st_sheet)):
            if l%2 == 0:
                print(f"{all_name_account[x].st_sheet[l]} {all_name_account[x].st_sheet[l+1]}")
           
        p = input("whould you like to download statistics? \nfor download please press 1: ")
        if p == "1":
            all_name_account[x].download_statistics(x)

def has_numbers(s):
    return any(char.isdigit() for char in s)

def password_check_f(p):
    u_c_counter = int(0)
    l_c_counter = int(0)
    d_counter = int(0)
    for c in range(len(p)):
        if p[c].isupper():
            u_c_counter += 1
        if p[c].islower():
            l_c_counter += 1
        if p[c].isdigit():
            d_counter += 1
    if len(p) > 7 and u_c_counter >0 and d_counter > 1:
        return True
    else:
        return False

def date_of_birth_check(d):
    if d[:2].isdigit():
        if int(d[:2]) < 32:
            if d[2] == "/":
                if d[3:5].isdigit():
                    if int(d[3:5]) < 13:
                        if d[5] == "/":
                            if d[6:].isdigit() and (d[6] == "1" or d[6] == "2") and len(d) < 11:
                                return True
    return False
                   
def open_a_new_account():
   
    # name loop
    while True:
        try:
            name = str(input("Enter Your Name: "))
            if has_numbers(name):
                print(2/0)
            else:
                break
        except:
            print("your mentioned name contain an number \nplease try again")
            continue
       
    # id loop
    while True:
        try:
            i_d = int(input("Enter your ID number: "))
            if len(str(i_d)) > 9 or len(str(i_d))<7:
                print("your mentioned ID missing numbers\nPlease try again")
                continue
            break
        except:
            print("your mentioned ID conains an characters \nPlease try again")
            continue
       
    # password loop    
    while True:
        try:
            password = str(input("""Enter a new password
must include:
1. at least 8 character
2. at least 1 uppercase
3. at least 1 lowercase
4. at least 2 numbers
Enter your password here: """))
            if not password_check_f(password):
                print(2/0)
            pass_check = str(input("Confirm your password: "))
            if password == pass_check:
                break
            else:
                print("confirmation failed")
                print(2/0)
        except:
            print("your password is no as required\nPlease try again")
            continue
       
    # date of birth loop
    while True:
        try:
            date_of_birth = str(input("""Enter your date of birth in a form of __/__/____
Enter here: """))
            if date_of_birth_check(date_of_birth):
                break
            else:
                print(2/0)
        except:
            print("the entered date of birth format is out of requires.\nPlease try again")
            continue
               
    physical_address = input("Enter your physical address: ")
   
    # phone number loop
    while True:
        try:
            phone_number = str(input("Enter your phone number (only digits): "))
            if len(str(phone_number)) > 15 or len(str(phone_number))<7:
                print("your mentioned phone number missing \nPlease try again")
                continue
            break
        except:
            print("your mentioned phone number missing \nPlease try again")
            continue
   
    # grandmother name loop
    while True:
        try:
            grandmother_name = str(input("Enter your grandmother name (for security identify): "))
            if has_numbers(grandmother_name):
                print(2/0)
            else:
                break
        except:
            print("your mentioned name contain an number \nplease try again")
            continue
   
    email = input("Enter your email address: ")
    import random
    bank_account_number = round(random.uniform(100000,199999))
    name = bank_account(name, i_d, password, email, date_of_birth, physical_address, bank_account_number, phone_number, grandmother_name, total_ils_deposits, total_dolar_deposits, total_ils_withdrawals, total_dolar_withdrawals)
    all_name_account.append(name)
    print(f"""
Your details is:
name: {all_name_account[-1].name}
ID: {all_name_account[-1].i_d}
Bank Account Number: {all_name_account[-1].bank_account_number}
Phone Number: {all_name_account[-1].phone_number}
Mail Address: {all_name_account[-1].email}""")
    print("Your Bank Account details has been confirm and sent to the secretariat for approvall.\nThank You, And Have a Great Day")


def morning_run():
    on = 1
    while on==1:
        main_nevigator = input("""Please enter a number according the following options:
    1.Open a New Account
    2.Exist Account
    9.For Exit Press 9
    Enter your choise here: """)
        if main_nevigator == "1":
            open_a_new_account()
        elif main_nevigator == "2":
            t=0
            while t < 3:
                n = input("enter your name for access to your account: ")
                id_num = input("enter your id number: ")
                p = input("enter your password: ")
                t += 1
                i=0
               
                while i<(len(all_name_account)):
                    i += 1
                    x = int()
                    if all_name_account[i-1].name == n and str(all_name_account[i-1].i_d) == str(id_num) and all_name_account[i-1].password == p:
                        x = i-1
                        account_nevi_on = 1
                        while account_nevi_on == 1:
                            main_nevigator_for_exist_account = input("""
                                                                             1.Balance Inquiry                                                                
                                                                             2.Deposit
                                                                             3.Cash Withdrawals
                                                                             4.Balance Transfers
                                                                             5.Download Balance Transfers
                                                                             6.Balance Statistics
                                                                             7.For Exit Press 9
                                                                             Enter your choise here: """)
                           
                            if main_nevigator_for_exist_account == "1":
                                all_name_account[x].balance_inquiry(x)
                            elif main_nevigator_for_exist_account == "2":
                                all_name_account[x].deposit(x)
                            elif main_nevigator_for_exist_account == "3":
                                all_name_account[x].cash_withdrawals(x)
                            elif main_nevigator_for_exist_account == "4":
                                all_name_account[x].balance_sheet(x)
                            elif main_nevigator_for_exist_account == "5":
                                all_name_account[x].downloader(x)
                            elif main_nevigator_for_exist_account == "6":
                                all_name_account[x].statistics(x)
                            elif main_nevigator_for_exist_account == "9":
                                account_nevi_on = 0
                                t=3
                                i=len(all_name_account)
                                break
                    elif i==len(all_name_account):
                        print(f"one or more of your idetify details failed, {3-t} attempts remaining")
                    elif 3-t == 0:
                            print("ALERM ALERM ALERM")
                            break
            print("Good bye and Have a Great Day")
        elif main_nevigator == "9":
            on = 0
            print("turn off the machine")

morning_run()
