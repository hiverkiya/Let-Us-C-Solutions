# Chapter-8 Functions
## [A]
    
      (a)  Learn C
           Followed by C++, C# and Java
           (infinite times)
      (b)  100
      (c)  3.140000
      (d)  Error.
     
## [B]

      (a)  Semicolor missing in the declaration of a function.
           A function cannot return more than one values.
      (b)  message function has return type void, so it cannot be assigned to any variable.
      (c)  Function definition argument should have a datatype.
           Function is not defined before calling, or there should be prototype declaration of the function.
      (d)  Invalid use of a semicolon.
      (e)  Function definition is invalid in other functions.
      (f)  void is send in the message as argument, which is invalid.
      
## [C]

      (a)  No! There is an Invalid use of a semicolon.
      (b)
        (1)  False.
        (2)  False.
        (3)  True.
        (4)  False.
        (5)  True.
        (6)  True.
        (7)  True.
        (8)  False.
        (9)  True.
       (10)  False.
       
## [D]

(a)

        #include<stdio.h>
        int fact(int );
        int main()
        {
         int num,fac;
         scanf("%d",&num);
         fac=fact(num);
         printf("%d",fac);
         return 0;
         }
         int fact(int n)
         {
           int i,factorial=1;
           for(i=1;i<=n;i++)
           {
             factorial*=i;
           }
           return factorial;
         }
         
(b)

       #include<stdio.h>
       #include<math.h>
       int power(int,int);
       int main()
       {
         int a,b,ans;
         scanf("%d %d",&a,&b);
         ans=power(a,b);
         printf("%d",ans);
        return 0;
       }
       int power(int a,int b)
       {
         int d;
         d=pow(a,b);
         return d;
       }
     
 OR 	
 	
	#include<stdio.h>
       #include<math.h>
       int power(int,int);
       int main()
       {
         int a,b,ans;
         scanf("%d %d",&a,&b);
         ans=power(a,b);
         printf("%d",ans);
        return 0;
       }
 
 	int power(int x, int y)
	{
	int num = 1, i;
	for (i = 1; i <= y; i++)
		num = num*x;
	return(num);
	}
(c)
    
        #include<stdio.h>
    #include<conio.h>

    void rom(int);
    void print(int, char);

    int main()
    {
	int yer;

	printf("Enter the year : ");
	scanf("%d", &yer);
	printf("\nRoman equivalent of %d is : ", yer);
	rom(yer);

	getch();
	return 0;
    }

    void rom(int yer)
    {
	int v, x, l, c, d, m;

	m = yer / 1000;
	print(m, 'm');
	yer %= 1000;

	d = yer / 500;
	print(d, 'd');
	yer %= 500;

	c = yer / 100;
	print(c, 'c');
	yer %= 100;

	l = yer / 50;
	print(l, 'l');
	yer %= 50;

	x = yer / 10;
	print(x, 'x');
	yer %= 10;

	v = yer / 5;
	print(v, 'v');
	yer %= 5;

	print(yer, 'i');
    }

    void print(int a, char c)
    {
	int i;
	for (i = 0; i < a; i++)
		printf("%c", c);
    }
(d)

         #include<stdio.h>
         int calc(int );
         int main()
         {
           int year,leap;
           printf("Enter year = ");
           scanf("%d",&year);
           leap=calc(year);
           if(leap==1)
           printf("%d is leap year",year);
           else
           printf("%d is not a leap year",year);
           return 0;
         }
         int calc(int year)
         {
           if(year%4==0 || year%100==0 || year%400==0)
           return 1;
           else
           return 0;
         } 

(e)

        #include<stdio.h>
        void prime(int );
        int main()
        {
          int num;
          printf("Enter a number = ");
          scanf("%d",&num);
          prime(num);
          return(0);
        }
        void prime(int n)
        {
          int i,j,isPrime=1;
          for(i=2;i<=n;i++)
          {
            if(n%i==0)
            {  
              isPrime=1; 
             for(j=2;j<=i/2;j++)
              {
               if(i%j==0)
               {
                 isPrime=0;
                 break;
               }
              }
              if(isPrime==1)
              printf("%d\n",i);
             }
           } 
           return 0;
         }
	 
OR

	#include<stdio.h>
	#include<conio.h>
	int check_prime(int);
	void pf(int);
	int main()
	{
	int num;
	printf("Enter a number : ");
	scanf("%d", &num);
	pf(num);
	_getch();
	return 0;
	}
	void pf(int num)
	{
	int i;
	for (i = 2; num != 1; i++) //loop for obtaining the numbers.
	{
		if (num%i != 0)// If the number is not a factor
			continue;
		else
		{
        	//If the number is prime, so check if it is prime
			if(check_prime(i) == 1)
			{
				while (num%i == 0)
				{
					printf("%d, ", i);
					num /= i;
				}
			}
		}
	}
	}

	//returns 1 if prime, otherwise 0.
	int check_prime(int num)
	{
	int i = 2;
	while(i < num)
	{
		if(i%num == 0)
			return 0;
		i++;
	}
	if(i == num)
		return 1;
	}

