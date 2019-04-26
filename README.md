# DK
Game
#include <iostream>
#include<stdlib.h>

using namespace std;
  void display();
  void yourturn();
    bool gameover();
  char a[3][3]={{'1','2','3'},{'4','5','6'},{'7','8','9'}};
  int choice;
  char turn = 'O';
  int row,coloum;
  int main()
  {
      while(gameover()){
    display();
    yourturn();
    display();

    }

    if(turn=='X')
        cout<< "Player 1[O] won the game,!!! "<<endl;
     if(turn=='O')
        cout<<"Player 2[X] won the game!!!"<<endl;




    return 0;

}
   void display()
{
     system("cls");
    cout<< "\n\t\t\tWelcome To Tic Tac Toe game"<<endl;


    cout << "\n\t\tPLAYER 1[0] "<<endl;
    cout << "\t\tPLAYER 2[x] "<<endl;
    cout<<"\n\t\t"<< " \t\t|"<<"\t\t|"<<endl;
    cout<<"\t\t"<< " \t\t|"<<"\t\t|"<<endl;
    cout<<"\t\t"<<a[0][0]<< " \t\t|"<<"\t"<<a[0][1]<<"\t|"<<"\t"<<a[0][2]<<endl;
    cout<<"\t\t"<< " \t\t|"<<"\t\t|"<<endl;
    cout<<"\t\t"<< " \t\t|"<<"\t\t|"<<endl;
    cout<<"\t\t     -----------|---------------|-------"<<endl;
    cout<<"\t\t"<< " \t\t|"<<"\t\t|"<<endl;
     cout<<"\t\t"<<a[1][0]<< " \t\t|"<<"\t"<<a[1][1]<<"\t|"<<"\t"<<a[1][2]<<endl;
    cout<<"\t\t"<< " \t\t|"<<"\t\t|"<<endl;
    cout<<"\t\t----------------|---------------|-------"<<endl;
    cout<<"\t\t"<< " \t\t|"<<"\t\t|"<<endl;
    cout<<"\t\t"<<a[2][0]<< " \t\t|"<<"\t"<<a[2][1]<<"\t|"<<"\t"<<a[2][2]<<endl;
    cout<<"\t\t"<< " \t\t|"<<"\t\t|"<<endl;



}
    void yourturn()
    {

       if (turn =='O')
       {
         cout<< "\n\t\tPlayer 1[0]:";
       }
        else if (turn == 'X')
       {
         cout<< "\n\t\tPlayer 2[X]:";
         }
         cin>>choice;


     switch(choice){
     case 1:row=0;coloum=0;break;
     case 2:row=0;coloum=1;break;
     case 3:row=0;coloum=2;break;
     case 4:row=1;coloum=0;break;
     case 5:row=1;coloum=1;break;
     case 6:row=1;coloum=2;break;
     case 7:row=2;coloum=0;break;
     case 8:row=2;coloum=1;break;
     case 9:row=2;coloum=2;break;
     default:
     cout<< "Invalid Choice"<<endl;break;
     }
     if (turn =='O' && a[row][coloum]!='X' && a[row][coloum]!='O')
     {

         a[row][coloum]='O';
         turn='X';
         }
     else if(turn=='X' && a[row][coloum]!='X' && a[row][coloum]!='O')
     {
          a[row][coloum]='X';
          turn='O';

     }
     else{
        cout<< "\n\t\tbox already filled \n\t\t Try Again."<<endl;
        yourturn();
     }
     }

     bool gameover()
     {
          for(int i=0;i<3;i++)
         {
              if(a[i][0] ==a[i][1]&& a[i][0] ==a[i][2]||a[0][i] ==a[1][i]&& a[0][i] ==a[2][i])
                return false;}
           if(a[0][0] ==a[1][1]&& a[0][0] ==a[2][2]||a[0][2] ==a[1][1]&& a[0][2] ==a[2][0])
           return false;



             for(int i=0;i<3;i++)
             for(int j=0;j<3;j++){
             if( a[i][j] != 'X'&& a[i][j] != 'O')
             return true;}
     }
