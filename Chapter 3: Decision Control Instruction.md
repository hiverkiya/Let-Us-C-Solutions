## [A]
    
    (a) 0 200
    (b) 300 200
    (c) NO OUTPUT
    (d) x and y are equal
    (e) x=10 y=10 z=0 
    (f) C is WOW

## [B]

    (a) If will be always true as we are assigning value of a to b,so condition checking becomes unnecessary.
    (b) There is no need to insert extra braces inside if block.
    (c) NO ERROR.
    (d) There is no syntax "then" related to if in C Programmming Language.
    (e) lvalue required as left operand of assignment.
    (f) There should be a space between else and if, as there is no "elseif" syntax in C,"else if" exists.
    (g) "&" Operator is missing.
    
##  [C]

   (a)
        
    #include<stdio.h>
    int main()
    {
      float sp,cp;
      printf("Enter Cost Price and Selling Price\n");
      scanf("%f %f",&cp,&sp);
      if(sp>cp)
      {
         printf("Profit incurred is %f.",sp-cp);
      }
      if(cp>sp)
        {
          printf("Loss incurred is %f",cp-sp);
         }
    return 0;
    }
  (b)
    
    #include<stdio.h>
    int main()
    {
     printf("Enter number\n");
     int number;
     scanf("%d",&number);
      if(number%2==0)
     {
     printf("Number is Even");
     }
     else
     {
     printf("Number is Odd");
     }
     return 0;
    }
(c)

(d)

(e)

    #include<stdio.h>
    #include<math.h>
    int main()
    {
      printf("Enter number\n");
      int number;
      scanf("%d",&number);
      int temp=number;
      int length_of_number=5;
      int reverse=0,remainder=0;
      while(number!=0)
     {
      length_of_number--;
      remainder=number%10;
      reverse=reverse+remainder*pow(10.0,length_of_number);
      number/=10;
    }
    printf("Reverse of number %d is %d\n",temp,reverse);
    if(temp==reverse)
    {
    printf("Reverse and Original Number are Equal\n");
    }
     else
    {
    printf("Reverse and Original Number are not Equal");
    }
    return 0;
    }
(f)

    #include<math.h>
    #include<stdio.h>
    int main()
    {
    printf("Enter ages of Ram,Shyam and Ajay.\n");
    int age1,age2,age3;
    scanf("%d %d %d",&age1,&age2,&age3);
    int youngest;
    youngest=age1<age2?(age1<age3?age1:age3):(age2<age3?age2:age3);
    if(youngest==age1)
    {
    printf("Ram is Youngest.");
    }
    else if(youngest==age2)
    {
    printf("Shyam is Youngest.");
    }
    else if(youngest==age3)
    {
    printf("Ajay is Youngest.");
    }
    return 0;
    }
(g)

    #include<stdio.h>
    int main()
    {
    int angle1,angle2,angle3;
    printf("Enter the angles of Triangle in any order in Degrees.\n");
    scanf("%d %d %d",&angle1,&angle2,&angle3);
    if(angle1+angle2+angle3==180)
    {
    printf("Triangle is Valid.");
    }   
    else
    {
    printf("Triangle is Invalid.");
    }
    return 0;
    }
(h)

    #include<math.h>
    #include<stdio.h>
    int main()
    {
    printf("Enter number\n");
    int number;
    scanf("%d",&number);
    printf("Absolute value of %d is %d.",number,abs(number));
    return 0;
    }
(i) 

(j)

(k)

(l)
