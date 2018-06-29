# Chapter-6 More Complex Repetitions
## [A]

      (a)  prints nothing.
      (b)  1 (infinite times).
      (c)  2
           5
## [B]

      (a)  the initialization expression.
           the testing expression.
           the increasing/decreasing expression.
      (b)  a for loop.
      (c)  At least once.
      (d)  Initialization, execution of body, testing.
      (e)  3.
      (f)  Continue;
      (g)  Infinte times.
      (h)  The program will produce the output x = 10 y = 10.
           The ; after the if (x != y) would NOT produce an error.
      (i)  All things that can be done using a for loop can also be done using a while loop.
           for(; ;) implements an infinite loop.
           
## [C]

(a)

      #include<stdio.h>
      int main()
      {
        int i,j,flag;
        for(i=1;i<=300;i++)
         flag=1;
         for(j=2;j<=i/2;j++)
         {
         if(i%j==0)
         {
         flag=0;
         break;
         }
       }
       if(flag==1)
       printf("%d\n",i);
       }
       return 0;
       }
       
(b)

      #include<stdio.h>
      int main()
      {
       int i=1;
       while(i)
       {
       printf("%c",i);
       }
       return 0;
      }
      
(c)

    #include<stdio.h>
    int main()
    {
     int i,j,fact;
     float sum=0,d;
     for(i=1;i<=7;i++)
     {
       fact=1;
       for(j=1;j<=i;j++)
       {
         fact=fact*j;
       }
       d=i/fact;
       sum=sum+d;
      }
      printf("Sum of first seven terms is = %d",sum);
      return 0;
     }
     
(d)

    #include<stdio.h>

       int main()
       {
	int i,j,k;
	for(i=1;i<=3;i++)
	{
		for(j=1;j<=3;j++)
		{
			for(k=1;k<=3;k++)
			{
				if(i==j || i==k || j==k)
					continue;
				printf("%d, ", i*100+j*10+k);
			}
		}
	}
	printf("are the all possible combinations of 1,2 and 3.");
	return 0;
     }
     
(e)

(f)

      #include<stdio.h>
      int main()
      {
        int n,i,mul;
	printf("Enter a number = ");
	scanf("%d",&n);
	for(i=1;i<=10;i++)
	{
	 mul=n*i;
	 printf("%d * %d = %d\n",n,i,mul);
        } 
	return 0;
	}
	
(g)

       #include<stdio.h>
        int main()
        {
	int y;
	float x,i;
	printf("           y         x      =       i");
	
	for(y=1;y<=6;y++)
	{
		for(x=5.5;x<=12.5;x+=0.5)
		{
			i=2+(y+(x*0.5));
			printf("\n           %d     %f   =   %f", y, x, i);
			
		}
	}
	return 0;
       }
       
(h) 

            #include<stdio.h>
            #include<math.h> 
             int main()
          {
	   float i,p,q,r,n,a,d;
	 for(i=1;i<=10;i++)
	{
		printf("\n\nEnter principal, rate, time (in year) and compound interest respectively : ");
		scanf("%f %f %f %f", &p,&r,&n,&q);
		
		d=pow((1+r/q),n*q);
		a=p*b;
		
		printf("\n%f is the amount.", d);
	}
	return 0;
       }
       
(i)

           #include<stdio.h>
	   #include<math.h>
	   int main()
	   {
	      int a,x,i,j,term;
	      float sol,sum;
	      printf("Enter the value of x = ");
	      scanf("%d",&x);
	      term=(x-1)/x;
	     sum=term;
	     int power=2;
	     for(i=1;i<=6;i++)
	    {
		sol=pow(term,a)/2;
		sum=sum+sol;
		a++;
	    }
	    printf("%f is the sum of the series.\n", sum);
	       return 0;
	       }
	       
(j)

          #include<stdio.h>
         int main()
           {
	    int i, j, k;
	    for(i = 1; i <= 30; i++)
	      {
		for (j = i; j <= 30; j++)
		{
			for (k = j; k <= 30; k++)
			{
				if (i*i + j*j == k*k || j*j + k*k == i*i || i*i + k*k == j*j)
					printf("\n%d %d and %d", i, j, k);
			}
		}
	}
	printf(" are all pythogorian triplets.\n");
	return 0;
          }
	  
(k)

      #include<stdio.h>
      int main()
         {
	   int population = 100000;
	   for(int i = 0; i < 10; i++)
	{
		population = population - (population / 100) * 10;
		printf("Year %d : %d\n", 10-i, population );
	}
	return 0;
       }
       


     
	  
	  
	       
	     
