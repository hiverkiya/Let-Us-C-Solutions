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
       
(c)

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
             for(j=2;j<=n/2;j++)
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
