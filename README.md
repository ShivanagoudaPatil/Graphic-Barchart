# Graphic-Barchart
#include <GL/freeglut.h>
#include <GL/glut.h>
#include <GL/gl.h>
#include <stdio.h>
#include<stdlib.h>
#include <math.h>


int x11,x12,x13,x14,x15,x16;
float a[10];
void ddaline2(int x1,int y1,int x2,int y2);
void drawline()
{
//to drwaw x and y axis
ddaline2(0,0,380,0);
ddaline2(0,0,0,390);
//to draw arrow for x axis
ddaline2(380,0,370,15);
ddaline2(380,0,370,-15);
//to draw arrow for y axis
ddaline2(0,390,-10,380);
ddaline2(0,390,10,380);
}
void ddaline(int x1,int y1,int x2,int y2,float a[])
{
   int s,m,dx,dy;
   float xi,yi,x,y;

   dx=x2-x1;
   dy=y2-y1;
  
  if(abs(dx)>abs(dy))
    s=abs(dx);
  else
    s=abs(dy);

  x=x1;
  y=y1;

  xi=dx/(float)s;
  yi=dy/(float)s;

  glPointSize(50.0);
  glBegin(GL_POINTS);
  glColor3fv(a);
  glVertex2i(x1,y1);

  for(m=0;m<s;m++)
  {
    x=x+xi;
    y=y+yi;
    glVertex2f(x,y);
  }
 glEnd();
 glFlush();
}

void ddaline2(int x1,int y1,int x2,int y2)
{
   int s,m,dx,dy;
   float xi,yi,x,y;

   dx=x2-x1;
   dy=y2-y1;
  
  if(abs(dx)>abs(dy))
    s=abs(dx);
  else
    s=abs(dy);

  x=x1;
  y=y1;

  xi=dx/(float)s;
  yi=dy/(float)s;

  glPointSize(5.0);
  glBegin(GL_POINTS);
  glColor3fv(a);
  glVertex2i(x1,y1);

  for(m=0;m<s;m++)
  {
    x=x+xi;
    y=y+yi;
    glVertex2f(x,y);
  }
 glEnd();
 glFlush();
}

void name()
{
glColor3f(1.0,1.0,1.0);
                glRasterPos2i(50,380);
                glutBitmapString(GLUT_BITMAP_TIMES_ROMAN_24, (const unsigned char*)"YEAR   V/S   POPULATION   GRAPH");

                glRasterPos2i(20,-10);
                glutBitmapString(GLUT_BITMAP_HELVETICA_10, (const unsigned char*)"2011");
                glRasterPos2i(70,-10);
                glutBitmapString(GLUT_BITMAP_HELVETICA_10, (const unsigned char*)"2012");
                glRasterPos2i(120,-10);
                glutBitmapString(GLUT_BITMAP_HELVETICA_10, (const unsigned char*)"2013");
                glRasterPos2i(170,-10);
                glutBitmapString(GLUT_BITMAP_HELVETICA_10, (const unsigned char*)"2014");
                glRasterPos2i(220,-10);
                glutBitmapString(GLUT_BITMAP_HELVETICA_10, (const unsigned char*)"2015");
                glRasterPos2i(270,-10);
                glutBitmapString(GLUT_BITMAP_HELVETICA_10, (const unsigned char*)"2016");


                glRasterPos2i(-20,80);
                glutBitmapString(GLUT_BITMAP_HELVETICA_10, (const unsigned char*)"20 lakh");
                glRasterPos2i(-20,135);
                glutBitmapString(GLUT_BITMAP_HELVETICA_10, (const unsigned char*)"40 lakh");
                glRasterPos2i(-20,190);
                glutBitmapString(GLUT_BITMAP_HELVETICA_10, (const unsigned char*)"60 lakh");
                glRasterPos2i(-20,245);
                glutBitmapString(GLUT_BITMAP_HELVETICA_10, (const unsigned char*)"80 lakh");
                glRasterPos2i(-20,295);
                glutBitmapString(GLUT_BITMAP_HELVETICA_10, (const unsigned char*)"1 crore");
                glRasterPos2i(-20,345);
                glutBitmapString(GLUT_BITMAP_HELVETICA_10, (const unsigned char*)"1.2 crore");
                





glRasterPos2i(350,340);
                glutBitmapString(GLUT_BITMAP_HELVETICA_10, (const unsigned char*)"Y-Axis : population");
                glRasterPos2i(350,350);
                glutBitmapString(GLUT_BITMAP_HELVETICA_10, (const unsigned char*)"X-Axis : year");


}

void bar()
{
 int i=0,j=0,x111,x122,x133,x144,x155,x166;
char d[10];
//colors for bar
float c1[3]={0.0,1.2,0.0};
float c2[3]={1.0,0.0,1.0};
float c3[3]={1.0,1.0,0.0};
float c4[3]={0.0,0.0,0.8};
float c5[3]={0.0,1.0,1.0};
float c6[3]={0.2,0.2,0.3};

i=20;
j=20;
x111=x11;
x11=(x11/40000);
       ddaline(i,j,i,j+x11,c1);

sprintf(d,"%d",x111);
	glRasterPos2i(10,j+x11+20);
        glutBitmapString(GLUT_BITMAP_HELVETICA_18, (const unsigned char *)d);

i=70;
j=20;    
x122=x12;
x12=(x12/40000);
ddaline(i,j,i,j+x12,c6); 

sprintf(d,"%d",x122);
	glRasterPos2i(60,j+x12+20);
        glutBitmapString(GLUT_BITMAP_HELVETICA_18, (const unsigned char *)d);

  
i=120;
j=20;
x133=x13;
x13=(x13/40000);
ddaline(i,j,i,j+x13,c2);
sprintf(d,"%d",x133);
	glRasterPos2i(110,j+x13+20);
        glutBitmapString(GLUT_BITMAP_HELVETICA_18, (const unsigned char *)d);

i=170;
j=20;
x144=x14;
x14=(x14/40000);
ddaline(i,j,i,j+x14,c3);
sprintf(d,"%d",x144);
	glRasterPos2i(160,j+x14+20);
        glutBitmapString(GLUT_BITMAP_HELVETICA_18, (const unsigned char *)d);

i=220;
j=20;
x155=x15;
x15=(x15/40000);
ddaline(i,j,i,j+x15,c4);
sprintf(d,"%d",x155);
	glRasterPos2i(210,j+x15+20);
        glutBitmapString(GLUT_BITMAP_HELVETICA_18, (const unsigned char *)d);


i=270;
j=20;
x166=x16;
x16=(x16/40000);
ddaline(i,j,i,j+x16,c5);
sprintf(d,"%d",x166);
	glRasterPos2i(260,j+x16+20);
        glutBitmapString(GLUT_BITMAP_HELVETICA_18, (const unsigned char *)d);


 glFlush();
}
void display()
{
name();
drawline();
bar();
}


void Init()
{
 glClearColor(0.2,0.0,0.2,1.0);
 glClear(GL_COLOR_BUFFER_BIT);
 gluOrtho2D(-30.0,400.0,-30.0,400.0);
}


int main(int argc,char **argv)
{
printf("enter population for 2011:\t");
scanf("%d",&x11);
printf("enter population for 2012:\t");
scanf("%d",&x12);
printf("enter population for 2013:\t");
scanf("%d",&x13);
printf("enter population for 2014:\t");
scanf("%d",&x14);
printf("enter population for 2015:\t");
scanf("%d",&x15);
printf("enter population for 2016:\t");
scanf("%d",&x16);

glutInit(&argc,argv);
 glutInitDisplayMode(GLUT_SINGLE|GLUT_RGB);
 glutInitWindowSize(1100,640); 
 glutInitWindowPosition(30,30);
 glutCreateWindow("POPULATION GROWTH");
 Init();
 glutDisplayFunc(display);
 glutMainLoop();
 return 0;
}
