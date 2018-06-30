# Chapter-7 Case Control Instructions
## [A]

      (a)  Heart
           I thought one wears a suite.
      (b)  You always lose gold prize.
      (c)  At least employees are good.
      (d)  Trapped.
      (e)  You entered a and b.
      (f)  Feeding fish
           Weeding grass
           Mending roof
           Just to survive
           
## [B]

      (a)  Expected ':' instead of ';' in case statements because with ';' case statement do not belong to any switch.
      (b)  temp cannot appean in constant expression. We can never have a variable in case statement, but the temp is there.
      (c)  Here 'a' is an float variable and we cannot test floats in switch statements.
      (d)  'a' and 'b' are not constants used in case statement.
      
## [C]

       #include<stdio.h>
       int main()
       {
         int choice,num,i,j,fact=1,isPrime=0;
         printf("Enter your choice = ");
         printf("press 1 for factorial of a number");
         printf("press 2 to check prime or not");
         printf("press 3 to check odd or even");
         scanf("%d",&choice);
         switch(choice)
         {
           case 1:
              printf("Enter a number = ");
              scanf("%d",&num);
              for(i=1;i<=num;i++)
              fact*=num;
              printf("Factorial of a number is %d",fact);
              break;
           case 2:
               printf("Enter a number = ");
               scanf("%d",&num);
               for(i=2; i<=num/2; ++i)
                {
                if(num%i==0)
                {
                   isPrime=1;
                   break;
                }
               }

              if (isPrime==0)
               printf("%d is a prime number.",num);
                  else
              printf("%d is not a prime number.",num);
                   break;
            case:3
               printf("Enter a number = ");
               scanf("%d",&num);
               if(num%2==0)
               printf("%d is odd",num);
               else
               printf("%d is even",num);
                  break;
            case:4
                 printf("Thanks for using");
                 exit(1);
                 break;
               }
               if(choice!=1 || choice!=2 || choice!=3 || choice!=4)
               printf("You entered a wrong choice. Try Again!!");
               return 0;
               }
         


     
         
