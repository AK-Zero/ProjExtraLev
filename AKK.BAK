
       #include<iostream.h>
       #include<conio.h>
       #include<stdio.h>
       #include<dos.h>
       #include<graphics.h>
       #include<process.h>
       #include<string.h>
       #include<stdlib.h>
       #include<fstream.h>

  union REGS in,out;

int callmouse()
{
  in.x.ax=1;
  int86(51,&in,&out);
  return 1;
}

void mouseposi(int &xpos,int &ypos,int &click)
{

  in.x.ax=3;
  int86(51,&in,&out);
  click=out.x.bx;
  xpos=out.x.cx;
  ypos=out.x.dx;

}

void setposi(int &xpos,int &ypos)
{
  in.x.ax=4;
  in.x.cx=xpos;
  in.x.dx=ypos;
  int86(51,&in,&out);

}

int mousehide()
{
  in.x.ax=2;
  int86(51,&in,&out);
  return 1;
}
void restrictmouseptr(int x1,int x2,int y1,int y2)
{
  in.x.ax=7;
  in.x.cx=x1;
  in.x.dx=x2;
  int86(51,&in,&out);
  in.x.ax=8;
  in.x.cx=y1;
  in.x.dx=y2;
  int86(51,&in,&out);
}

void main()
{

  clrscr();
  int x,y,cl,a,b;
  char ch;
  int g=DETECT,m;
  initgraph(&g,&m,"..\\bgi");
  setcolor(WHITE);
  line(0,75,640,75);
  line(0,74,640,74);
  line(0,73,640,73);
  line(0,72,640,72);
  line(0,71,640,71);
  setcolor(MAGENTA);
  settextstyle(0,HORIZ_DIR,3);
  outtextxy(25,20,"Beware....");
  setcolor(3);
  settextstyle(0,HORIZ_DIR,4);
  outtextxy(25,20,"Go On ....");
  setcolor(15);
  for(int r=0;r<5;r++)
 {
  rectangle(r,r,639-r,479-r);
}

  a=20;
  b=500;
  randomize();
  int z=random(16);
  setposi(a,b);
  callmouse();
  restrictmouseptr(0,630,76,470);
  float score=0;
  int x1=random(100),y1=100 , x2=400+random(180),y2=230 , x3=random(200),y3=400
    ,x4=random(200),y4=75+random(126) , x5=400+random(180),y5=75+random(125);

do
{
  setcolor(WHITE);
  line(0,75,640,75);
  line(0,74,640,74);
  line(0,73,640,73);
  line(0,72,640,72);
  line(0,71,640,71);
  setcolor(MAGENTA);
  settextstyle(0,HORIZ_DIR,3);
  outtextxy(25,20,"Beware....");
  setcolor(15);
  for(int r=0;r<5;r++)
 {
  rectangle(r,r,639-r,479-r);
}
  mouseposi(x,y,cl);

  gotoxy(36,2);
  cout<<"If U click , U won't die...";

  gotoxy(36,3);
  cout<<"But score'll increase only if U don't Click.";

  gotoxy(44,4);
  cout<<"Score :"<<(int)(score)*100;

  setcolor(LIGHTCYAN);
  rectangle(x1,y1,x1+50,y1+30);
  rectangle(x1+1,y1+1,x1+49,y1+29);
  rectangle(x1+2,y1+2,x1+48,y1+28);

  setcolor(YELLOW);
  rectangle(x2,y2,x2+30,y2+60);
  rectangle(x2+1,y2+1,x2+29,y2+59);
  rectangle(x2+2,y2+2,x2+28,y2+58);

  setcolor(12);
  rectangle(x3,y3,x3+50,y3+50);
  rectangle(x3+1,y3+1,x3+49,y3+49);
  rectangle(x3+2,y3+2,x3+48,y3+48);

  setcolor(BLUE);
  rectangle(x4,y4,x4+60,y4+30);
  rectangle(x4+1,y4+1,x4+59,y4+29);
  rectangle(x4+2,y4+2,x4+58,y4+28);

  setcolor(GREEN);
  rectangle(x5,y5,x5+30,y5+50);
  rectangle(x5+1,y5+1,x5+29,y5+49);
  rectangle(x5+2,y5+2,x5+28,y5+48);

  if(cl==0 && ((x>x1 && x<x1+50 && y>y1 && y<y1+30)||
  (x>x2 && x<x2+30 && y>y2 && y<y2+60)||(x>x3 && x<x3+50 && y>y3 && y<y3+50)
  ||(x>x4 && x<x4+60 && y>y4 && y<y4+30)||(x>x5 && x<x5+30 && y>y5 && y<y5+50)))
  {
  setcolor(WHITE);
  settextstyle(0,HORIZ_DIR,4);
  outtextxy(170,190,"Game Over...");
  settextstyle(0,HORIZ_DIR,3);
  outtextxy(40,280,"The Spirit Boxes got U...");
  delay(5000);
  ch=' ';
  }
  x1+=10;
  x2-=14;
  x3+=18;
  x4+=16;
  y4+=16;
  x5-=20;
  y5+=20;
  if(cl==0 && x!=20 && y!=500)
  score+=0.05;
  if(x1>585)
  x1=random(100);
  if(x2<30)
  x2=400+random(180);
  if(x3>585)
  x3=random(200);
  if(x4>585 || y4>500)
  {
  x4=random(200);
  y4=75+random(125);
  }
  if(x5<30 || y5>500)
  {
  x5=400+random(180);
  y5=75+random(125);
  }
  delay(100);
  cleardevice();
  if(kbhit())
  ch=getch();
}while(ch!=' ');

  mousehide();
  closegraph();
}

