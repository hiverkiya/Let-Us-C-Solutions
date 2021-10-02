# [Chapter 3: Decision Control Instruction] Solutions

## [A]

    (a) garbage 200

    (b) 300 200

    (c) no output

    (d) x and y are equal

    (e) x=10 y=10 z=0

    (f) C is WOW

## [B]

    (a)ERROR == this is missing in if statement

    (b) NO ERROR.

    (c) NO ERROR.

    (d) There is no keyword "then" related to if in C & no variable defined here in program as well.

    (e) lvalue required as left operand of assignment.

    (f) There should be a space between else and if, as there is no "elseif" syntax in C,"else if" exists.

    (g) "&" Operator is missing before variables "a" and "b".

## [C]

(a)

    #include<stdio.h>
    int main()
    {
      float sp,cp;
      printf("Enter Cost Price and Selling Price\n");
      scanf("%f %f",&cp,&sp);
      if(sp-cp>0)
      {
         printf("Profit incurred is %f.",sp-cp);
      }
      if(sp-cp<0)
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

OR

    #include<stdio.h>;
    #include<conio.h>;
    int main()
    {
    int num;
    printf("Enter an integer : ");
    scanf("%d", &num);
    if(num%2 != 0)//odd
    printf("\n\nThe number is odd");
    else//even
    printf("\n\nThe number is even.");
    getch();
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

    #include<stdio.h>

    int main()

    {

    int leapdays,firstday,yr;

    long int normaldays,totaldays;

    printf("enter the year\n");

    scanf("%d",&yr);

    normaldays= (yr-1)*365L;

    leapdays=(yr-1)/4- (yr-1)/100+(yr-1)/400;

    totaldays=normaldays+leapdays;

    firstday=totaldays%7;

    if(firstday==0)

    printf("monday");

    if(firstday==1)

    printf("tuesday");

    if(firstday==2)

    printf("wednesday");

    if(firstday==3)

    printf("thursday");

    if(firstday==4)

    printf("friday");

    if(firstday==5)

    printf("saturday");

    if(firstday==6)

    printf("sunday");

    return 0;

    }

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

OR

    #include<stdio.h>
    #include<conio.h>
    int main()
    {
    int num,a,b,c,d,e,x;

    printf("Enter a five digit number : ");
    scanf("%d", &num);

    //separating digits of the number
    e = num % 10;
    d = (num/10) % 10;
    c = (num/100) % 10;
    b = (num/1000) % 10;
    a = (num/10000);

    //reversing the number
    x = e*10000 + d*1000 + c*100 + b*10 + a;
    printf("\n%d", x);

    if(x == num)
    	printf("\n\nThe reverse of the number %d is same as actual number.", num);

    getch();
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

OR

    #include<stdio.h>
    #include<conio.h>
    int main()
    {
    int ram,sam,ajy;

    printf("Enter the age of Ram, Shyam and Ajay respectively : ");
    scanf("%d%d%d", &ram,&sam,&ajy);

    if(ram<sam && ram<ajy)
    	printf("\n\nRam is youngest among all.");
    else if(sam<ram && sam<ajy)
    	printf("\n\nShyam is youngest among all.");
    else
    	printf("\n\nAjay is youngest among all.");

    getch();
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

OR

    #include<stdio.h>
    #include<conio.h>
    int main()
    {
    int a;

    printf("Enter any number : ");
    scanf("%d", &a);

    if(a>0)
    	printf("\n\n%d is it's absolute value.", a);
    else
    	printf("\n\n%d is it's absolute number.", -1*a);

    getch();
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

OR

    #include<stdio.h>
    #include<conio.h>
    int main()
    {
    float a,b, area, peri;

    printf("Enter the length and breadth of the rectangle : ");
    scanf("%f%f", &a,&b);

    area = a*b;
    peri = 2*a + 2*b;

    if((area > peri)
    	printf("\n\nThe area %f of the rectangle is greater than it's perimenter %f.", area,peri);
    else
    	printf("\n\nThe area %f of the rectangle is less than it's perimenter %f.", area,peri);

    getch();
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

OR

    #include<stdio.h>
    #include<conio.h>
    int main()
    {
    int x1,x2,x3,y1,y2,y3,ar;

    printf("Enter x-y coordinates of first point : ");
    scanf("%f%f", &x1,&y1);

    printf("\nEnter x-y coordinates of second point : ");
    scanf("%f%f", &x2,&y2);

    printf("\nEnter x-y coordinates of third point : ");
    scanf("%f%f", &x3,&y3);

    ar= (x1*(y2-y3) + x2*(y3-y1) + x3*(y1-y2));//condition for collinear

    if(!ar)
    	printf("\n\nThe points are collinear.");
    else
    	printf("\n\nThe points are not collinear.");

    //To check there's is an example (0, -2) , (2, 4) and (-1, -5).

    getch();
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

OR

    #include<stdio.h>
    #include<conio.h>
    int main()
    {
    float r,x,y;

    printf("Enter the radius of the circle : ");
    scanf("%f", &r);

    printf("\n\nEnter the x-y coordinates of the point for checking it's position : ");
    scanf("%f%f", &x,&y);

    if(r > sqrt(pow(x,2) + pow(y,2)))
    	printf("\n\nThe pints lie inside the circle.");
    else if(r == sqrt(pow(x,2) + pow(y,2)))
    	printf("\n\nThe points lie on the circle.");
    else
    	printf("\n\nThe points lie outside the circle.");

    getch();
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

OR

    #include<stdio.h>
    #include<conio.h>
    int main()
    {
    float x,y;

    printf("Enter the x-y coordinates of the point : ");
    scanf("%f%f", &x,&y);

    if(x==0 && y==0)
    	printf("\n\nThe point is on the origin.");
    if(x==0 && y!=0)
    	printf("\n\nThe point lie on the y-axis");
    if(x!=0 && y==0)
    	printf("\n\nThe points lie on the x-axis");
    if(x!=0 && y!=0)
    	printf("\n\nThe points lie on the plane");

    getch();
    return 0;
    }
