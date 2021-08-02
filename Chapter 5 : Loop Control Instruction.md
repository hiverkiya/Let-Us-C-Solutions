# Chapter-5 Loop Control Instruction
## [A]

      (a)   No Output since ';' is used after while 
      
      (b)   2 3 3
      
      (c)   3 3 1
      
      (d)   prints it infnite times.
      
      (e)   prints 10 infinite times.
      
      (f)   prints nothing.
       
## [B]

   (a)
       
        #include<stdio.h>
         int main()
           {
	      int i,hour, extra;
	      for(i = 1 ; i <= 10 ; i++) 
	       {
              printf("\n");
		printf("Enter the working hour of the employ : ");
		scanf("%d", &hour);
		
		if(hour>40)
		{
			extra = (hour - 40)*12;
			printf("\n%d Rs. is the overtime pay of employee\n", extra);
		}
		else
			printf("\nThis employ has not done overtime.\n");
	  }
	 return 0;
         }
         
   (b)
   
          #include<stdio.h>
          int main()
          {
             int i,fact=1,num;
             scanf("%d",&num);
             printf("Ener a number = ");
             for(i=1;i<=num;i++)
             {
               fact*=num;
              }
              printf("%d",fact);
              return 0;
           }
           
   (c)
   
          #include<stdio.h>
          #include<math.h>
          int main()
          {
            int base,power,d;
            print("Enter value of base = ");
            scanf("%d",&base);
            printf("Enter value of power = ");
            scanf("%d",&power);
            d=pow(base,power);
            printf("%d",d);
            return 0;
          }
           
   (d)
   
           #include<stdio.h>
           int main()
           {
             int i;
             for(i=0;i<=255;i++)
             printf("\n%d = %c",i,i);
             return 0;
           }
           
   (e)
   
           #include<stdio.h>
          int main()
          {
          int i,rem,num=0,x;
          for(i=1;i<=500;i++)
          {
          	num=0;
           x=i;
            while(x)
            {
              rem=x%10;
              num=num+(rem*rem*rem);
              x/=10;
             }
            if(num==i)
            printf("%d is a armstrong number\n",i);
           }
           return 0;
           }
	   
   (f)
   	
	#include<stdio.h>
	main()
	{

	int matchsticks=21, user, computer;

	printf("Do not enter Invalid Numbers.\nNumbers above 4 are invalid.");

	printf("\nIf you do so, the computer automatically wins.");

	while (matchsticks>=1)
	{

	printf("\nNumber of matchsticks available right now is %d.", matchsticks);

	printf("\n\nYour Turn...\n\n\n");

	printf("\nPick up the matchstick(s)-- (1-4): ");
	scanf ("%d", &user);

	if (user>4)

	{
	printf("Invalid Selection"); 
	break;
	}

	computer=5-user;

	printf("\nComputer's Turn..\n" );
	printf("\nComputer chooses:%d", computer);
	
	matchsticks=matchsticks-user-computer;
	continue;

	if(matchsticks==1)

	break;
	}

	matchsticks--;
	printf("\nComputer Wins");

	}

 OR
 	
	#include
	#include
	void main()
	{

	int matchsticks=21, user, computer;
	clrscr();
	printf("Do not enter Invalid Numbers.\nNumbers above 4 are invalid.");

	printf("\nIf you do so, the computer automatically wins.");

	while (matchsticks>=1)
	{

	printf("\nNumber of matchsticks available right now is %d.", matchsticks);

	printf("\n\nYour Turn...\n\n\n");

	printf("\nPick up the matchstick(s)-- (1-4): ");
	scanf ("%d", &user);

	if (user>4)

	{
	printf("Invalid Selection");
	break;
	}

	computer=5-user;

	printf("\nComputer's Turn..\n" );


	if(matchsticks==1)

	break;
	printf("\nComputer chooses:%d", computer);
	matchsticks=matchsticks-user-computer;
	continue;

	}

	matchsticks--;
	printf("\nComputer Wins");
	getch();
	}
   (g)
         
	 #include<stdio.h>
	 int main()
	 {
	 int num,pos=0,neg=0,zero=0,choice;
	  do
	  {
	    scanf("%d",&num);
	    if(num==0)
	    zero++;
	    else if(n<0)
	    neg++;
	    else if(n>0)
	    pos++;
	    printf("Do you want to enter another number? (Enter 1 for yes & 0 for no)");
	    scanf("%d",&choice);
	   }while(choice);
	   printf("Zeroes = %d\n",zero);
	   printf("Negatives = %d\n",neg);
	   printf("Positives = %d\n",pos);
	   return 0;
	   }

   (h)
   
        #include<stdio.h>
	int main()
	{
	  int num,rem,oct=0,rev=0,rem1;
	  scanf("%d",&num);
	  while(num)
	  {
	    rem=num%8;
	    oct=10*oct+rem;
	    num/=8;
	  }
	  while(oct)
	  {
	   rem1=oct%10;
	   rev=rev*10+rem1;
	   oct/=10;
	   }
	     printf("%d is octal equivalent",rev);
	    return 0;
	    }
	
 OR
 	
	#include<stdio.h>
	int main()
	{   int number;
    printf("Enter Number\n");
    scanf("%d",&number);
    printf("Octal equivalent is %o",number);
    return 0;
	}
  
  (i)
   
        #include<stdio.h>
        int main()
        {
	int i,num,max,min, N, range;
	
	printf("Enter how many number you want to enter : ");
	scanf("%d", &N);
	
	printf("Enter the number : ");
	scanf("%d", &num);
	
	max=min=num;
	
	for( i = 1; i < N; i++)
	{
		printf("Enter the number : ");
		scanf("%d", &num);
		if(num>max)
			max=num;
		if(num<min)
			min=num;
	}
	range = max - min;
	
	printf("\n%d is the range of the data.", range);
	return 0;
     }
            
	 
