# [Chapter-7 Case Control Instructions] Solutions

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

    (a) Expected ':' instead of ';' in case statements because with ';' case statement do not belong to any switch.
     
    (b) temp can't appear in constant expression.We can never have a variable in case statement,but temp is there.
     
    (c) Here 'a' is an float variable and we cannot test floats in switch statements.
     
    (d) 'a' and 'b' are not constants used in case statement.
      
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
         
   OR
   
      #include<stdio.h>
      #include<conio.h>
      int main()
      {
    int a,x,num,p,fact,prm;
    for(a=2;a>1;a++)
    {
        printf("\n\nEnter what your choice.\n");
        printf("\n\n1. Find factorial.");
        printf("\n\n2. Check Prime number.");
        printf("\n\n3. Check even and odd.\n\n4. Exit.\n");
        scanf("%d", &x);
        switch(x)
        {
        case(1):
            printf("Enter the number of what you want to find the factorial :");
            scanf("%d", &num);
            fact=num;
            for(p=1;p<num;p++)
                fact=fact*p;
            printf("%d is the factorial.", fact);
            break;
            
        case(2):
            printf("Enter the number which you want to check whether it is prime or not : ");
            scanf("%d", &num);
            for(;p<num;p++)
            {
                prm=num%p;
                if(prm==0)
                {
                    printf("%d is not a prime number.", num);
                    break;	
                }
                if(p==num-1)
                    printf("%d is a prime number.", num);
            }
            break;
            
        case(3):
            printf("Enter the number to check whether it is even or odd : ");
            scanf("%d", &num);
            if(num%2==0)
                printf("%d is an even number.", num);
            else
                printf("%d is odd odd number.", num);
            break;
    	}
            
            if(x==4)
            {
                printf("\n\nOk Thank you for using this program.\n\n Bye.\n\n Exiting.");
                break;
            }
            if(x!=1 && x!=2 && x!=3 && x!=4)
                printf("You have entered the wrong choice. Try Again!!");
    }
    getch();
    return 0;
    }

## [D]

          #include<stdio.h>
          int main()
          {
            int class,fail;
            printf("Enter the class = ");
            scanf("%d",&class);
            printf("Enter the number of subjects student got failed = ");
            scanf("%d",&fail);
            switch(class)
            {
              case 1:
                switch(fail)
                {
                  case 0:
                  case 1:
                  case 2:
                  case 3:
                    printf("You've got grace of 5 marks per subject");
                    break;
                   default:
                   printf("You didn't got any grace");
                   break;
                 }
                 break;
               case 2:
                 switch(fail)
                 {
                   case 0:
                   case 1:
                   case 2:
                   printf("You've got grace of 4 marks per subject");
                   break;
                   default:
                   printf("You didn't got any grace");
                   break;
                  }
                  break;
               case 3:
                  switch(fail)
                  {
                   case 0:
                   case 1:
                   printf("You've got grace of 3 marks per subject");
                   break;
                   default:
                   printf("You didn't got any grace");
                   break;
                   }
                   break;
                   default:
                   printf("Wrong Choice. Please try again!!");
                   break;
                  }  
                  return 0;
                  }


     
         
