# Object-Oriented-Programming

Date: 2011/6/7

Purpose:

Develope a BankAccount class for Parkville Bank, which contains fields and functions that a BankAccount needs. 
Create a class containing private fields that hold the account number, account balance, and interest rate. Create public member functions for the class.



   class BankAccount{
   
   public:
   BankAccount()
   {
   rate=0;
   
   }
   
   BankAccount(int num,double bal=0.0)
   {
    AccNum=num;
    AccBal=bal;
   }
   
   BankAccount(int Num,double Bal=0.0,double r=0.0)
   {
    AccNum=Num;
    AccBal=Bal;
    rate=r;
    }

   void setAccount(int n,double b)
   {
    AccNum=n;
    AccBal=b;
   }

   void setAccount2(int n,double b,double r)
   {
    AccNum=n;
    AccBal=b;
    rate=r;
    
   }

   double balance()
   {
    double Balan;
    return Balan=AccBal;
    }

   void computeInterest(int x)
   {
   for(int i=1;i<=x;i++)
   {
      AccBal*=(1+rate);
      cout<<"After"<<i<<"year(s),the balance is $"<<AccBal<<endl;
   }
   }


   void displayAccount()
   {
   cout<<"Account number #"<<AccNum<<"has a balance of $"<<AccBal<<"and earns"<<rate*100<<"% interest"<<endl;
   }


   void saveMoney(int y)
   {
    AccBal+=y;
   }
   private:

   int AccNum;
   double AccBal;
   double rate;
   };
   
   class Portfolio
   {
   public:
   Portfolio(int cnum,int chnum,double cbal,int snum,double sbal,double srate,double smhtv,double rehtv)
   {
   clientNum=cnum;
   check.setAccount(chnum,cbal);
   save.setAccount2(snum,sbal,srate);
   SMHTV=smhtv;
   REHTV=rehtv;
   balancePortfolio();
   }

   void displayPortfolio()
   {
   cout<<"Client #"<<clientNum<<endl;
   check.displayAccount();
   save.displayAccount();
   cout<<"Stock market value $"<<SMHTV;
   cout<<"Real estate holdings $"<<REHTV;
   }


   private:
   int clientNum;
   BankAccount check;
   BankAccount save;

   double SMHTV;
   double REHTV;

   void balancePortfolio()
   {
   double total=check.balance()+save.balance()+SMHTV+REHTV;
   if((SMHTV/total)>0.4)
   cout<<"Your portfolio is out of balance -perhaps too much in the stock market"<<endl;
   else if((REHTV/total)>0.4)
   cout<<"Your portfolio is out of balance -perhaps too much in the real estate"<<endl;
   else if((check.balance()/total)>0.4)
   cout<<"Your portfolio is out of balance -perhaps too much in checkings"<<endl;
   else if((save.balance()/total)>0.4)
   cout<<"Your portfolio is out of balance -perhaps too much in savings"<<endl;
   else
   cout<<" ";
   
   }
   
   };



   int main()
   {
   Portfolio portfolioA(
   5555,
   4321, 30000,
   789, 10000, 0.03,
   100000,
   20000);
   portfolioA.displayPortfolio();
   system("pause");
   return 0;
   }
