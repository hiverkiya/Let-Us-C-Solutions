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
         
