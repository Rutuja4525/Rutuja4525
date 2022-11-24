#include<stdio.h>
int Enqueue(int queue_arr[],int *front,int *rear,int ele,int size)
{
	if(*front==(*rear+1)%size)
	{
		printf("\nQUEUE IS FULL");
		return;
	}

	if(*front==-1 && *rear==-1)
	{
		*front=0;
		*rear=0;
		queue_arr[*rear]=ele;
	}
	else
	{
		*rear=(*rear+1)%size;
		queue_arr[*rear]=ele;
	}
}
int Dequeue(int queue_arr[],int *front,int *rear,int size)
{
	if(*front==-1 && *rear==-1)
	{
		printf("\nQUEUE IS EMPTY");
        return 1;
	}
	if(*front==*rear)
	{
		int tmp;
		tmp=queue_arr[*front];
		*front=-1;
		*rear=-1;

		return tmp;
	}
	else
	{
		int tmp=queue_arr[*front];
		*front=(*front+1)%size;

		return tmp;
	}
}
int Display(int queue_arr[],int front,int rear)
{   int i;
	for( i=front;i<=rear;i++)
	{
		printf("\n%d\t",queue_arr[i]);
	}
}
int main()
{
	int queue_arr[10];
	int max_size=5;
	int front=-1,rear=-1;
	int data,tmp,cho;
	while(1)
	{
   		printf("\nENTER THE CHOICE--->\n1.INSERT\n2.DELETE\n3.DISPLAY LIST \n4.EXIT\n");
   		scanf("%d",&cho);

   		if(cho==1)
   		{
   			printf("\nENTER THE DATA :");
           	scanf("%d",&data);
            Enqueue(queue_arr,&front,&rear,data,max_size);

		}
		else if(cho==2)
		{
			tmp=Dequeue(queue_arr,&front,&rear,max_size);
			if(tmp!=1)
			printf("%d deleted",tmp);
		}
		else if(cho==3)
		{
			Display(queue_arr,front,rear);
		}
		else if(cho==4)
		{
			return 1;
		}
	}
}
