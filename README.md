class sbi:
  def __init__(self):
    self.pin =''
    self.balance = 0
    self.menu()
  def menu(self):
    #constructor are used to initalize everythinng to object when an object is created.
    #it runs automatically when an object is created.
    #we need 1) To store variables.2) to run the code which is not the control of user.
    #in every method,there should be self as parameter.
    #u should only create variables/attributes in constructor.
   user_input=input("""
  Hi how can Ihelp you?
    1. press 1 to cash withdrawl..
    2. press 2 to cash deposit..
    3. press 3 to cash transfer..
    4. press 4 to check balence..
    5. press 6 to exit..
    """)
   if user_input == '1':
       self.create_pin()
   elif user_input == '2':
      self.withdraw()
   elif user_input == '3':
      self.deposit()
   elif user_input == '4':
      self.change_pin()
  def create_pin(self):
        user_pin=input("please enter your pin")
        self.pin=user_pin
        user_balance=int(input("please enter your balance"))
        self.balance=user_balance
        print("pin created successfully")
        self.menu()

  def withdraw(self):
    ask2=input("enter your pin")
    if ask2==self.pin:
      amount=int(input("enter your amount"))
      if amount>self.balance:
        print("insufficient funds")
      else:
        self.balance-=amount
        print('collect your cash',(amount),"you are left with,",(self.balance))
        self.menu()
    else:
      print("bhaaaaaaaaag jaa")
      self.menu()

  def deposit(self):
    ask3=input("enter your pin")
    if ask3==self.pin:
      amount2=int(input("enter the amount to add?Deposit"))
     
      print("your balance has been added,you have",self.balance)
      self.menu() 
    else:
      print("bhag jaa")
      self.menu()

      #change pin
  def change_pin(self):
    old_pin=input("enter old pin")
    if old_pin==self.pin:
     ask4=input("please enter your pin")
     self.pin=ask4
     print("pinchange successful")
     self.menu()
    else:
      print("nai karne de sakta re baba")
      self.menu()      
