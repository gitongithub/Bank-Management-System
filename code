#include<process.h>
#include<stdio.h>
#include<stdlib.h>
#include<string.h>
#include<iostream.h>
#include<conio.h>
#include<dos.h>
#include<fstream.h>

class transact
{
 int acc,id;
 char what[25];
 int amot;
 public: void in(int,int,int,char[20]);
		 void out();
		 void readd();
		 int getno();
		 void find();

}t;

 void transact::out()
 {
   cputs("Transaction Id:");
   cout<<id;
   cputs("   Account Number:");
   cout<<acc;
   cputs("  Amount:");
   cout<<amot;
   cputs("    Transaction:");
   cout<<what;
   cout<<endl;

 }

void transact::in(int an,int amt,int tid,char give[20])
 {
   acc=an;
   id=tid;
   amot=amt;
   strcpy(what,give);
 }
 void transact::readd()
 {
  ifstream ifs1;
  ifs1.open("hitoo.DAT",ios::binary);
  ifs1.seekg(0);
  while(ifs1.read((char*)&t,sizeof(t)))
  {
   t.out();
   cout<<endl;
  }
  ifs1.close();
 }
 void transact::find()
 {
  char ch;
  int an,f=0;
  clrscr();
  ifstream ifs1;
  ifs1.open("hitoo.DAT",ios::in|ios::binary);
  cout<<"Enter Account Number:";
  cin>>an;
  ifs1.seekg(0);
  clrscr();
  while(ifs1.read((char*)&t,sizeof(t)))
  {
  if(an==getno())
  {
   t.out();
   f=1;
  }
  }
  if(f==1)
  {
   cout<<"\n\nPress 1 to continue.Thank You";
   cin>>ch;
  }
  if(f==0)
 {
  cout<<"No Transactions.Press 1 to continue";
  cin>>ch;
 }
  ifs1.close();
 }
 int transact::getno()
 {
  return acc;
 }
 class Customer
 {
   int Acc_no;
   char name[25];
   int Age;
   float balance;
   char type[25];
   char status[20];
   char Address[30];
   char phone[11];
	 int pin;
	 public:
	 Customer()
	 {
	strcpy(status,"Active");
	 }
	 void input();
	 void display();
	 int transfer();
	 void receive(float);
	 void exchange(float);
	 void update1();
	 void create();
	 void close();
	 void clos();
	 void disp();
	 void search();
	 int getaccno();
	 int getpin();
	 void change();
	 void modify();
	 void deposit(int);
	 void withdraw(int);
	 void update(int);
	 char* getname();

 }p;

 char* Customer::getname()
 {
	return status;
 }
 void Customer::clos()
 {
	char Ch;
	strcpy(status,"Inactive");
	cout<<"Account Closed.Press 1 to continue";
	cin>>Ch;
 }
 void Customer::input()
 {
	 char ch;
	 cout<<endl<<"Enter Name:";
	 gets(name);
	 do
	 {
	cout<<endl<<"Enter Age:";
	cin>>Age;
	if(Age<18)
	 {
	 cout<<"\nYou are not eligible to create account.";
	 }
	}while(Age<18);
	 cout<<endl<<"Enter Address:";
	 gets(Address);
	 cout<<endl<<"Enter Phone Number:";
	 gets(phone);

	 cout<<"\nEnter Account Type\n1.Savings Account\n2.Current Account\n";
	 cin>>ch;
	 switch(ch)
	 {
	case '1':balance=1500;
			 strcpy(type,"Savings");
			 Acc_no=1000+random(9000);;
			 cout<<"\nYour Account Number is:"<<Acc_no;
			 break;
	case '2':balance=0;
			 strcpy(type,"Current");
			 Acc_no=1000+random(9000);
			 cout<<"\nYour Account Number is:"<<Acc_no;
			 break;
	default : cout<<"Wrong Choice";
	 }
	 cout<<endl<<"Your 4 digit ATM PIN:";
	 pin=random(9000)+1000;
	 cout<<pin;

}
 void Customer::change()
 {
	 cout<<endl<<"Enter New Name:";
	 gets(name);

	 do
	 {
	 cout<<endl<<"Enter New Age:";
	 cin>>Age;
	 if(Age<18)
	 {
	 cout<<"\nYou are not eligible to create account.";
	 }
	}while(Age<18);
	cout<<endl<<"Enter New Address:";
	 gets(Address);
	 cout<<endl<<"Enter New Phone Number:";
	 gets(phone);
	 cout<<endl<<"Enter Desired 4 digit ATM PIN:";
	 cin>>pin;

 }
 void Customer::display()
 {
	 if(strcmp(status,"Inactive")==0)
		textcolor(RED);
	 else
		textcolor(GREEN);
	 cputs("Acc_no:");
	 cout<<Acc_no;
	 cputs("  Name:");
	 cout<<name;
	 cputs("  Age:");
	 cout<<Age;
	 cputs("  Address:");
	 cout<<Address;
	 cputs("  Phone Number:");
	 cout<<phone;
	 cout<<endl;
	 cputs("  ATM PIN:");
	 cout<<pin;
	 cputs("  Balance:");
	 cout<<balance;
	 cputs("  Type:");
	 cout<<type;
	 cputs("   Status:");
	 cout<<status;
	 cout<<endl;

 }
 void Customer::deposit(int an)
 {
	float amt;
	int tid;
	char ch;
	ofstream ofs1;
	ofs1.open("hitoo.DAT",ios::app|ios::binary);
	cout<<"\nEnter the amount to be deposited:";
	cin>>amt;
	balance+=amt;
	tid=random(32600);
	t.in(an,amt,tid,"Deposit");
	ofs1.write((char*)&t,sizeof(t));
	ofs1.close();
	cout<<"\nTransaction Number "<<tid<<" Initiated.Press 1 to continue.";
	cin>>ch;
 }
 void Customer::receive(float amt)
 {
	char ch;
	balance+=amt;
	 }
 void Customer::withdraw(int an)
 {
	float amt;
	char ch;
	int c=0,tid;
	ofstream ofs1;
	ofs1.open("hitoo.DAT",ios::app|ios::binary);
	do
	{
	 cout<<"\nEnter the amount to be withdrawn:";
	 cin>>amt;
	 if(balance-1500>=amt)
	 {
	balance=balance-amt;
	c=1;
	tid=random(32600);
	t.in(an,amt,tid,"Withdraw");
	ofs1.write((char*)&t,sizeof(t));
	 ofs1.close();
	cout<<"\nTransaction Id "<<tid<<" Initiated";
	cout<<"\nPress 1 to continue";
	cin>>ch;
	break;
	 }
	 else

	{
	cout<<"\nYour balance is:"<<balance<<"\nSo you can't withdraw:"<<amt;
	cout<<"\nPlease Try again.";
	cin>>ch;
	}
	 }while(c!=1);
}
int Customer::transfer()
 {
	float amt;
	char ch;
	int c=0;
	do
	{
	 cout<<"\nEnter the amount to be transfered:";
	 cin>>amt;
	 if(balance-1500>=amt)
	 {
	balance=balance-amt;
	c=1;

	break;
	 }
	 else

	{
	cout<<"\nYour balance is:"<<balance<<"\nSo you can't transfer:"<<amt;
	cout<<"\nPlease Try again.";

	}
	 }while(c!=1);
	 return amt;
}
 void Customer::create()
 {
	 ofstream ofs;
	 char ch;
	 ofs.open("hilloo.DAT",ios::app|ios::binary);
	 p.input();
	 ofs.write((char*)&p,sizeof(p));
	 ofs.close();
	 cout<<"\nAccount created.Press 1 to continue";
	cin>>ch;
 }

 void Customer::disp()
 {
	ifstream ifs;
	ifs.open("hilloo.DAT",ios::binary);
	ifs.seekg(0);
	while(ifs.read((char*)&p,sizeof(p)))
	{
	 p.display();
	 cout<<endl;
	}
	ifs.close();
 }
 void Customer :: close()
 {
	int an;
	clrscr();
	fstream fs;
	fs.open("hilloo.DAT",ios::in|ios::out|ios::binary);
	cout<<"Enter Account Number to be closed!!:";
	cin>>an;
	fs.seekg(0);
	while(fs)
	{
	 int pos=fs.tellg();
	fs.read((char*)&p,sizeof(p));
	if(an==getaccno())
	{
	 p.clos();
	 fs.seekp(pos,ios::beg);
	 fs.write((char*)&p,sizeof(p));
	 break;
	}
	}
	fs.close();
	}

	void Customer :: search()
 {
	char ch;
	int an,f=0;
	clrscr();
	ifstream ifs;
	ifs.open("hilloo.DAT",ios::in|ios::binary);
	cout<<"Enter Account Number:";
	cin>>an;
	ifs.seekg(0);
	while(ifs)
	{
	ifs.read((char*)&p,sizeof(p));
	if(an==getaccno())
	{
	 clrscr();
	 cout<<"Account Details are:\n\n";
	 p.display();
	 f=1;
	 cout<<"\nThank You.Press 1 to continue";
	 cin>>ch;
	 break;
	}
	}
	if(f==0)
 {
	cout<<"\nSearch Unsuccessful.Press 1 to continue.";
	cin>>ch;
 }
	ifs.close();
 }
void Customer::modify()
	{

	fstream file;
	file.open("hilloo.DAT",ios::in|ios::out|ios::binary);
	int r,f=0;
	char ch;
	cout<<"\n Enter Account number:";
	cin>>r;
	file.seekg(0);
	while(file)
	{
	int pos=file.tellg();
	file.read((char*)&p,sizeof(p));
	if(r==p.getaccno())
	{
	 f=1;
	cout<<"\n Account Details are:\n";
	p.display();
	cout<<"\n Enter New Record\n";
	p.change();
	file.seekp(pos,ios::beg);
	file.write((char*)&p,sizeof(p));
	cout<<"\n Record modified succesfully.Press 1 to continue";
	cin>>ch;
	break;
	}
	}
	if(f==0)
	{
	 cout<<"Search Unsuccessful.Please try agin.Press 1 to continue";
	 cin>>ch;
	}
	file.close();
}
void Customer::exchange(float amt)
{
	char ch;
	int an,f=0;
	clrscr();
	fstream file;
	file.open("hilloo.DAT",ios::in|ios::out|ios::binary);
	cout<<"Enter Account Number who you want to send:";
	cin>>an;
	file.seekg(0);
	while(file)
	{
	 int pos=file.tellg();
	file.read((char*)&p,sizeof(p));
	if(an==getaccno())
	{
	 p.receive(amt);
	 file.seekp(pos,ios::beg);
	 file.write((char*)&p,sizeof(p));
	 f=1;
	 break;
	}
	}
	if(f==0)
	{
	cout<<"\nSearch Unsuccessful.Press 1 to continue";
	cin>>ch;
	}
	file.close();
 }
void Customer::update(int n)
{
	char ch;
	int an,pin1,f=0;
	clrscr();
	fstream file;
	file.open("hilloo.DAT",ios::in|ios::out|ios::binary);
	cout<<"Enter Account Number:";
	cin>>an;
	cout<<"\nEnter ATM PIN:";
	cin>>pin1;
	file.seekg(0);
	while(file)
	{
	 int pos=file.tellg();
	file.read((char*)&p,sizeof(p));
	if(an==getaccno())
	{
	 if(pin1!=getpin())

		{
		 f=0;
		 break;

		}
	 if(strcmp(getname(),"Inactive")==0)
	 {
	 cout<<"\nYour account is inactive.Press 1 to continue";
	 cin>>ch;
	 f=0;
	 break;
	}
	}

	 if(f==1)
	 {

	 if(n!=1)
	 p.withdraw(an);
	 else
	 p.deposit(an);
	 file.seekp(pos,ios::beg);
	 file.write((char*)&p,sizeof(p));
	 break;

	}
	 }
	if(f==0)
	{
	cout<<"\nSearch Unsuccessful.Press 1 to continue";
	cin>>ch;
	}
	file.close();
 }
 void Customer::update1()
{
	char ch;
	float d;
	int an,f=0;
	clrscr();
	int tid;
	ofstream ofs1;
	ofs1.open("hitoo.DAT",ios::app|ios::binary);
	fstream file;
	file.open("hilloo.DAT",ios::in|ios::out|ios::binary);
	cout<<"Enter Account Number:";
	cin>>an;
	file.seekg(0);
	while(file)
	{
	 int pos=file.tellg();
	file.read((char*)&p,sizeof(p));
	if(an==getaccno())
	{
	d=p.transfer();
	 file.seekp(pos,ios::beg);
	 file.write((char*)&p,sizeof(p));
	 f=1;

	 break;
	}
	}
	if(f==1)
	{
	 p.exchange(d);
	 tid=random(32600);
	 t.in(an,d,tid,"Transfer");
	 ofs1.write((char*)&t,sizeof(t));
	 ofs1.close();
	 cout<<"\nTransaction Id "<<tid<<" Initiated";
	 cout<<"Press 1 to continue";
	 cin>>ch;
	}
  if(f==0)
  {
  cout<<"\nSearch Unsuccessful.Press 1 to continue";
  cin>>ch;
  }

  file.close();
 }

int Customer::getpin()
{
  return pin;
}
int Customer::getaccno()
{
 return Acc_no;
}
 void staff();
 void page();
 void security();

 void main()
 {
	 char ch1 ;
	clrscr();
	 char ch,k,l,che;
	 randomize();
	 page();
	 security();
	 do
	 {
	 clrscr();
	 int x;
	for(x=2;x<80;x++)
	{
		gotoxy(x,1);
		if(x%2==0)
			cout<<"#";
		else	cout<<" ";
		delay(5);
	}
	for(x=2;x<25;x++)
	{
		gotoxy(1,x);
		cout<<"#";
		delay(5);
	}
	for(x=2;x<80;x++)
	{
		gotoxy(x,25);
		if(x%2==0)
			cout<<"#";
		else    cout<<" ";
		delay(5);
	}
	for(x=2;x<25;x++)
	{
		gotoxy(80,x);
		cout<<"#";
		delay(5);
	}
	delay(500);
	 gotoxy(35,5);cout<<"======================\n";
	 gotoxy(35,6);cout<<"BANK MANAGEMENT SYSTEM";
	 gotoxy(35,7);cout<<"======================\n";
	 gotoxy(35,8);cout<<"    ::MAIN MENU::\n";
	 gotoxy(35,11);cout<<"1. DEPOSIT AMOUNT";
	 gotoxy(35,12);cout<<"2. WITHDRAW AMOUNT";
	 gotoxy(35,13);cout<<"3. BALANCE ENQUIRY";
	 gotoxy(35,14);cout<<"4. VIEW TRANSACTION";
	 gotoxy(35,15);cout<<"5. TRANFER MONEY";
	 gotoxy(35,16);cout<<"6. EXIT";
	 gotoxy(35,18);cout<<"Select Your Option (1-6): ";
	 cin>>ch;
	 clrscr();
	 switch(ch)
	 {

		 case '1':cout<<"You have selected DEPOSIT AMOUNT";
				 cout<<endl<<"To Continue Press any key\nTo go back to main menu Press 0\n";
				 cin>>ch1;
				 clrscr();
				 if(ch1!='0')
					p.update(1);
				 else
					continue;
			break;
		 case '2':cout<<"You have selected WITHDRAW AMOUNT";
				 cout<<endl<<"To Continue Press any key\nTo go back to main menu Press 0\n";
				cin>>ch1;
				clrscr();
				if(ch1!='0')
					p.update(2);
				 else
					continue;
			break;
		 case '3':cout<<"You have selected BALANCE ENQUIRY";
				 cout<<endl<<"To Continue Press any key\nTo go back to main menu Press 0\n";
				 cin>>ch1;
				 clrscr();
				 if(ch1!='0')
					 p.search();
				else
					continue;
				break;
		 case '4':cout<<"You have selected VIEW TRANSACTIONS";
				 cout<<endl<<"To Continue Press any key\nTo go back to main menu Press 0\n";
				 cin>>ch1;
				 clrscr();
				 if(ch1!='0')
					 t.find();
				else
					continue;
				break;
		 case '5':cout<<"You have selected TRANSFER MONEY";
				 cout<<endl<<"To Continue Press any key\nTo go back to main menu Press 0\n";
				 cin>>ch1;
				 clrscr();
				 if(ch1!='0')
					p.update1();
				 else
					continue;
			break;
		case '6':cout<<"You have selected TO EXIT";
				 cout<<endl<<"To Continue Press any key\nTo go back to main menu Press 0\n";
				 cin>>ch1;
				 if(ch1!='0')
				 {
				 for(int k=3;k>0;k--)
				 {
				 clrscr();
				 cout<<"Exiting in "<<k;
				 delay(800);
				 }
				 exit(0);
				 }

			break;
		 default :cout<<"\n\n\t\t\tBrought To You By ";
		 }
 }while(ch!=6);
getch();
}

void security()
{
char s[6];
int k,ch,j=0;
clrscr();


	for(int i=1;i<=10;i++)
	{
		clrscr();
		cout<<"\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\tLOADING!!\n\t\t\t\t";
		for(j=i;j>0;j--)
			cout<<"\DB\DB";
		cout<<i<<"0%";
		delay(500);
	}

	cout<<"\n\t\t\t\tCOMPLETE ";
	delay(200);
	cout<<"!";
	delay(200);
	cout<<"!";
	delay(300);
textcolor(GREEN);
clrscr();
cputs("For Staff Login:(1)");
cout<<endl;
cputs("For User Login :(2)");
cout<<endl;
cin>>ch;

do
{
if(ch==1)
{
cputs("Enter ");
delay(500);
cputs("Staff ");
delay(500);
cputs("Password:");
}
else if(ch==2)
{
cputs("Enter ");
delay(500);
cputs("User ");
delay(500);
cputs("Password:");
}
textcolor(WHITE);
for(k=0;k<=5;k++)
{
s[k]=getch();
cputs("*");
}
s[k]=NULL;
cout<<endl;
delay(1000);
char op[]="Matching Password";
for(k=0;k<strlen(op);k++)
{
textcolor(WHITE);
cout<<op[k];
delay(100);
}
delay(1000);
clrscr();
textcolor(YELLOW);
if(strcmp("istaff",s)==0||strcmp("meuser",s)==0)
{
 cputs("Password ");
 delay(500);
 cputs("Matched");
 delay(1000);
 if(ch==1)
	staff();
 else
	break;

}
else
{
 cputs("Password ");
 delay(500);
 cputs("Incorrect");
 delay(1000);
 clrscr();
 if(j==0)
 {
 j++;
 continue;
 }
 for(k=5;k>=0;k--)
 {
 clrscr();
 cout<<"Exiting in "<<k;
 delay(1000);
 }
 exit(0);
}
}while(j<2);
}
void page()
{
char ch;
textcolor(RED);
cputs("# # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # #");
cout<<endl;
cputs("#   @                 @                                                       #");
cout<<endl;
cputs("#    @               @                                                        #");
cout<<endl;
cputs("#     @             @  @ @ @   @       @ @ @ @   @ @ @ @   @       @  @ @ @   #");
cout<<endl;
cputs("#      @     @     @   @       @       @         @     @   @ @   @ @  @       #");
cout<<endl;
cputs("#       @   @ @   @    @ @     @       @         @     @   @  @ @  @  @ @ @   #");
cout<<endl;
cputs("#        @ @   @ @     @       @       @         @     @   @   @   @  @       #");
cout<<endl;
cputs("#         @     @      @ @ @   @ @ @   @ @ @ @   @ @ @ @   @       @  @ @ @   #");
cout<<endl;
textcolor(GREEN);
cputs("#                                                                             #");
cout<<endl;
cputs("#                                                                             #");
cout<<endl;
cputs("#                             @ @ @ @ @ @  @ @ @ @                            #");
cout<<endl;
cputs("#                                  @       @     @                            #");
cout<<endl;
cputs("#                                  @       @     @                            #");
cout<<endl;
cputs("#                                  @       @     @                            #");
cout<<endl;
cputs("#                                  @       @ @ @ @                            #");
cout<<endl;
cputs("#                                                                             #");
cout<<endl;
cputs("#                                                                             #");
cout<<endl;
textcolor(MAGENTA);
cputs("#                  @ @ @ @         @       @     @    @     @                 #");
cout<<endl;
cputs("#                  @       @      @ @      @ @   @    @   @                   #");
cout<<endl;
cputs("#                  @ @ @ @       @   @     @  @  @    @ @                     #");
cout<<endl;
cputs("#                  @       @    @ @ @ @    @   @ @    @   @                   #");
cout<<endl;
cputs("#                  @ @ @ @     #       @   @     @    @     @                 #");
cout<<endl;
cputs("#                                                                             #");
cout<<endl;
cputs("# # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # #");
cin>>ch;
}
void staff()
{
 char ch,ch1,che,chf;
 int k;
do
	 {
	 clrscr();
	 textcolor(YELLOW);
	 int x;
	for(x=2;x<80;x++)
	{
		gotoxy(x,1);
		if(x%2==0)
			cputs("#");
		else	cout<<" ";
		delay(5);
	}
	for(x=2;x<25;x++)
	{
		gotoxy(1,x);
		cputs("#");
		delay(5);
	}
	for(x=2;x<80;x++)
	{
		gotoxy(x,25);
		if(x%2==0)
			cputs("#");
		else    cout<<" ";
		delay(5);
	}
	for(x=2;x<25;x++)
	{
		gotoxy(80,x);
		cputs("#");
		delay(5);
	}
	delay(500);
	 gotoxy(35,5);cout<<"======================\n";
	 gotoxy(35,6);cout<<"BANK MANAGEMENT SYSTEM";
	 gotoxy(35,7);cout<<"======================\n";
	 gotoxy(35,8);cout<<"::MAIN MENU::\n";
	 gotoxy(35,10);cout<<"1. NEW ACCOUNT";
	 gotoxy(35,11);cout<<"2. ALL ACCOUNT HOLDER LIST";
	 gotoxy(35,13);cout<<"4. ALL TRANSACTIONS";
	 gotoxy(35,12);cout<<"3. MODIFY ACCOUNT";
	 gotoxy(35,14);cout<<"5. SEARCH ACCOUNT";
	 gotoxy(35,15);cout<<"6. CLOSE ACCOUNT";
	 gotoxy(35,16);cout<<"7. EXIT";
	 gotoxy(35,18);cout<<"Select Your Option (1-7): ";
	 cin>>ch;
	 clrscr();
	 switch(ch)
	 {
		 case '1':cout<<"You have selected NEW ACCOUNT";
				cout<<endl<<"To Continue Press any key\nTo go back to main menu Press 0\n";
				cin>>ch1;
				clrscr();
				if(ch1!='0')
					p.create();
				else
					continue;
				break;
		 case '2':cout<<"You have selected ALL ACCOUNT HOLDER LIST";
				cout<<endl<<"To Continue Press any key\nTo go back to main menu Press 0";
				cin>>ch1;
				if(ch1!='0')
					{
					p.disp();
					cout<<"\nPress any key to continue:";
					cin>>che;
					}
				else
					continue;
				break;
		 case '3':cout<<"You have selected MODIFY ACCOUNT";
				 cout<<endl<<"To Continue Press any key\nTo go back to main menu Press 0\n";
				 cin>>ch1;
				 clrscr();
				 if(ch1!='0')
					 p.modify();
				 else
					 continue;

				 break;
		 case '4':cout<<"You have selected ALL TRANSACTIONS";
				 cout<<endl<<"To Continue Press any key\nTo go back to main menu Press 0\n";
				 cin>>ch1;
				 clrscr();
				 if(ch1!='0')
					{
					t.readd();
					cout<<"\nThank You.";
					cin>>chf;
					}
				 else
					continue;
			break;
		 case '5':cout<<"You have selected SEARCH ACCOUNT";
				 cout<<endl<<"To Continue Press any key\nTo go back to main menu Press 0\n";
				 cin>>ch1;
				 clrscr();
				 if(ch1!='0')
					 p.search();
				else
					continue;
				break;
		 case '6':cout<<"You have selected CLOSE ACCOUNT";
				 cout<<endl<<"To Continue Press any key\nTo go back to main menu Press 0\n";
				 cin>>ch1;
				 clrscr();
				 if(ch1!='0')
					{
					p.close();

					}
				 else
					continue;
			break;
		 case '7':cout<<"You have selected TO EXIT";
				 cout<<endl<<"To Continue Press any key\nTo go back to main menu Press 0";
				 cin>>ch1;
				 if(ch1!='0')
				 {
				 for(int k=3;k>0;k--)
				 {
				 clrscr();
				 cout<<"Exiting in "<<k;
				 }
				 exit(0);
				 }
			break;

		 default :cout<<"\n\n\t\t\tBrought To You By ";
		 }
 }while(1);


}
