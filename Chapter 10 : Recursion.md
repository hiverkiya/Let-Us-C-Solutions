# [Chapter 10: Recursion ] Solutions

## [A]
  
    (a) Infinite Print C adds wings to your thoughts.
    (b) C adds wings to your thoughts.
  
## [B]

   (a) 
   (b) 
        
       int func(int num);
        #include <stdio.h>
      int main()
    {   int number;

    printf("Enter number\n");
    scanf("%d",&number);
    func(number);
    return 0;
      }
      int func(int num)
      {
    int i;
    for(i=2;i<=num;i++)
    {
        if(num%i==0)
        {
            printf("%d\n",i);
            func(num/i);
            break;
        }
    }
    return 0;
    }
   (c)
   (d)
   
   (1) Without Recursion 
   
    
   
   (2) With recursion
          
          #include<stdio.h>
      int bin(int);
      int main()
      {   int number;
    printf("Enter number\n");
    scanf("%d",&number);
    bin(number);
    return 0;
      }
      int bin(int number)
        {
    if(number>1)
    {
        bin(number/2);
    }
    printf("%d",number%2);

    return 0;
    }
   (e)
   
