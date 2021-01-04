# Queue-using-Array
#include<stdio.h>
#include<stdlib.h>
#include<conio.h>
#define max 10
struct queue
{int data[max];
int front, rear;
}q;
void enqueue()
{char ch='y';
printf("\n-------------------------------------------------------------");
do
{if(q.front==0 && q.rear == max-1 )
{printf("\nQueue OVERFLOW!!");
break;
}
else
{q.rear++;
printf("\nInsert Item :");
scanf("%d",&q.data[q.rear]);
}
printf("\tAdd More?? Y or N:");
ch=getch();
printf("%c",ch);
} while (ch=='y' || ch=='Y');
}
void dequeue()
{int ch='y';
printf("\n------------------------------------------------------------");
do
{if(q.front>q.rear)
{printf("\nQueue UNDERFLOW!!");
break;
}
else
{printf("\nData Deleted : %d",q.data[q.front]);
for(int i=q.front;i<=q.rear;i++)
{q.data[i]=q.data[i+1];
}
q.rear--;
}
printf("\tDelete More?? Y or N:");
ch=getch();
printf("%c",ch);
} while (ch=='y'||ch=='Y');
}
void display()
{printf("------------------------------------------------------------");
if(q.front>q.rear)
{
printf("\nEmpty Queue");
}
else
{printf("\nFront->");
for(int i=q.front;i<=q.rear;i++)
{printf("%d ",q.data[i]);
}
printf("<-rear");
}
}

int main()
{int c,size,x=1;
q.front=0; q.rear=-1;
do
{printf("\n------------------------------------------------------------\n");
printf("1.ENQUEUE(Add data)  \t2.DEQUEUE(delete data)    \t3.Display QUEUE\n4.Exit");
printf("\n\t\tEnter Choice :");
scanf("%d",&c);
switch(c)
{case 1: {enqueue(); break; }
case 2: {dequeue(); break; }
case 3: {display(); break; }
case 4: {x=0;break;exit(0);    }
default:{printf("\n\n\t\tError!!!!!"); break;}
}
}while(x);
return 0;
}
