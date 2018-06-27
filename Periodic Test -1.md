## [A]
  
    (1) i+1
    (2) Real
    (3) ; (Statement Terminator)
    (4) 2 or 4 bytes
    (5) Do-while

## [B]
   
    (1) True
    (2) True
    (3) False
    (4) True
    (5) False

## [C]

    (a) 5 5 6
    (b) 65 A
    (c) 2 1
    (d) 21525
    (e) 0 1
 
## [D] 

    (a) Syntax of logical connectives is incorrect.
    (b) "then" is not any type of syntax in C language.
    (c) Parentheses should be used in conditional operators to specify the associativity of operations.
    (d) NO ERROR
    (e) NO ERROR

## [E]

   (1) 
    
     #include <stdio.h>
      int fact (int);
      int main()
      {
        long int sum=0;
        int i;  
        for(i=1;i<=9;i++)
          {
            sum+=(fact(i)*fact(i+1)); 
          }
        printf("%ld",sum);
        return 0;
      }
       int fact(int fact)
      {
        int result=1,i;
        for(i=1;i<=fact;i++)
       {
        result*=i;
        }
        return result;
      }
      
   (2)
      
        #include<stdio.h>
    int main()
    {
     int cp=0,cn=0,cz=0,number;
    char another='y';
    while(another=='y')
    {
        scanf("%d",&number);
        
        if(number<0)
        {
            cn++;
        }
         if(number>0)
        {
            cp++;
        }
         if(number==0)
        {
            cz++;
        }
        
        printf("Enter Another Number y/n ?\n");
        fflush (stdin);
        scanf(" %c",&another);
    }
    printf("Number of Positives = %d\n",cp);
    printf("Number of Negatives = %d\n",cn);
    printf("Number of Zeroes = %d\n",cz);
    return 0;
     }
  (3)

    #include<stdio.h>
    int main()
    {   
     int size,i;
     printf("Enter number of elements you want to Enter\n");
     scanf("%d",&size);
      int array[size];
     printf("Enter Elements now \n");
     for(i=0;i<size;i++)
     {
         scanf("%d",&array[i]);
      }
     int large=array[0],small=array[0];
        for(i=1;i<size;i++)
         {
           if(array[i]>large)
          {
              large=array[i];
          }
         if(array[i]<small)
          {
             small=array[i];
          }
      }
    printf("The Largest Number is %d and Smallest Number is %d.\n",large,small);
    printf("The Range is %d",large-small);
    return 0;
    }
  
  (4)
    
     #include<stdio.h>
    int main()
    {
     int num1,num2,num3;
     printf("Enter Numbers one by one.\n");
     scanf("%d %d %d",&num1,&num2,&num3);
     int smallest,largest,sum=0,middle;
     sum=num1+num2+num3;
     smallest=num1<num2?(num1<num3?num1:num3):(num2<num3?num2:num3);
     largest=num1>num2?(num1>num3?num1:num3):(num2>num3?num2:num3);
     middle=sum-smallest-largest;
     if((largest*largest)==(smallest*smallest)+(middle*middle))
     {
          printf("Entered Numbers are Pythagorean triplet.\n");
      }
      else
     {
         printf("Entered Numbers are not Pythagorean triplet.\n");
     }
     return 0;
    }
       
