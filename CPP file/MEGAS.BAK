//School Timetable Program
#include<fstream.h>
#include<conio.h>
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
#include<ctype.h>
class timetable
{
 public:
 //Data members
 char store[22][16]; //Store staff data
 char stud[6][9][6][4],teach[6][9][21][7]; //Arrays for teacher and student timetables
 //Constructor
 timetable(); //Initializes the first slot as days of the week and the empty slots
 //Member functions
 int checkperiod(char*,int,int); //Checks if there is some undesired period on a given day
 int checknop(char*,int); //Counts total number of periods of a subject in a week
 void info(); //Gives information about the product
 void pt(); //Allots P.T periods to each class
 void yoga(); //Alots yoga periods to each class
 void mains12(); //Allots main subjects to class XII
 void mains11(); //Allots main subjects to class XI
 void firstper12(); //Initializes double periods for Class XII
 void practicals(); //Initializes practical periods for both standards
 void intro(); //Main output window
 void filetable(); //Prints the timetables generated in a .txt file, randomizes timetable combinations and also generates output in the Output window
 void mainmenu(); //Displays mainmenu
 void beg(); //Goes to beginning of program
 void generate(); //Generates the timetable
 void displaystud(int); //Displays Student timetable
 void displayteach(int); //Displays Teacher timetable
};

timetable::timetable()
{
 int i,j,k,l;
 char days[6][4]={"Mon","Tue","Wed","Thu","Fri","Sat"}; //Array containg the six working days of the week
 for(k=0,l=0;k<6,l<21;k++,l++)
 for(i=0;i<6;i++)
 for(j=0;j<9;j++)
 {
  strcpy(stud[i][j][k],"---");
  strcpy(teach[i][j][l],"-----");   //Initialize all periods as blanks
 }
 for(k=0,l=0;k<6,l<21;k++,l++)
 for(j=6;j<9;j++)
 {
  strcpy(stud[5][j][k],"   ");
  strcpy(teach[5][j][l],"   ");  //Saturday has only 5 periods. So remove required slots
 }
 for(k=0;k<6;k++)
 for(i=0;i<6;i++)
 strcpy(stud[i][0][k],days[i]);
 for(k=0;k<21;k++)
 for(i=0;i<6;i++)
 strcpy(teach[i][0][k],days[i]);  //Give first slot as day of the week
}

void timetable::mainmenu()
{
 textbackground(BLUE);
 textcolor(GREEN);
 clrscr();
 gotoxy(28,10);
 cout<<"MAIN MENU";
 gotoxy(24,11);
 cout<<"1.View Constraints.";
 gotoxy(24,12);
 cout<<"2.Generate a Time Table";
 gotoxy(24,13);
 cout<<"3.Exit";
 gotoxy(24,14);
 cout<<"Enter your choice: ";
 char ch;
 cin>>ch;
 switch(ch)
 {
  default:
  {
   cout<<"\n\nDidn't get you!";
   cout<<"\nPress any key to return to main screen.";
   getch();
   beg();
   break;
  }
  case '3':
  {
   clrscr();
   gotoxy(23,9);
   cout<<"We hope you liked our product.";
   gotoxy(20,12);
   cout<<"Please send your feedback and enquiries to:";
   gotoxy(23,14);
   cout<<"ROUNAK BANIK";
   gotoxy(23,15);
   cout<<"e-mail: rounakbanik@gmail.com";
   gotoxy(23,16);
   cout<<"Phone: +919840445150";
   getch();
   break;
  }
  case '2':
  {
   clrscr();
   gotoxy(10,6);
   cout<<"Please open 'God.txt' to view the entire timetable of the school";
   gotoxy(23,12);
   cout<<"TIMETABLE MENU";
   gotoxy(23,14);
   cout<<"1.Classroom Timetables";
   gotoxy(23,15);
   cout<<"2.Teacher Timetables";
   gotoxy(23,16);
   cout<<"3.Return to Main Menu";
   gotoxy(23,18);
   cout<<"Enter your choice: ";
   char ch5;
   cin>>ch5;
   switch(ch5)
   {
    default:
    {
     cout<<"\n\nDidn't get you!";
     cout<<"\nPress any key to return to main menu";
     getch();
     mainmenu();
     break;
    }
    case '3':
    {
     mainmenu();
     break;
    }
    case '2':
    {
     clrscr();
     gotoxy(13,1);
     cout<<"TEACHER TIMETABLE MENU";
     gotoxy(13,3);
     cout<<"A.Physics Lab \t\tB.Chemistry Lab";
     gotoxy(13,4);
     cout<<"C.Biology Lab \t\tD.Computer Lab";
     gotoxy(13,5);
     cout<<"E.ED Lab      \t\tF.PT";
     gotoxy(13,6);
     cout<<"G.Yoga        \t\tH.Physics XI";
     gotoxy(13,7);
     cout<<"I.Chemistry XI\t\tJ.Math XI";
     gotoxy(13,8);
     cout<<"K.English XI  \t\tL.GVC";
     gotoxy(13,9);
     cout<<"M.WE          \t\tN.Biology";
     gotoxy(13,10);
     cout<<"O.Computer    \t\tP.ED";
     gotoxy(13,11);
     cout<<"Q.Physics XII\t\tR.Chemistry XII";
     gotoxy(13,12);
     cout<<"S.Math XII   \t\tT.English XII";
     gotoxy(13,13);
     cout<<"U.Art";
     gotoxy(13,14);
     cout<<"Press any other character to return to main menu";
     gotoxy(13,16);
     cout<<"Enter your choice: ";
     char ch12;
     cin>>ch12;
     switch(toupper(ch12))
     {

      default:
      {
       cout<<"\n\nDidn't get you!";
       cout<<"\nPress any key to return to main menu";
       getch();
       mainmenu();
       break;
      }
      case 'U':
      {
       clrscr();
       displayteach(20);
       getch();
       mainmenu();
       break;
      }
      case 'T':
      {
       clrscr();
       int a;
       for(a=16;a<20;a++)
       if(strcmp(store[a],"English XII")==0)
       break;
       displayteach(a);
       getch();
       mainmenu();
       break;
      }
      case 'S':
      {
       clrscr();
       int a;
       for(a=16;a<20;a++)
       if(strcmp(store[a],"Maths XII")==0)
       break;
       displayteach(a);
       getch();
       mainmenu();
       break;
      }
      case 'R':
      {
       clrscr();
       int a;
       for(a=16;a<20;a++)
       if(strcmp(store[a],"Chemistry XII")==0)
       break;
       displayteach(a);
       getch();
       mainmenu();
       break;
      }
      case 'Q':
      {
       clrscr();
       int a;
       for(a=16;a<20;a++)
       if(strcmp(store[a],"Physics XII")==0)
       {
	break;
       }
       displayteach(a);
       getch();
       mainmenu();
       break;
      }
      case 'P':
      {
       clrscr();
       displayteach(15);
       getch();
       mainmenu();
       break;
      }
      case 'O':
      {
       clrscr();
       displayteach(14);
       getch();
       mainmenu();
       break;
      }
      case 'N':
      {
       clrscr();
       displayteach(13);
       getch();
       mainmenu();
       break;
      }
      case 'M':
      {
       clrscr();
       displayteach(12);
       getch();
       mainmenu();
       break;
      }
      case 'L':
      {
       clrscr();
       displayteach(11);
       getch();
       mainmenu();
       break;
      }
      case 'K':
      {
       clrscr();
       int a;
       for(a=7;a<11;a++)
       if(strcmp(store[a],"English XI")==0)
       break;
       displayteach(a);
       getch();
       mainmenu();
       break;
      }
      case 'J':
      {
       clrscr();
       int a;
       for(a=7;a<11;a++)
       if(strcmp(store[a],"Maths XI")==0)
       break;
       displayteach(a);
       getch();
       mainmenu();
       break;
      }
      case 'I':
      {
       clrscr();
       int a;
       for(a=7;a<11;a++)
       if(strcmp(store[a],"Chemistry XI")==0)
       break;
       displayteach(a);
       getch();
       mainmenu();
       break;
      }
      case 'H':
      {
       clrscr();
       int a;
       for(a=7;a<11;a++)
       if(strcmp(store[a],"Physics XI")==0)
       break;
       displayteach(a);
       getch();
       mainmenu();
       break;
      }
      case 'G':
      {
       clrscr();
       displayteach(6);
       getch();
       mainmenu();
       break;
      }
      case 'F':
      {
       clrscr();
       displayteach(5);
       getch();
       mainmenu();
       break;
      }
      case 'E':
      {
       clrscr();
       displayteach(4);
       getch();
       mainmenu();
       break;
      }
      case 'D':
      {
       clrscr();
       displayteach(3);
       getch();
       mainmenu();
       break;
      }
      case 'C':
      {
       clrscr();
       displayteach(2);
       getch();
       mainmenu();
       break;
      }
      case 'B':
      {
       clrscr();
       displayteach(1);
       getch();
       mainmenu();
       break;
      }
      case 'A':
      {
	clrscr();
	displayteach(0);
	getch();
	mainmenu();
	break;
      }
     }
    break;
    }
    case '1':
    {
     clrscr();
     gotoxy(23,9);
     cout<<"CLASSROOM MENU";
     gotoxy(23,11);
     cout<<"1.XI-A";
     gotoxy(23,12);
     cout<<"2.XI-B";
     gotoxy(23,13);
     cout<<"3.XI-C";
     gotoxy(23,14);
     cout<<"4.XII-A";
     gotoxy(23,15);
     cout<<"5.XII-B";
     gotoxy(23,16);
     cout<<"6.XII-C";
     gotoxy(23,17);
     cout<<"7.Return to Main Menu: ";
     gotoxy(23,19);
     cout<<"Enter your choice: ";
     char ch24;
     cin>>ch24;
     switch(ch24)
     {
      default:
      {
       cout<<"\n\nDidn't get you!";
       cout<<"\nPress any key to return to main menu";
       getch();
       mainmenu();
       break;
      }
      case '7':
      {
       mainmenu();
       break;
      }
      case '6':
      {
       clrscr();
       displaystud(5);
       getch();
       mainmenu();
       break;
      }
      case '5':
      {
       clrscr();
       displaystud(4);
       getch();
       mainmenu();
       break;
      }
      case '4':
      {
       clrscr();
       displaystud(3);
       getch();
       mainmenu();
       break;
      }
      case '3':
      {
       clrscr();
       displaystud(2);
       getch();
       mainmenu();
       break;
      }
      case '2':
      {
       clrscr();
       displaystud(1);
       getch();
       mainmenu();
       break;
      }
      case '1':
      {
       clrscr();
       displaystud(0);
       getch();
       mainmenu();
       break;
      }


     }
     break;
    }
   }
   break;
  }
  case '1':
  {
   clrscr();
   gotoxy(23,9);
   cout<<"CONSTRAINTS MENU";
   gotoxy(23,11);
   cout<<"1.General Constraints";
   gotoxy(23,12);
   cout<<"2.Classroom Constraints";
   gotoxy(23,13);
   cout<<"3.Teacher Constraints";
   gotoxy(23,14);
   cout<<"4.Staff Statistics";
   gotoxy(23,15);
   cout<<"5.Subject Constraints";
   gotoxy(23,16);
   cout<<"6.Return to Main Menu";
   gotoxy(23,18);
   cout<<"Enter your choice: ";
   char ch8;
   cin>>ch8;
   switch(ch8)
   {
    default:
    {
     cout<<"\n\nDidn't get you!";
     cout<<"\nPress any key to return to main menu";
     getch();
     mainmenu();
     break;
    }
    case '6':
    {
     mainmenu();
     break;
    }
    case '5':
    {
     clrscr();
     cout<<"\n\t\t\tSUBJECT CONSTRAINTS";
     cout<<"\n\n\n1.The main subjects (Physics, CHEMISTRY, Maths, English, Optional) have 6 \ntheory periods and 2 practical periods in a week. The theory and practical \nperiods are handledby different teachers.";
     cout<<"\n2.There are three practical periods in a week, amounting to a total of 6\n periods. Each practical period allots itself two labs. The class is divided \ninto two and attends the two labs separately.";
     cout<<"\n3.The labs have a maximum capacity of 20 students.";
     cout<<"\n4.Each class is alloted 2 Physcial Timings (PT) periods in a week. These\n periods occur in a block. Only one class can aatend PT at a time.";
     cout<<"\n5.There are 2 Yoga periods for a class in a week. All the sections of class XI\n attend Yoga at a time. Same applies to class XII.";
     cout<<"\n6.There is one Zero hour for each class in a week. The zero periods have the \nsame slots for class XI and XII.";
     cout<<"\n7.There are 1 GVC and 1 Art periods for each class in a week. No two classes can attend these periods at the same time.";
     cout<<"\n8.PT, Art, GVC and WE cannot be alloted the first slot on any given day.";
     cout<<"\n\nPress any key to return to main menu.";
     getch();
     mainmenu();
     break;
    }
    case '4':
    {
     clrscr();
     cout<<"\n\t\t\tSTAFF STATISTICS";
     cout<<"\n\n\n1. Physics:                 2 (One each for class XI and XII)";
     cout<<"\n2. Chemistry:               2 (One each for class XI and XII)";
     cout<<"\n3. Mathematics:             2 (One each for class XI and XII)";
     cout<<"\n4. English:                 2 (One each for class XI and XII)";
     cout<<"\n5. Biology:                 1";
     cout<<"\n6. Computer Science:        1";
     cout<<"\n7. Engineering Drawing:     1";
     cout<<"\n8. Physics Lab:             1";
     cout<<"\n9. Chemistry Lab:           1";
     cout<<"\n10.Biology Lab:             1";
     cout<<"\n11.C.Sc Lab:                1";
     cout<<"\n12.ED Lab:                  1";
     cout<<"\n13.Yoga:                    1";
     cout<<"\n14.Work Experience          1";
     cout<<"\n15.PT                       1";
     cout<<"\n16.GVC                      1";
     getch();
     mainmenu();
     break;
    }
    case '3':
    {
     clrscr();
     cout<<"\n\t\t\tTEACHER CONSTRAINTS";
     cout<<"\n\n\n1.There are 20 staff members in the High School.";
     cout<<"\n2.Each teacher can attend only one class at a time.";
     cout<<"\n3.No more than one teacher can attend a particular class at a time";
     cout<<"\n4.No teacher can have more than 6 periods in a day. The exception to this rule \nare the Science labs";
     cout<<"\n5.No teacher can have more than 30 periods in a week.";
     cout<<"\n6.Each teacher has to teach the full class strength during her alloted slot. \nAgain the exception to this rule are the labs.";
     getch();
     mainmenu();
     break;
    }
    case '2':
    {
     clrscr();
     cout<<"\n\t\t\tCLASSROOM CONSTRAINTS";
     cout<<"\n\n\n1.Each class has a maximum strength of 40 students.";
     cout<<"\n2.Each class can attend only one period at a time.";
     cout<<"\n3.The exception to the above rule is during practical periods when the class \ndivides into two and attends two different practical classes.";
     cout<<"\n4.For class XII students, the first two periods of the five, full working \ndays have to be block periods of one of the main subjects";
     cout<<"\n5.'A' sections of both standards haver their optional subject as Biology. \n'B' sections have Computer Science and 'C' sections have Engineering Drawing";
     cout<<"\n6.Each class has the following subjects:";
     cout<<"\nPhysics, Chemistry, Maths, Optional, English, Physics Practicals, \nChemistry Practicals, Optional Practicals, GVC, WE, Yoga, Art, PT and Zero hour.";
     getch();
     mainmenu();
     break;
    }
    case '1':
    {
     clrscr();
     cout<<"\n\t\t\tGENERAL CONSTRAINTS";
     cout<<"\n1.The timetable has been generated according to the format followed by \nIndian High Schools";
     cout<<"\n2.The timetable has been generated for the science stream of high school classes";
     cout<<"3.The school functions for 6 days a week.";
     cout<<"\n4.There are 8 periods in a day, except for Saturdays which has only 5 periods.";
     cout<<"\n5.There are a total of 6 classes; 3 each in class XI and XII";
     cout<<"\n6.There are 20 staff members in the school.";
     cout<<"\n7.The school has a facility of 6 labs: Physics, Chemistry, Biology, CSc, ED.";
     getch();
     mainmenu();
     break;
    }
   }
   break;
  }
 }
}

void timetable::intro()
{
 textbackground(BLUE);
 textcolor(GREEN);
 clrscr();
 cout<<"\n\t\t\t____________________";
 cout<<"\n\t\t\t| Che | Eng | Phy  |";
 cout<<"\n\t\t\t--------------------";
 cout<<"\n\t\t\t| Art | WE  | Mat  |";
 cout<<"\n\t\t\t--------------------";
 cout<<"\n\t\t\t| PO  | CO  |  OP  |";
 cout<<"\n\t\t\t____________________";
 gotoxy(23,12);
 cout<<"MEGAS TIMETABLE GENERATOR";
 gotoxy(20,13);
 cout<<"AN EPICUREAN ENTERPRISE PRODUCT";
 gotoxy(53,25);
 cout<<"A Rounak Banik Production.";
 gotoxy(23,15);
 cout<<"PRESS ANY KEY TO CONTINUE. ";
 getch();
}

void timetable::info()
{
 clrscr();
 textbackground(BLUE);
 textcolor(GREEN);
 gotoxy(23,1);
 cout<<"WONDER TIMETABLE GENERATOR";
 gotoxy(20,2);
 cout<<"AN EPICUREAN ENTERPRISE PRODUCT";
 cout<<"\n\nWe at Epicurean Enterprises understand the time and effort that goes into \nbuliding the timetable for a school.";
 cout<<"\nWe have therefore created a software that could be the answer to your \nproblems.";
 cout<<"\nWe build a timetable for you in a matter of seconds!";
 cout<<"\nThe Timetable is built according to the General norms followed by \nIndian High Schools.";
 cout<<"\n\nNOTE:";
 cout<<"\nTo view the complete set of constraints used, please refer to 'Constraint.txt' \nfile which comes with this product";
 cout<<"\nAlternatively, you can choose to directly view the constraints in the Output \nwindow itself.";
 cout<<"\n\n\nPRESS ANY KEY TO PROCEED TO MAIN MENU ";
 getch();
}

void just()
{

 char ch;
 cin>>ch;
}

int timetable::checknop(char ch[],int k)
{
 int i,j;
 int n=0; //Counter
 for(i=0;i<5;i++)
 for(j=0;j<9;j++)
 if(strcmp(stud[i][j][k],ch)==0)
 n++;
 return n;
}

int timetable::checkperiod(char ch[],int i,int k)
{
 int j;
 int n=0;
 for(j=0;j<9;j++)
 if(strcmp(stud[i][j][k],ch)==0)
 {
  n++;
 }
 return n;
}


void timetable::firstper12()
{
 int i,j,k;
 int x=0;
 char classes[3][7]={"XII-A","XII-B","XII-C"};
 char periods[5][6]={"Phy","Che","Mat","Eng","Opt"};
 char optional[3][6]={"Bio","Csc","ED "};
 for(k=3;k<6;k++)
 {
  x=k%3;
  for(i=0;i<5;i++)
  {
   if(x!=4)
   {
    strcpy(stud[i][1][k],periods[x%5]);
    strcpy(stud[i][2][k],periods[x%5]);
    strcpy(teach[i][1][x%5+16],classes[k%3]);
    strcpy(teach[i][2][x%5+16],classes[k%3]);
    x++;
   }
   else
   {
    strcpy(stud[i][1][k],optional[k%3]);
    strcpy(stud[i][2][k],optional[k%3]);
    strcpy(teach[i][1][k+10],classes[k%3]);
    strcpy(teach[i][2][k+10],classes[k%3]);
    x++;
   }
  }
  x++;
 }
}

void timetable::mains11()
{
 //Optional Subject fill-up. Wr have to make sure that the slot is not already taken up by a section in class XII
 int i,j;
 int l=13; //Number alloted as per teacher timetable display
 int k=0; //Controls class
 int x=0; //Keeps a check on the fact that teacher has only particular number of slots in a week
 int y=0; //Keeps a check for the number of periods of a subject for a class in a week
 char classes[3][6]={"XI-A ","XI-B ","XI-C "};
 char optional[3][5]={"Bio","Csc","ED "};
 while(k<3)
 {
  for(i=0;i<6;i++)
  for(j=0;j<9;j++)
  {
   if(strcmp(teach[i][j][l],"-----")==0&&x<6&&strcmp(stud[i][j][k],"---")==0&&y<6&&checkperiod(optional[l%13],i,k)==0)
   {
    x++;
    y++;
    strcpy(teach[i][j][l],classes[k]);
    strcpy(stud[i][j][k],optional[l%13]);
   }
  }
  if(y==6)
  {
   k++;
   l++;
   y=0;
   x=0;
  }
 }
 //Maths, Physics,Chemistry allocation
 l=7;
 k=0;
 x=0;
 y=0;
 char subjects[4][5]={"Phy","Che","Mat","Eng"};
 while(l<10)
 {
  while(k<3)
  {
   for(i=0;i<6;i++)
   for(j=0;j<9;j++)
   {
    if(strcmp(teach[i][j][l],"-----")==0&&x<18&&strcmp(stud[i][j][k],"---")==0&&y<6&&checkperiod(subjects[l%7],i,k)==0)
    {
     x++;
     y++;
     strcpy(teach[i][j][l],classes[k]);
     strcpy(stud[i][j][k],subjects[l%7]);
    }
   }
   if(y==6)
   {
    k++;
    y=0;
   }
  }
  if(x==18)
  {
   l++;
   x=0;
   y=0;
   k=0;
  }
 }
  //For english, the constraints applied above will result in error due to inadequate number of appropriate slots. So, we relax the constraint and allow two periods of English in a day
 l=10;
 x=0;
 y=0;
 k=0;
 while(k<3)
 {
  for(i=0;i<6;i++)
  for(j=0;j<9;j++)
  {
   if(strcmp(teach[i][j][l],"-----")==0&&x<15&&y<5&&strcmp(stud[i][j][k],"---")==0&&checkperiod("Eng",i,k)<1)
   {
    x++;
    y++;
    strcpy(teach[i][j][l],classes[k%3]);
    strcpy(stud[i][j][k],subjects[l%7]);
   }
  }
  if(y==5)
  {
   k++;
   y=0;
  }
 }
//To fill up the sixth slot. We see that XI-A has an extra slot whereas the other two do not. So, we relax the constraint for them and allow two periods a day
 for(i=0;i<6;i++)
 for(j=0;j<9;j++)
 if(strcmp(teach[i][j][l],"-----")==0&&strcmp(stud[i][j][0],"---")==0&&checkperiod("Eng",i,0)<1)
 {
  strcpy(teach[i][j][l],classes[0]);
  strcpy(stud[i][j][0],subjects[l%7]);
  break;
 }
 y=0;
 for(i=0;i<6;i++)
 for(j=0;j<9;j++)
 if(y==0&&strcmp(teach[i][j][l],"-----")==0&&strcmp(stud[i][j][1],"---")==0&&checkperiod("Eng",i,1)<2)
 {
  strcpy(teach[i][j][l],classes[1]);
  strcpy(stud[i][j][1],subjects[l%7]);
  y++;
  break;
 }
 y=0;
 for(i=0;i<6;i++)
 for(j=0;j<9;j++)
 if(y==0&&strcmp(teach[i][j][l],"-----")==0&&strcmp(stud[i][j][2],"---")==0&&checkperiod("Eng",i,2)<2)
 {
  strcpy(teach[i][j][l],classes[2]);
  strcpy(stud[i][j][2],subjects[l%7]);
  y++;
  break;
 }
 //Zero period allocation
 for(k=0;k<3;k++)
 strcpy(stud[4][8][k],"Zer");
 //Work Experience allocation
 l=12;
 x=0;
 y=0;
 k=0;
 while(k<3)
 {
  for(i=0;i<6;i++)
  for(j=0;j<9;j++)
  {
   if(strcmp(stud[i][j][k],"---")==0&&strcmp(teach[i][j][l],"-----")==0&&x<6&&y<2&&checkperiod("WE ",i,k)<2)
   {
    x++;
    y++;
    strcpy(teach[i][j][l],classes[k]);
    strcpy(stud[i][j][k],"WE ");
   }
  }
  if(y==2)
  {
   y=0;
   k++;
  }
 }
 //GVC allocation
 l=11;
 x=0;
 y=0;
 k=0;
 while(k<3)
 {
  for(i=0;i<6;i++)
  for(j=0;j<9;j++)
  {
   if(strcmp(stud[i][j][k],"---")==0&&strcmp(teach[i][j][l],"-----")==0&&x<6&&y<1&&checkperiod("GVC",i,k)<2)
   {
    x++;
    y++;
    strcpy(teach[i][j][l],classes[k]);
    strcpy(stud[i][j][k],"GVC");
   }
  }
  if(y==1)
  {
   y=0;
   k++;
  }
 }
 //Art allocation. As this is the last subject left, we may just substitute the empty slots with art
 l=20;
 for(k=0;k<3;k++)
 for(i=0;i<6;i++)
 for(j=0;j<9;j++)
 if(strcmp(stud[i][j][k],"---")==0)
 {
  strcpy(stud[i][j][k],"Art");
  strcpy(teach[i][j][l],classes[k]);
 }


}


void timetable::mains12()
{
 //Optional Subject fill-up
 int i,j;
 int l=13; //Number alloted as per teacher timetable display
 int k=3; //Controls class
 int x=0; //Keeps a check on the fact that teacher has only particular number of slots in a week
 int y=0; //Keeps a check for the number of periods of a subject for a class in a week
 char classes[3][6]={"XII-A","XII-B","XII-C"};
 char optional[3][5]={"Bio","Csc","ED "};
 while(k<6)
 {
  for(i=0;i<6;i++)
  for(j=0;j<9;j++)
  {
   if(strcmp(teach[i][j][l],"-----")==0&&x<12&&strcmp(stud[i][j][k],"---")==0&&y<4&&checkperiod(optional[l%13],i,k)==0)
   {
    x++;
    y++;
    strcpy(teach[i][j][l],classes[k%3]);
    strcpy(stud[i][j][k],optional[l%13]);
   }
  }
  if(y==4)
  {
   k++;
   l++;
   y=0;
  }
 }
 //Physics,Maths,Chemistry allocation
 l=16;
 k=3;
 x=0;
 y=0;
 char subjects[4][5]={"Phy","Che","Mat","Eng"};
 while(l<19)
 {
  while(k<6)
  {
   for(i=0;i<6;i++)
   for(j=0;j<9;j++)
   {
    if(strcmp(teach[i][j][l],"-----")==0&&x<12&&strcmp(stud[i][j][k],"---")==0&&y<4&&checkperiod(subjects[l%16],i,k)==0)
    {
     x++;
     y++;
     strcpy(teach[i][j][l],classes[k%3]);
     strcpy(stud[i][j][k],subjects[l%16]);
    }
   }
   if(y==4)
   {
    k++;
    y=0;
   }
  }
  if(x==12)
  {
   l++;
   x=0;
   y=0;
   k=3;
  }
 }
 //For english, the constraints applied above will result in error due to inadequate number of appropriate slots. So, we relax the constraint and allow two periods of English in a day
 l=19;
 x=0;
 y=0;
 k=3;
 while(k<6)
 {
  for(i=0;i<6;i++)
  for(j=0;j<9;j++)
  {
   if(strcmp(teach[i][j][l],"-----")==0&&x<12&&y<4&&strcmp(stud[i][j][k],"---")==0&&((strcmp(stud[i][1][k],"Eng")==0&&checkperiod(subjects[l%16],i,k)<3)||checkperiod(subjects[l%16],i,k)<2))
   {
    x++;
    y++;
    strcpy(teach[i][j][l],classes[k%3]);
    strcpy(stud[i][j][k],subjects[l%16]);
   }
  }
  if(y==4)
  {
   k++;
   y=0;
  }
 }
 //Zero hour allocation
 for(k=3;k<6;k++)
 strcpy(stud[5][5][k],"Zer");
 //Work Experience allocation
 l=12;
 x=0;
 y=0;
 k=3;
 while(k<6)
 {
  for(i=0;i<6;i++)
  for(j=0;j<9;j++)
  {
   if(strcmp(stud[i][j][k],"---")==0&&strcmp(teach[i][j][l],"-----")==0&&x<6&&y<2&&checkperiod("WE ",i,k)<2)
   {
    x++;
    y++;
    strcpy(teach[i][j][l],classes[k%3]);
    strcpy(stud[i][j][k],"WE ");
   }
  }
  if(y==2)
  {
   y=0;
   k++;
  }
 }
 //Art and GVC are manually filled such that they do not clash, in the remaining two slots for each class
 strcpy(stud[5][3][3],"Art"); strcpy(teach[5][3][20],classes[0]);
 strcpy(stud[5][4][4],"Art"); strcpy(teach[5][4][20],classes[1]);
 strcpy(stud[5][2][5],"Art"); strcpy(teach[5][2][20],classes[2]);
 strcpy(stud[5][4][3],"GVC"); strcpy(teach[5][4][11],classes[0]);
 strcpy(stud[5][2][4],"GVC"); strcpy(teach[5][2][11],classes[1]);
 strcpy(stud[5][3][5],"GVC"); strcpy(teach[5][3][11],classes[2]);
}

void timetable::practicals()
{
 int l=0,k=0; //'l' controls lab and 'k' controls the class
 int i,j,y;
 int x=0; //Keeps a check on the fact that Physics lab can be occupied for a maximum of 24 slots
 char classes[6][7]={"XI-A ","XI-B ","XI-C ","XII-A","XII-B","XII-C"};
 while(k<12)
 {
  for(i=0;i<5;i++)
  for(j=0;j<8;j++)
  if(strcmp(teach[i][j][l],"-----")==0&&strcmp(stud[i][j][k%6],"---")==0&&strcmp(teach[i][j+1][l],"-----")==0&&strcmp(stud[i][j+1][k%6],"---")==0&&x<24)
  {
   strcpy(teach[i][j][l],classes[k%6]);
   strcpy(teach[i][j+1][l],classes[k%6]);
   strcpy(stud[i][j][k%6],"***");
   strcpy(stud[i][j+1][k%6],"***");
   k++;
   x+=2;
  }
  else if(strcmp(teach[i][j][l],"-----")==0&&strcmp(stud[i][j][k%6],"***")==0&&strcmp(teach[i][j+1][l],"-----")==0&&strcmp(stud[i][j+1][k%6],"***")==0&&x<24)
  {
   strcpy(teach[i][j][l],classes[k%6]);
   strcpy(teach[i][j+1][l],classes[k%6]);
   strcpy(stud[i][j][k%6],"$$$");
   strcpy(stud[i][j+1][k%6],"$$$");
   k++;
   x+=2;
  }
 }
 l=1; //Allotment of slots for Chemistry lab. An important point to be noted is that Chemistry and Physics can combine only half the number of times
 k=0;
 x=0;
 y=0; //Counter for the purpose mentioned above
 while(k<12)
 {
  for(i=0;i<5;i++)
  for(j=0;j<8;j++)
  if(strcmp(teach[i][j][l],"-----")==0&&strcmp(teach[i][j][l-1],"-----")==0&&strcmp(stud[i][j][k%6],"---")==0&&strcmp(teach[i][j+1][l],"-----")==0&&strcmp(stud[i][j+1][k%6],"---")==0&&x<24)
  {
   strcpy(teach[i][j][l],classes[k%6]);
   strcpy(teach[i][j+1][l],classes[k%6]);
   strcpy(stud[i][j][k%6],"^^^");
   strcpy(stud[i][j+1][k%6],"^^^");
   k++;
   x+=2;
  }
  else if(strcmp(teach[i][j][l],"-----")==0&&strcmp(stud[i][j][k%6],"***")==0&&strcmp(teach[i][j+1][l],"-----")==0&&strcmp(stud[i][j+1][k%6],"***")==0&&x<24&&y<12)
  {
   strcpy(teach[i][j][l],classes[k%6]);
   strcpy(teach[i][j+1][l],classes[k%6]);
   strcpy(stud[i][j][k%6],"PC ");
   strcpy(stud[i][j+1][k%6],"PC ");
   k++;
   x+=2;
   y+=2;
  }
 }
//Now, to fill in the optional slot. We simply have to merge it with existing lab periods which are not paired up. But we have to take care that there are 3 optional subjects
 for(k=0;k<6;k++)
 for(i=0;i<5;i++)
 for(j=0;j<9;j++)
 if(strcmp(stud[i][j][k],"***")==0)
 {
  strcpy(stud[i][j][k],"OP ");
  strcpy(teach[i][j][k%3+2],classes[k]);
 }
 else if(strcmp(stud[i][j][k],"^^^")==0)
 {
  strcpy(stud[i][j][k],"CO ");
  strcpy(teach[i][j][k%3+2],classes[k]);
 }
}

void timetable::pt()
{
 int i,j;
 char classes[6][6]={"XI-A ","XI-B ","XI-C ","XII-A","XII-B","XII-C"};
 int k=0; //Controls class
 int l=5; //Teacher number as alloted during the display of teacher timetable
 while(k<6)
 {
  for(i=0;i<5;i++)
  for(j=2;j<9;j++) //PT cannot be the first period
  if(strcmp(teach[i][j][l],"-----")==0&&strcmp(teach[i][j+1][l],"-----")==0&&checknop("PT ",k)<2&&strcmp(stud[i][j][k],"---")==0&&strcmp(stud[i][j+1][k],"---")==0&&checkperiod("PC ",i,k)==0&&checkperiod("CO ",i,k)==0&&checkperiod("OP ",i,k)==0)
  {
   strcpy(stud[i][j][k],"PT ");
   strcpy(stud[i][j+1][k],"PT ");
   strcpy(teach[i][j][l], classes[k]);
   strcpy(teach[i][j+1][l], classes[k]);
   k++;
  }
 }
}

void timetable::yoga()
{
 int i,j;
 int l=6; //Number alloted to Yoga as per teacher timetable display
 int n=0; //Keeps a check on the fact that there are only 2 Yoga periods for a class
 for(i=0;i<5;i++)
 for(j=0;j<9;j++)
 {
  if(strcmp(stud[i][j][3],"---")==0&&strcmp(stud[i][j][4],"---")==0&&strcmp(stud[i][j][5],"---")==0&&strcmp(teach[i][j][l],"-----")==0&&n<2&&checkperiod("Yog",i,3)==0)
  {
   n++;
   strcpy(stud[i][j][3],"Yog");
   strcpy(stud[i][j][4],"Yog");
   strcpy(stud[i][j][5],"Yog");
   strcpy(teach[i][j][l],"XII  ");
  }
 }
 n=0;
 for(i=0;i<5;i++)
 for(j=0;j<9;j++)
 {
  if(strcmp(stud[i][j][0],"---")==0&&strcmp(stud[i][j][1],"---")==0&&strcmp(stud[i][j][2],"---")==0&&strcmp(teach[i][j][l],"-----")==0&&n<2&&checkperiod("Yog",i,1)==0)
  {
   n++;
   strcpy(stud[i][j][0],"Yog");
   strcpy(stud[i][j][1],"Yog");
   strcpy(stud[i][j][2],"Yog");
   strcpy(teach[i][j][l],"XI   ");
  }
 }
}

void timetable::filetable()
{
 fstream f("God.txt", ios::out|ios::in);
 char classes[21][20]={"Physics Lab","Chemistry Lab","Biology Lab","Computer Lab","ED Lab","PT ","Yoga","Physics XI","Chemistry XI","Math XI","English XI","GVC","WE","Biology","Computer","ED","Physics XII","Chemistry XII","Maths XII","English XII","Art"};
 int i,j,k;
 /*We have now generated a timetable. It is now possible to swap positions of English,Physics,Chemistry and Maths of classes
   XI and XII to generate a total of 4!x4! combinations! */
 //Swapping class XI subjects
 char subj[4][5]={"Phy","Che","Mat","Eng"};
 char swapper[4][20]={"Physics XI","Chemistry XI","Maths XI","English XI"};
 char subjswap[4][5];
 char temp[10];
 int l,m,n;
 for(l=0;l<4;l++)
 {
  n=random(4-l);
  strcpy(classes[7+l],swapper[n]);
  strcpy(temp,swapper[n]);
  strcpy(swapper[n],swapper[4-1-l]);
  strcpy(swapper[4-1-l],temp);
  strcpy(subjswap[l],subj[n]);
  strcpy(temp,subj[n]);
  strcpy(subj[n],subj[4-1-l]);
  strcpy(subj[4-1-l],temp);
 }
 for(k=0;k<3;k++)
 for(i=0;i<6;i++)
 for(j=0;j<9;j++)
 {
  if(strcmp(stud[i][j][k],"Phy")==0)
  strcpy(stud[i][j][k],subjswap[0]);
  else if(strcmp(stud[i][j][k],"Che")==0)
  strcpy(stud[i][j][k],subjswap[1]);
  else if(strcmp(stud[i][j][k],"Mat")==0)
  strcpy(stud[i][j][k],subjswap[2]);
  else if(strcmp(stud[i][j][k],"Eng")==0)
  strcpy(stud[i][j][k],subjswap[3]);
  else
  continue;
 }
 //Swapping Class XII subjects
 char subj1[4][5]={"Phy","Che","Mat","Eng"};
 char swapper1[4][20]={"Physics XII","Chemistry XII","Maths XII","English XII"};
 for(l=0;l<4;l++)
 {
  n=random(4-l);
  strcpy(classes[16+l],swapper1[n]);
  strcpy(temp,swapper1[n]);
  strcpy(swapper1[n],swapper1[4-1-l]);
  strcpy(swapper1[4-1-l],temp);
  strcpy(subjswap[l],subj1[n]);
  strcpy(temp,subj1[n]);
  strcpy(subj1[n],subj1[4-1-l]);
  strcpy(subj1[4-1-l],temp);
 }
 for(k=3;k<6;k++)
 for(i=0;i<6;i++)
 for(j=0;j<9;j++)
 {
  if(strcmp(stud[i][j][k],"Phy")==0)
  strcpy(stud[i][j][k],subjswap[0]);
  else if(strcmp(stud[i][j][k],"Che")==0)
  strcpy(stud[i][j][k],subjswap[1]);
  else if(strcmp(stud[i][j][k],"Mat")==0)
  strcpy(stud[i][j][k],subjswap[2]);
  else if(strcmp(stud[i][j][k],"Eng")==0)
  strcpy(stud[i][j][k],subjswap[3]);
  else
  continue;
 }
 for(k=0;k<21;k++)
 {
  f<<classes[k]<<"\n";
  for(i=0;i<6;i++)
  {
   for(j=0;j<9;j++)
   f<<teach[i][j][k]<<"  ";
   f<<"\n";
  }
  f<<"\n\n";
 }
 char classe[6][6]={"XI-A","XI-B","XI-C","XII-A","XII-B","XII-C"};
 for(k=0;k<6;k++)
 {
  f<<classe[k]<<"\n";
  for(i=0;i<6;i++)
  {
   for(j=0;j<9;j++)
   f<<stud[i][j][k]<<"  ";
   f<<"\n";
  }
  f<<"\n\n";
 }
 f.close();
 for(k=0;k<21;k++)
 strcpy(store[k],classes[k]);
}

void timetable::beg()
{
 clrscr();
 intro();
 info();
 mainmenu();
}

void timetable::generate()
{
 firstper12();
 practicals();
 pt();
 yoga();
 mains12();
 mains11();
 filetable();
}

void timetable::displaystud(int k)
{
 int i,j;
 cout<<"\n\n\t\t";
 char classe[6][6]={"XI-A","XI-B","XI-C","XII-A","XII-B","XII-C"};
 cout<<classe[k]<<"\n";
 char roman[9][6]={"1","2","3","4","5","6","7","8"};
 int a;
 cout<<"\t\t"<<"     ";
 for(a=0;a<9;a++)
 cout<<roman[a]<<"    ";
 cout<<"\n";
 for(i=0;i<6;i++)
 {
  cout<<"\t\t";
  for(j=0;j<9;j++)
  cout<<stud[i][j][k]<<"  ";
  cout<<"\n";
 }
}

void timetable::displayteach(int k)
{
 int i,j;
 cout<<store[k]<<"\n";
 char roman[9][6]={"1","2","3","4","5","6","7","8"};
 int a;
 cout<<"     ";
 for(a=0;a<9;a++)
 cout<<roman[a]<<"      ";
 cout<<"\n";
 for(i=0;i<6;i++)
 {
  for(j=0;j<9;j++)
  cout<<teach[i][j][k]<<"  ";
  cout<<"\n";
 }
}


void main()
{
 clrscr();
 timetable t;
 t.generate();
 t.beg();
}





