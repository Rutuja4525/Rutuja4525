#include<stdio.h>
#include<string.h>
int fun(char ch)
{
if(ch=='1')
return 1;
else if(ch=='2')
return 2;
else if(ch=='3')
return 3;
else if(ch=='4')
return 4;
else if(ch=='5')
return 5;
else if(ch=='6')
return 6;
else if(ch=='7')
return 7;
else if(ch=='8')
return 8;
else if(ch=='9')
return 9;
else if(ch=='0')
return 0;
}
int check(int temp)
{
	if(temp>255)
		return 0; //incorrect
	return 1; //correct
}
int checkclass(int temp)
{
	if(temp>=0 && temp<=127)
		return 1;
	else if(temp>=127 && temp<=191)
		return 2;
		else if(temp>=192 && temp<=223)
		return 3;
		else if(temp>=224 && temp<=239)
		return 4;
		else if(temp>=240 && temp<=255)
		return 5;

}
int main()
{
	char ip[15];
	printf("\n Enter IP Address : ");
	gets(ip);
	int len=strlen(ip);
	int temp=0,flag=0,first,i,cls;
	
	for(i=0;i<=len;i++)
    {
    	if(ip[i]=='.'|| i==len)
    	{
    		if(check(temp)==0)
        	{
            	printf("\n INVALID IP ");
                return;					 		
			}
            if(flag==0)
            {
              	first=temp;
                flag=1;
            }
            temp=0;
    	}
    	else
    	{
    		temp=temp*10+fun(ip[i]);
		}
	}
	if(flag==1)
	{
		cls=checkclass(first);
		if(cls==1)
			printf("\n Class A");

		else if(cls==2)
			printf("\n Class B");

		else if(cls==3)
			printf("\n Class C");

		else if(cls==4)
			printf("\n Class D");

		else if(cls==5)
			printf("\n Class E");

	}
}
    
