# Hotel-Management-System
#include<iostream>
#include<fstream>
#include <sstream>
using namespace std;
struct Student{
	string Name;
	int RollNo,Id;
};
struct BreakFast{
	string DishName,StdName[3];
};
struct Dinner{
	string DName,SName[3];
};
class Management{
	public:
		void SetSalariesAndHostelProfit(){
			int Salary;
			Salary=2500+(15000*5)+15000+(10000*4)+5000;
			string Profit1,Profit2,Profit3,Profit4;
			ifstream File;
			File.open("Clothes1.txt",ios::in);
			for (int i=0; i<3;i++){
        		getline(File,Profit1);
    		}
    		File.close();
    		File.open("Clothes2.txt",ios::in);
			for (int i=0; i<3;i++){
        		getline(File,Profit2);
    		}
    			File.close();
    		File.open("Clothes3.txt",ios::in);
			for (int i=0; i<3;i++){
        		getline(File,Profit3);
    		}
    			File.close();
    		File.open("Clothes4.txt",ios::in);
			for (int i=0; i<3;i++){
        		getline(File,Profit4);
    		}
    			File.close();
    		int Salaries=Salary*4;
    		fstream MFile;
    		MFile.open("Salaries&HostelProfit.txt",ios::out);
    		if(File){
    		MFile<<"Total Salary of 4 Hostels are: "<<Salaries<<endl;
    		MFile<<Profit1<<endl;
    		MFile<<Profit2<<endl;
    		MFile<<Profit3<<endl;
    		MFile<<Profit4<<endl;
    		MFile.close();
			}else{
				cout<<"Salaries&HostelProfit is not created!!!"<<endl;
			}
		}
		void ShowTotalDues(){
			int MessBill,MessGuestBill,LostFoundFine,TotalBill;
			string IDCardNo;
			cout<<"Enter Student ID Card Number: ";
			cin>>IDCardNo;
			cout<<"Enter Mess Bill: ";
			cin>>MessBill;
			cout<<"Enter Guest Mess Bill: ";
			cin>>MessGuestBill;
			fstream File;
			File.open("LFitem1 Hostel 1.txt",ios::in);
			string str,value;
			while(1){
				getline(File,str);
					if(IDCardNo==str){
						getline(File,value);
						break;
					}
					if(File.eof()){
						break;
					}
			}
			File.close();
			fstream File2;
			File2.open("LFitem2 Hostel 2.txt",ios::in);
			while(1){
				getline(File2,str);
					if(IDCardNo==str){
						getline(File2,value);
						break;
					}
					if(File2.eof()){
						break;
					}
			}
			File2.close();
			fstream File3;
			File3.open("LFitem3 Hostel 3.txt",ios::in);
			while(1){
				getline(File3,str);
					if(IDCardNo==str){
						getline(File3,value);
						break;
					}
					if(File3.eof()){
						break;
					}
			}
			File3.close();
			fstream File4;
			File4.open("LFitem4 Girls Hostel.txt",ios::in);
			while(1){
				getline(File4,str);
					if(IDCardNo==str){
						getline(File4,value);
						break;
					}
					if(File4.eof()){
						break;
					}
			}
			File4.close();
			stringstream ss;  
  			ss << value;  
  			ss >> LostFoundFine; 
			TotalBill=LostFoundFine+MessBill+MessGuestBill;
			cout<<"Total Bill is: "<<TotalBill;
			File.close();
		}
};
class Hostel1:public Management{
	public:
		Student S;
	void SetStudent(){
		cout<<"==========Information of Hostel 1============="<<endl;
		int Size;
		cout<<"Enter number of students you want to store.";
		cout<<"Size must be greater than or equal to 200."<<endl;
	a:	cin>>Size;
		if(Size>=3){
			fstream File;
			File.open("Hostel1.txt",ios::app);
			if(File){
				File<<"************Student Details************"<<endl;
				File<<"ID\tRollNo\t\tName"<<endl;	
				for(int i=0;i<Size;i++){
					cout<<"Enter Name: ";
					cin>>S.Name;
					cout<<"Enter Roll Number: ";
					cin>>S.RollNo;
					cout<<"Enter ID: ";
					cin>>S.Id;
					File<<S.Id<<"\t"<<S.RollNo<<"\t\t"<<S.Name<<endl;
				}
				File.close();
			}else{
				cout<<"Hostel 1 File not created!"<<endl;
			}
		}else{
			cout<<"Enter again Number of students";
			cout<<" because number of students must be greater than 200: ";
			goto a;
		}
	}
};
class Hostel2:public Management{
	public:
		Student S;
	void SetStudent(){
		int Size;
		cout<<"==========Information of Hostel 2============="<<endl;
		cout<<"Enter number of students you want to store.";
		cout<<"Size must be greater than or equal to 200: ";
	b:	cin>>Size;
		if(Size>=3){
			fstream File;
			File.open("Hostel2.txt",ios::app);
			if(File){
				File<<"************Student Details************"<<endl;
				File<<"ID\tRollNo\t\tName"<<endl;	
				for(int i=0;i<Size;i++){
					cout<<"Enter Name: ";
					cin>>S.Name;
					cout<<"Enter Roll Number: ";
					cin>>S.RollNo;
					cout<<"Enter ID: ";
					cin>>S.Id;
					File<<S.Id<<"\t"<<S.RollNo<<"\t\t"<<S.Name<<endl;
				}
				File.close();
			}else{
				cout<<"Hostel 2 File not created!"<<endl;
			}
		}else{
			cout<<"Enter again Number of students: ";
			cout<<" because number of students must be greater than or equal 3: ";
			goto b;
		}
	}
};
class Hostel3:public Management{
	public:
		Student S;
	void SetStudent(){
		int Size;
		cout<<"==========Information of Hostel 3============="<<endl;
		cout<<"Enter number of students you want to store.";
		cout<<"Size must be greater than or equal to 200: "<<endl;
	c:	cin>>Size;
		if(Size>=3){
			fstream File;
			File.open("Hostel3.txt",ios::app);
			if(File){
				File<<"************Student Details************"<<endl;
				File<<"ID\tRollNo\t\tName"<<endl;	
				for(int i=0;i<Size;i++){
					cout<<"Enter Name: ";
					cin>>S.Name;
					cout<<"Enter Roll Number: ";
					cin>>S.RollNo;
					cout<<"Enter ID: ";
					cin>>S.Id;
					File<<S.Id<<"\t"<<S.RollNo<<"\t\t"<<S.Name<<endl;
				}
				File.close();
			}else{
				cout<<"Hostel 3 File not created!"<<endl;
			}
		}else{
			cout<<"Enter again Number of students";
			cout<<" because number of students must be greater than 200: ";
			goto c;
		}
	}
};
class GirlsHostel:public Management{
	public:
	Student S;
	void SetStudent(){
		int Size;
		cout<<"==========Information of Girls Hostel============="<<endl;
		cout<<"Enter number of students you want to store."<<endl;
		cout<<"Size must be greater than or equal to 3: "<<endl;
	d:	cin>>Size;
		if(Size>=3){
			fstream File;
			File.open("GirlsHostel.txt",ios::app);
			if(File){
				File<<"************Student Details************"<<endl;
				File<<"ID\tRollNo\t\tName"<<endl;	
				for(int i=0;i<Size;i++){
					cout<<"Enter Name: ";
					cin>>S.Name;
					cout<<"Enter Roll Number: ";
					cin>>S.RollNo;
					cout<<"Enter ID: ";
					cin>>S.Id;
					File<<S.Id<<"\t"<<S.RollNo<<"\t\t"<<S.Name<<endl;
				}
				File.close();
			}else{
				cout<<"Girls Hostel File not created!"<<endl;
			}
		}else{
			cout<<"Enter again Number of students";
			cout<<" because number of students must be greater than 200: ";
			goto d;
		}
	}
};
class Mess1:public Hostel1{
	public:
		BreakFast B;
		Dinner d;
	void SetMess(){
		fstream File;
		File.open("Mess1.txt",ios::app);
		cout<<"==========Information of Mess 1============="<<endl;
		cout<<"**********Breakfast Information**********"<<endl;
		File<<"**********Breakfast Information**********"<<endl;
		File<<"Dish Name \tStudent Name\t\t";
		if(File){
			cout<<"Enter Dish Name: ";
			cin>>B.DishName;
			File<<endl;
			File<<B.DishName<<"\t\t";
			for(int i=0;i<3;i++){
				cout<<"Enter Student Name who eats breakfast "<<i+1<<": ";

				File<<"\t\t"<<B.StdName[i]<<"\t\t\t\t\t"<<endl;
			}
			cout<<endl;
			File<<endl;
			cout<<"**********Dinner Information**********"<<endl;
			File<<"**********Dinner Information**********"<<endl;
			File<<"Dish Name \tStudent Name\t\t"<<endl;
			cout<<"Enter Dish Name: ";
			cin>>d.DName;
			File<<d.DName<<"\t\t";
			for(int i=0;i<3;i++){
				cout<<"Enter Student Name who eats dinner "<<i+1<<": ";
				cin>>d.SName[i];
				File<<"\t\t"<<d.SName[i]<<"\t\t\t"<<endl;
			}
			File.close();
		}else{
			cout<<"Mess 1 File not Created!!!"<<endl;
		}
	}
};
class Mess2:public Hostel2{
	public:
		BreakFast B;
		Dinner d;
		void SetMess(){
			fstream File;
			File.open("Mess2.txt",ios::app);
			cout<<"==========Information of Mess 2============="<<endl;
			cout<<"**********Breakfast Information**********"<<endl;
			File<<"**********Breakfast Information**********"<<endl;
			File<<"Dish Name \tStudent Name\t\t";
			if(File){
				cout<<"Enter Dish Name: ";
				cin>>B.DishName;
				File<<endl;
				File<<B.DishName<<"\t\t";
				for(int i=0;i<3;i++){
					cout<<"Enter Student Name who eats breakfast "<<i+1<<": ";
					cin>>B.StdName[i];
					File<<"\t\t"<<B.StdName[i]<<"\t\t\t\t\t"<<endl;
				}
				cout<<endl;
				File<<endl;
				cout<<"**********Dinner Information**********"<<endl;
				File<<"**********Dinner Information**********"<<endl;
				File<<"Dish Name \tStudent Name\t\t"<<endl;
				cout<<"Enter Dish Name: ";
				cin>>d.DName;
				File<<d.DName<<"\t\t";
				for(int i=0;i<3;i++){
					cout<<"Enter Student Name who eats dinner "<<i+1<<": ";
					cin>>d.SName[i];
					File<<"\t\t"<<d.SName[i]<<"\t\t\t"<<endl;
				}
				File.close();
			}else{
				cout<<"Mess 2 File not Created!!!"<<endl;
			}
	}
};
class Mess3:public Hostel3{
	public:
		BreakFast B;
		Dinner d;
		void SetMess(){
		fstream File;
		File.open("Mess3.txt",ios::app);
		cout<<"==========Information of Mess 3============="<<endl;
		cout<<"**********Breakfast Information**********"<<endl;
		File<<"**********Breakfast Information**********"<<endl;
		File<<"Dish Name \tStudent Name\t\t";
		if(File){
			cout<<"Enter Dish Name: ";
			cin>>B.DishName;
			File<<endl;
			File<<B.DishName<<"\t\t";
			for(int i=0;i<3;i++){
				cout<<"Enter Student Name who eats breakfast "<<i+1<<": ";
				cin>>B.StdName[i];
				File<<"\t\t"<<B.StdName[i]<<"\t\t\t\t\t"<<endl;
			}
			cout<<endl;
			File<<endl;
			cout<<"**********Dinner Information**********"<<endl;
			File<<"**********Dinner Information**********"<<endl;
			File<<"Dish Name \tStudent Name\t\t"<<endl;
			cout<<"Enter Dish Name: ";
			cin>>d.DName;
			File<<d.DName<<"\t\t";
			for(int i=0;i<3;i++){
				cout<<"Enter Student Name who eats dinner "<<i+1<<": ";
				cin>>d.SName[i];
				File<<"\t\t"<<d.SName[i]<<"\t\t\t"<<endl;
			}
			File.close();
		}else{
			cout<<"Mess 3 File not Created!!!"<<endl;
		}
	}
};
class Mess4:public GirlsHostel{
	public:
		BreakFast B;
		Dinner d;
		void SetMess(){
		fstream File;
		File.open("Mess4.txt",ios::app);
		cout<<"==========Information of Mess 4============="<<endl;
		cout<<"**********Breakfast Information**********"<<endl;
		File<<"**********Breakfast Information**********"<<endl;
		File<<"Dish Name \tStudent Name\t\t";
		if(File){
			cout<<"Enter Dish Name: ";
			cin>>B.DishName;
			File<<endl;
			File<<B.DishName<<"\t\t";
			for(int i=0;i<3;i++){
				cout<<"Enter Student Name who eats breakfast "<<i+1<<": ";
				cin>>B.StdName[i];
				File<<"\t\t"<<B.StdName[i]<<"\t\t\t\t\t"<<endl;
			}
			cout<<endl;
			File<<endl;
			cout<<"**********Dinner Information**********"<<endl;
			File<<"**********Dinner Information**********"<<endl;
			File<<"Dish Name \tStudent Name\t\t"<<endl;
			cout<<"Enter Dish Name: ";
			cin>>d.DName;
			File<<d.DName<<"\t\t";
			for(int i=0;i<3;i++){
				cout<<"Enter Student Name who eats dinner "<<i+1<<": ";
				cin>>d.SName[i];
				File<<"\t\t"<<d.SName[i]<<"\t\t\t"<<endl;
			}
			File.close();
		}
		cout<<"Mess 4 File not Created!!!"<<endl;
	}
};
class Guest1:public Hostel1{
	public:
		string Name[5];
		int SID[5];
		int Bill[5];
		int GuestTotal(int Id){
			int n=0;
			for(int i=0;i<5;i++){
				if(Id==SID[i]){
					n++;
				}
			}
			return n;	
		}
		void SetGuest(){
			fstream File;
			File.open("Guest1.txt",ios::app);
			if(File){
				cout<<"==========Information of Guest 1 Hostel 1============="<<endl;
				File<<"**********Guests Information**********"<<endl;
				File<<"Student ID \tGuest Name\t\tBill"<<endl;
				for(int i=0;i<5;i++){
					cout<<"Enter Guest Name: ";
					cin>>Name[i];
					cout<<"Enter Student ID: ";
					cin>>SID[i];
					cout<<"Enter Total Bill: ";
					cin>>Bill[i];
					int TotalNumber=GuestTotal(SID[i]);
					if(TotalNumber>3){
						cout<<"Student already have 3 guests."<<endl;
					}
					else{
						File<<SID[i]<<"\t\t"<<Name[i]<<"\t\t\t"<<Bill[i]<<endl;
					}
				}
				File.close();
			}
			else{
				cout<<"Guest 1 File is not Created!"<<endl;
			}	
		}
};
class Guest2:public Hostel2{
	public:
		string Name[5];
		int SID[5];
		int Bill[5];
		int GuestTotal(int Id){
			int n=0;
			for(int i=0;i<5;i++){
				if(Id==SID[i]){
					n++;
				}
			}
			return n;	
		}
		void SetGuest(){
			fstream File;
			File.open("Guest2.txt",ios::app);
			if(File){
			cout<<"==========Information of Guest 2 Hostel 2============="<<endl;
				File<<"**********Guests Information**********"<<endl;
				File<<"Student ID \tGuest Name\t\tBill"<<endl;
				for(int i=0;i<5;i++){
					cout<<"Enter Guest Name: ";
					cin>>Name[i];
					cout<<"Enter Student ID: ";
					cin>>SID[i];
					cout<<"Enter Total Bill: ";
					cin>>Bill[i];
					int TotalNumber=GuestTotal(SID[i]);
					if(TotalNumber>3){
						cout<<"Student already have 3 guests."<<endl;
					}
					else{
						File<<SID[i]<<"\t\t"<<Name[i]<<"\t\t\t"<<Bill[i]<<endl;
					}
				}
				File.close();
			}
			else{
				cout<<"Guest 2 File is not Created!"<<endl;
			}	
		}
};
class Guest3:public Hostel3{
	public:
		string Name[5];
		int SID[5];
		int Bill[5];
		int GuestTotal(int Id){
			int n=0;
			for(int i=0;i<5;i++){
				if(Id==SID[i]){
					n++;
				}
			}
			return n;	
		}
		void SetGuest(){
			fstream File;
			File.open("Guest3.txt",ios::app);
			if(File){
				cout<<"==========Information of Guest 3 Hostel 3============="<<endl;
				File<<"**********Guests Information**********"<<endl;
				File<<"Student ID \tGuest Name\t\tBill"<<endl;
				for(int i=0;i<5;i++){
					cout<<"Enter Guest Name: ";
					cin>>Name[i];
					cout<<"Enter Student ID: ";
					cin>>SID[i];
					cout<<"Enter Total Bill: ";
					cin>>Bill[i];
					int TotalNumber=GuestTotal(SID[i]);
					if(TotalNumber>3){
						cout<<"Student already have 3 guests."<<endl;
					}
					else{
						File<<SID[i]<<"\t\t"<<Name[i]<<"\t\t\t"<<Bill[i]<<endl;
					}
				}
				File.close();
			}
			else{
				cout<<"Guest 3 File is not Created!"<<endl;
			}	
		}
};
class Guest4:public GirlsHostel{
	public:
		string Name[5];
		int SID[5];
		int Bill[5];
		int GuestTotal(int Id){
			int n=0;
			for(int i=0;i<5;i++){
				if(Id==SID[i]){
					n++;
				}
			}
			return n;	
		}
		void SetGuest(){
			fstream File;
			File.open("Guest4.txt",ios::app);
			if(File){
				cout<<"==========Information of Guest 4 Girls Hostel============="<<endl;
				File<<"**********Guests Information**********"<<endl;
				File<<"Student ID \tGuest Name\t\tBill"<<endl;
				for(int i=0;i<5;i++){
					cout<<"Enter Guest Name: ";
					cin>>Name[i];
					cout<<"Enter Student ID: ";
					cin>>SID[i];
					cout<<"Enter Total Bill: ";
					cin>>Bill[i];
					int TotalNumber=GuestTotal(SID[i]);
					if(TotalNumber>3){
						cout<<"Student already have 3 guests."<<endl;
					}
					else{
						File<<SID[i]<<"\t\t"<<Name[i]<<"\t\t\t"<<Bill[i]<<endl;
					}
				}
				File.close();
			}
			else{
				cout<<"Guest 4 File is not Created!"<<endl;
			}	
		}
};
class Clothes1:public Hostel1{
	private:
		int Wash,Iron;
		float WashPrice,IronPrice,HostelShareIron,HostelShareWash;
		float HostelShare;
	public:
		void SetClothes(){
			fstream File;
			File.open("Clothes1.txt",ios::out);
			if(File){
				cout<<"==========Information of Clothes 1 Hostel 1============="<<endl;
				cout<<"Enter No of Wash: ";
				cin>>Wash;
				cout<<"Enter no of Ironing clothes: ";
				cin>>Iron;
				WashPrice=Wash*12;
				IronPrice=Iron*5;
				HostelShareIron=IronPrice*0.15;
				HostelShareWash=WashPrice*0.15;
				WashPrice-=HostelShareWash;
				IronPrice-=HostelShareIron;
				HostelShare=HostelShareWash+HostelShareIron;
				File<<"Price of Washing Clothes after 15% deduction ";
				File<<"of hostel share: "<<WashPrice<<endl;
				File<<"Price of ironing Clothes after 15% deduction ";
				File<<"of hostel share: "<<IronPrice<<endl;	
				File<<"Price of Hostel Share: "<<HostelShare<<endl;	
				File.close();
			}else{
				cout<<"Clothes 1 FIle not Created!!!"<<endl;
			}
		}
};
class Clothes2: public Hostel2{
	private:
		int Wash,Iron;
		float WashPrice,IronPrice,HostelShareIron,HostelShareWash;
		float HostelShare;
	public:
		void SetClothes(){
			fstream File;
			File.open("Clothes2.txt",ios::out);
			if(File){
				cout<<"==========Information of Clothes 2 Hostel 2============="<<endl;
				cout<<"Enter No of Wash: ";
				cin>>Wash;
				cout<<"Enter no of Ironing clothes: ";
				cin>>Iron;
				cout<<"Price of Washing clothes: "<<Wash;
				cout<<"Price of Ironing Clother: "<<Iron;
				WashPrice=Wash*12;
				IronPrice=Iron*5;
				HostelShareIron=IronPrice*0.15;
				HostelShareWash=WashPrice*0.15;
				WashPrice-=HostelShareWash;
				IronPrice-=HostelShareIron;
				HostelShare=HostelShareWash+HostelShareIron;
				File<<"Price of Washing Clothes after 15% deduction ";
				File<<"of hostel share: "<<WashPrice<<endl;
				File<<"Price of ironing Clothes after 15% deduction ";
				File<<"of hostel share: "<<IronPrice<<endl;	
				File<<"Price of Hostel Share: "<<HostelShare<<endl;	
				File.close();
			}else{
				cout<<"Clothes 2 File not Created!!!"<<endl;
			}
		}
};
class Clothes3:public Hostel3{
	private:
		int Wash,Iron;
		float WashPrice,IronPrice,HostelShareIron,HostelShareWash;
		float HostelShare;
	public:
		void SetClothes(){
			fstream File;
			File.open("Clothes3.txt",ios::out);
			if(File){
				cout<<"==========Information of Clothes 3 Hostel 3============="<<endl;
				cout<<"Enter No of Wash: ";
				cin>>Wash;
				cout<<"Enter no of Ironing clothes: ";
				cin>>Iron;
				cout<<"Price of Washing clothes: "<<Wash;
				cout<<"Price of Ironing Clother: "<<Iron;
				WashPrice=Wash*12;
				IronPrice=Iron*5;
				HostelShareIron=IronPrice*0.15;
				HostelShareWash=WashPrice*0.15;
				WashPrice-=HostelShareWash;
				IronPrice-=HostelShareIron;
				HostelShare=HostelShareWash+HostelShareIron;
				File<<"Price of Washing Clothes after 15% deduction ";
				File<<"of hostel share: "<<WashPrice<<endl;
				File<<"Price of ironing Clothes after 15% deduction ";
				File<<"of hostel share: "<<IronPrice<<endl;	
				File<<"Price of Hostel Share: "<<HostelShare<<endl;	
				File.close();
			}else{
				cout<<"Clothes 3 File not Created!!!"<<endl;
			}
		}
};
class Clothes4:public GirlsHostel{
	private:
		int Wash,Iron;
		float WashPrice,IronPrice,HostelShareIron,HostelShareWash;
		float HostelShare;
	public:
		void SetClothes(){
			fstream File;
			File.open("Clothes4.txt",ios::out);
			if(File){
				cout<<"==========Information of Clothes 4 Girls Hostel============="<<endl;
				cout<<"Enter No of Wash: ";
				cin>>Wash;
				cout<<"Enter no of Ironing clothes: ";
				cin>>Iron;
				cout<<"Price of Washing clothes: "<<Wash;
				cout<<"Price of Ironing Clother: "<<Iron;
				WashPrice=Wash*12;
				IronPrice=Iron*5;
				HostelShareIron=IronPrice*0.15;
				HostelShareWash=WashPrice*0.15;
				WashPrice-=HostelShareWash;
				IronPrice-=HostelShareIron;
				HostelShare=HostelShareWash+HostelShareIron;
				File<<"Price of Washing Clothes after 15% deduction ";
				File<<"of hostel share: "<<WashPrice<<endl;
				File<<"Price of ironing Clothes after 15% deduction ";
				File<<"of hostel share: "<<IronPrice<<endl;	
				File<<"Price of Hostel Share: "<<HostelShare<<endl;	
				File.close();
			}else{
				cout<<"Clothes4 File not open!!!"<<endl;
			}
				
		}
};
class SecuritySystem1:public Hostel1{
	private:
		long int CNIC;
		string GuardName,ChiefName;
		int Fine,StdId;
		int Option;
	public:
		void SetSecuritySystem(){
			cout<<"==========Information of Secuirty System 1 Hostel 1============="<<endl;
			cout<<"Press 1 to Enter Guest CNIC"<<endl;
			cout<<"Press 2 to Enter Shift Guard Details"<<endl;
			cout<<"Press 3 to the details of extra curricular activities"<<endl;
			cout<<"Press 4 to Enter Lost Fine details"<<endl;
			cin>>Option;
			if(Option==1){
				fstream File;
				File.open("GuestID1 Hostel 1.txt",ios::app);
				if(File){
					cout<<"Enter Guest Id Card: ";
					cin>>CNIC;
					File<<CNIC<<endl;
					File<<"----------------------------"<<endl;
					File.close();
				}else{
					cout<<"GuestID1 Hostel 1 File not open!!!";
				}
			}else if(Option==2){
				fstream File;
				File.open("GuardShift1.txt",ios::app);
				if(File){
					for(int i=0;i<4;i++){
						cout<<"Enter Guard Name "<<i+1<<": ";
						cin>>GuardName;
						File<<GuardName<<endl;
						File<<"----------------------------"<<endl;
					}
					cout<<"Enter Chief Name: ";
					cin>>ChiefName;
					File<<"ChiefName is: "<<ChiefName<<endl;
					File<<"----------------------------"<<endl;
					File.close();
				}else{
					cout<<"GuardShift1 Hostel 1 File not open!!!"<<endl;
				}
			}else if(Option==3){
				fstream File;
				File.open("ExtraActivities1 Hostel 1.txt",ios::out);
				if(File){
					File<<"The Extra Curricular Activities includes";
					File<<" trip per weekend and bonfire once a month!!!";
					File.close();
				}else{
					cout<<"ExtraActivities1 Hostel 1 File not open!!!"<<endl;
				}
			}else if(Option==4){
				fstream File;
				File.open("LFItem1 Hostel 1.txt",ios::app);
				if(File){
					cout<<"Enter Student ID: ";
					cin>>StdId;
					cout<<"Lost item Fine: ";
					cin>>Fine;
					File<<StdId<<endl;
					File<<Fine<<endl;
					File<<"-------------------------------\n";
					File.close();
				}else{
					cout<<"LF Item1 Hostel 1 File not open!!!"<<endl;
				}
			}else{
				cout<<"Invalid Option";
			}
		}
};
class SecuritySystem2:public Hostel2{
	private:
		long int CNIC;
		string GuardName,ChiefName;
		int Fine,StdId;
		int Option;
	public:
		void SetSecuritySystem(){
			cout<<"==========Information of Secuirty System 2 Hostel 2============="<<endl;
			cout<<"Press 1 to Enter Guest CNIC"<<endl;
			cout<<"Press 2 to Enter Shift Guard Details"<<endl;
			cout<<"Press 3 to the details of extra curricular activities"<<endl;
			cout<<"Press 4 to Enter Lost Fine details"<<endl;
			cin>>Option;
			if(Option==1){
				fstream File;
				File.open("GuestID2 Hostel 2.txt",ios::app);
				if(File){
					cout<<"Enter Guest Id Card: ";
					cin>>CNIC;
					File<<CNIC<<endl;
					File<<"----------------------------"<<endl;
					File.close();
				}else{
					cout<<"GuestID2 Hostel 2 File not open!!!";
				}
			}else if(Option==2){
				fstream File;
				File.open("GuardShift2.txt",ios::app);
				if(File){
					for(int i=0;i<4;i++){
						cout<<"Enter Guard Name "<<i+1<<": ";
						cin>>GuardName;
						File<<GuardName<<endl;
						File<<"----------------------------"<<endl;
					}
					cout<<"Enter Chief Name: ";
					cin>>ChiefName;
					File<<"ChiefName is: "<<ChiefName<<endl;
					File<<"----------------------------"<<endl;
					File.close();
				}else{
					cout<<"GuardShift2 Hostel 2 File not open!!!"<<endl;
				}
			}else if(Option==3){
				fstream File;
				File.open("ExtraActivities2 Hostel 2.txt",ios::out);
				if(File){
					File<<"The Extra Curricular Activities includes";
					File<<" trip per weekend and bonfire once a month!!!";
					File.close();
				}else{
					cout<<"ExtraActivities2 Hostel 2 File not open!!!"<<endl;
				}
			}else if(Option==4){
				fstream File;
				File.open("LFItem2 Hostel 2.txt",ios::app);
				if(File){
					cout<<"Enter Student ID: ";
					cin>>StdId;
					cout<<"Lost item Fine: ";
					cin>>Fine;
					File<<StdId<<endl;
					File<<Fine<<endl;
					File<<"-------------------------------\n";
					File.close();
				}else{
					cout<<"LF Item2 Hostel 2 File not open!!!"<<endl;
				}
			}else{
				cout<<"Invalid Option";
			}
		}
};
class SecuritySystem3:public Hostel3{
	private:
		long int CNIC;
		string GuardName,ChiefName;
		int Fine,StdId;
		int Option;
	public:
		void SetSecuritySystem(){
			cout<<"==========Information of Secuirty System 3 Hostel 3============="<<endl;
			cout<<"Press 1 to Enter Guest CNIC"<<endl;
			cout<<"Press 2 to Enter Shift Guard Details"<<endl;
			cout<<"Press 3 to the details of extra curricular activities"<<endl;
			cout<<"Press 4 to Enter Lost Fine details"<<endl;
			cin>>Option;
			if(Option==1){
				fstream File;
				File.open("GuestID3 Hostel 3.txt",ios::app);
				if(File){
					cout<<"Enter Guest Id Card: ";
					cin>>CNIC;
					File<<CNIC<<endl;
					File<<"----------------------------"<<endl;
					File.close();
				}else{
					cout<<"GuestID3 Hostel 3 File not open!!!";
				}
			}else if(Option==2){
				fstream File;
				File.open("GuardShift3.txt",ios::app);
				if(File){
					for(int i=0;i<4;i++){
						cout<<"Enter Guard Name "<<i+1<<": ";
						cin>>GuardName;
						File<<GuardName<<endl;
						File<<"----------------------------"<<endl;
					}
					cout<<"Enter Chief Name: ";
					cin>>ChiefName;
					File<<"ChiefName is: "<<ChiefName<<endl;
					File<<"----------------------------"<<endl;
					File.close();
				}else{
					cout<<"GuardShift3 Hostel 3 File not open!!!"<<endl;
				}
			}else if(Option==3){
				fstream File;
				File.open("ExtraActivities3 Hostel 3.txt",ios::out);
				if(File){
					File<<"The Extra Curricular Activities includes";
					File<<" trip per weekend and bonfire once a month!!!";
					File.close();
				}else{
					cout<<"ExtraActivities3 Hostel 3 File not open!!!"<<endl;
				}
			}else if(Option==4){
				fstream File;
				File.open("LFItem3 Hostel 3.txt",ios::app);
				if(File){
					cout<<"Enter Student ID: ";
					cin>>StdId;
					cout<<"Lost item Fine: ";
					cin>>Fine;
					File<<StdId<<endl;
					File<<Fine<<endl;
					File<<"-------------------------------\n";
					File.close();
				}else{
					cout<<"LF Item3 Hostel 3 File not open!!!"<<endl;
				}
			}else{
				cout<<"Invalid Option";
			}
		}
};
class SecuritySystem4:public GirlsHostel{
	private:
		long int CNIC;
		string GuardName,ChiefName;
		int Fine,StdId;
		int Option;
	public:
		void SetSecuritySystem(){
			cout<<"==========Information of Secuirty System 4 Girls Hostel============="<<endl;
			cout<<"Press 1 to Enter Guest CNIC"<<endl;
			cout<<"Press 2 to Enter Shift Guard Details"<<endl;
			cout<<"Press 3 to the details of extra curricular activities"<<endl;
			cout<<"Press 4 to Enter Lost Fine details"<<endl;
			cin>>Option;
			if(Option==1){
				fstream File;
				File.open("GuestID4 Girls Hostel.txt",ios::app);
				if(File){
					cout<<"Enter Guest Id Card: ";
					cin>>CNIC;
					File<<CNIC<<endl;
					File<<"----------------------------"<<endl;
					File.close();
				}else{
					cout<<"GuestID4 Girls Hostel File not open!!!";
				}
			}else if(Option==2){
				fstream File;
				File.open("GuardShift4.txt",ios::app);
				if(File){
					for(int i=0;i<4;i++){
						cout<<"Enter Guard Name "<<i+1<<": ";
						cin>>GuardName;
						File<<GuardName<<endl;
						File<<"----------------------------"<<endl;
					}
					cout<<"Enter Chief Name: ";
					cin>>ChiefName;
					File<<"ChiefName is: "<<ChiefName<<endl;
					File<<"----------------------------"<<endl;
					File.close();
				}else{
					cout<<"GuardShift4 Girls Hostel File not open!!!"<<endl;
				}
			}else if(Option==3){
				fstream File;
				File.open("ExtraActivities4 Girls Hostel.txt",ios::out);
				if(File){
					File<<"The Extra Curricular Activities includes";
					File<<" trip per weekend and bonfire once a month!!!";
					File.close();
				}else{
					cout<<"ExtraActivities4 Girls Hostel File not open!!!"<<endl;
				}
			}else if(Option==4){
				fstream File;
				File.open("LFItem4 Girls Hostel.txt",ios::app);
				if(File){
					cout<<"Enter Student ID: ";
					cin>>StdId;
					cout<<"Lost item Fine: ";
					cin>>Fine;
					File<<StdId<<endl;
					File<<Fine<<endl;
					File<<"-------------------------------\n";
					File.close();
				}else{
					cout<<"LF Item4 Girls Hostel File not open!!!"<<endl;
				}
			}else{
				cout<<"Invalid Option";
			}
		}
};
class Salaries:public Hostel1,Hostel2,Hostel3,GirlsHostel{
	public:
		void SetSalaries(){
			fstream File;
			File.open("Salaries.txt",ios::out);
			if(File){
				cout<<"==========Information of Salaries for All Hostels============="<<endl;
				File<<"Manager 25k"<<endl;
				File<<"Guard 15k"<<endl;
				File<<"Cook 15k"<<endl;
				File<<"Sweeper 10k"<<endl;
				File<<"Serving Boy 5k"<<endl;
			} 
		}
};
int main()
{
	int O;
	char P;
	cout<<"*********************************"<<endl;
	cout<<"*\t\tMenu Hostel Management System*"<<endl;
	cout<<"*********************************"<<endl;
	cout<<"Press 1 For Enter Data of Hostel 1"<<endl;
	cout<<"Press 2 For Enter Data of Hostel 2"<<endl;
	cout<<"Press 3 For Enter Data of Hostel 3"<<endl;
	cout<<"Press 4 For Enter Data of Hostel 4"<<endl;
	cin>>O;
	if(O==1){
		cout<<"*********Hostel 1***********"<<endl;
		Hostel1 h1;
		h1.SetStudent();
		cout<<"Press A/a for Enter Data of Mess 1"<<endl;
		cout<<"Press B/b for Enter Data of Guest 1"<<endl;
		cout<<"Press C/c for Enter Data of Clothes 1"<<endl;
		cout<<"Press D/d for Enter Data of Security 1"<<endl;
		cin>>P;
		switch(P){
			case 'A':
			case 'a':{
				Mess1 m1;
				m1.SetMess();
				break;
			}
			case 'B':
			case 'b':{
				Guest1 G1;
    			G1.SetGuest();
				break;
			}
    		case 'C':
    		case 'c':{
    			Clothes1 C1;
    			C1.SetClothes();
				break;
			}
   			case 'D':
   			case 'd':{
   				SecuritySystem1 S1;
    			S1.SetSecuritySystem();
				break;
			}
   				
		}
	}else if(O==2){
		cout<<"*********Hostel 2***********"<<endl;
		Hostel2 h2;
    	h2.SetStudent();
		cout<<"Press A/a for Enter Data of Mess 1"<<endl;
		cout<<"Press B/b for Enter Data of Guest 1"<<endl;
		cout<<"Press C/c for Enter Data of Clothes 1"<<endl;
		cout<<"Press D/d for Enter Data of Secuirity 1"<<endl;
		cin>>P;
		switch(P){
			case 'A':
			case 'a':{
				Mess2 m2;
    			m2.SetMess();
				break;
			}
			case 'B':
			case 'b':{
				Guest2 G2;
    			G2.SetGuest();
				break;
			}
    		case 'C':
    		case 'c':{
    			Clothes2 C2;
    			C2.SetClothes();
				break;
			}
   			case 'D':
   			case 'd':{
   				SecuritySystem2 S2;
    			S2.SetSecuritySystem();
				break;
			}
   				
		}
	}else if(O==3){
		cout<<"*********Hostel 3***********"<<endl;
		Hostel3 h3;
    	h3.SetStudent();
		cout<<"Press A/a for Enter Data of Mess 1"<<endl;
		cout<<"Press B/b for Enter Data of Guest 1"<<endl;
		cout<<"Press C/c for Enter Data of Clothes 1"<<endl;
		cout<<"Press D/d for Enter Data of Secuirity 1"<<endl;
		cin>>P;
		switch(P){
			case 'A':
			case 'a':{
				Mess3 m3;
				m3.SetMess();
				break;
			}
			case 'B':
			case 'b':{
				Guest3 G3;
    			G3.SetGuest();
				break;
			}
    		case 'C':
    		case 'c':{
    			Clothes3 C3;
    			C3.SetClothes();
				break;
			}
   			case 'D':
   			case 'd':{
   				SecuritySystem3 S3;
    			S3.SetSecuritySystem();
				break;
			}
   				
		}
	}else if(O==4){
		cout<<"*********Hostel 3***********"<<endl;
		GirlsHostel Gh;
    	Gh.SetStudent();
		cout<<"Press A/a for Enter Data of Mess 1"<<endl;
		cout<<"Press B/b for Enter Data of Guest 1"<<endl;
		cout<<"Press C/c for Enter Data of Clothes 1"<<endl;
		cout<<"Press D/d for Enter Data of Secuirity 1"<<endl;
		cin>>P;
		switch(P){
			case 'A':
			case 'a':{
				Mess4 m4;
    			m4.SetMess();
				break;
			}
			case 'B':
			case 'b':{
				Guest4 G4;
    			G4.SetGuest();
				break;
			}
    		case 'C':
    		case 'c':{
    			Clothes4 C4;
    			C4.SetClothes();
				break;
			}
   			case 'D':
   			case 'd':{
   				SecuritySystem4 S4;
   				S4.SetSecuritySystem();
				break;
			}
   				
		}
	}
   	
    Salaries Salary;
    Salary.SetSalaries();
    Management M;
    M.SetSalariesAndHostelProfit();
    M.ShowTotalDues();
    return 0;
}
