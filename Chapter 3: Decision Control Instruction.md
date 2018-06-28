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

    #include <stdio.h>

    int main()
    {
      int year;

    printf("Enter a year: ");
    scanf("%d",&year);

    if(year%4 == 0)
    {
        if( year%100 == 0)
        {
            // year is divisible by 400, hence the year is a leap year
            if ( year%400 == 0)
                printf("%d is a leap year.", year);
            else
                printf("%d is not a leap year.", year);
        }
        else
            printf("%d is a leap year.", year );
    }
    else
        printf("%d is not a leap year.", year);
    
    return 0;
    }

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

    #include <stdio.h>
    int main()
    {
    int l,b;
    printf("Enter length and breadth of rectangle\n");
    scanf("%d %d",&l,&b);
    if((l*b)>(2*(l+b)))
    {
        printf("Area is Greater than perimeter\n");
    }
    else
    {
        printf("Area is not Greater than perimeter\n");
    }
    return 0;
    }

(j)

    #include <stdio.h>
    int main()
    {
     float x1,y1,x2,y2,x3,y3;
    printf("Enter coordinates (x1,y1)\n");
    scanf("%f %f",&x1,&y1);
    printf("Enter coordinates (x2,y2)\n");
    scanf("%f %f",&x2,&y2);
    printf("Enter coordinates (x3,y3)\n");
    scanf("%f %f",&x3,&y3);
    if((y2-y1)/(x2-x1)==(y3-y1)/(x3-x1))
    {
        printf("Point lies on straight line");
    }
    else
    {
        printf("Points don't lie on straight line");
    }
    return 0;
    }

(k)

    #include<stdio.h>
    int main()
    {
        float cen_x,cen_y,rad,x,y,d;
        printf("Enter Center x,y coodinate and radius\n");
        scanf("%f %f %f",&cen_x,&cen_y,&rad);
        printf("Enter coordinates of point\n");
        scanf("%f %f",&x,&y);
        d=sqrt(pow((cen_x-x),2.0)+pow((cen_y-y),2.0));
        if(d<rad)
         {
            printf("Point is inside circle\n");
         }
        else if(d==rad)
     {
            printf("Point is on the circle\n");
     }
     else if(d>rad)
     {
             printf("Point is outside the circle\n");
     }
     return 0;
    }
(l)

    #include<stdio.h>
    int main()
    {
     float x,y;
     printf("Enter Coordinates\n");
     scanf("%f %f",&x,&y);
     if(x==0.0&&y==0.0)
    {
        printf("Point lies on origin\n");
    }
     else if (x==0.0&&y>0.0)
    {
        printf("Point lies on y-axis\n");
    }
     else if(y==0.0&& x>0.0)
    {
        printf("Point lies on x-axis\n");
    }
    return 0;
    }
