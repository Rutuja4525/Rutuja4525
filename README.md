#include<stdio.h>
#include<string.h>
int bin[100];
void fill(int bin[],int start,int end,int temp)
{
   int rem,i;
//printf("Start = %d end = %d temp = %d",start,end,temp);
   int e = end;
   while(temp > 0)
  {

    rem = temp % 2;
    bin[end] = rem;
    end--;
    temp = temp / 2;
   }

for(i=start;i<=e;i++)
printf("%d ",bin[i]);

}


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
int main()
    {
char ip[15],i,j;
int chance = 0;
printf("\n Enter IP Address : ");
gets(ip);
int len=strlen(ip);
int temp=0,flag=0,first,k=0;

for(i=0;i<32;i++)
                  bin[i] = 0;

for(i=0;i<=len;i++)
   {
                 if(ip[i]=='.' || i==len)
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
                         if(chance == 0)
                        {
                           fill(bin,0,7,temp);
                           printf(".");
                        }

                         else if(chance == 1)
                        {
                           fill(bin,8,15,temp);
                           printf(".");
                        }
                         else if(chance == 2)
                        {
                           fill(bin,16,23,temp);
                           printf(".");
                        }
                         else if(chance == 3)
                        {
                           fill(bin,24,31,temp);
                        }
                    temp=0;
                    chance++;

}
else

{

temp = temp*10 + fun(ip[i]);

}

}
if(bin[0]==0)
printf("\n Class A");

else if(bin[0]==1 && bin[1]==0)
printf("\n Class B");

else if(bin[0]==bin[1]==1 && bin[2]==0)
printf("\n Class C");

else if(bin[0]==bin[1]==bin[2]==1 && bin[3]==0)
printf("\n Class D");

else if(bin[0]==bin[1]==bin[2]==bin[3]==1)
printf("\n Class E");

}
