# Chapter-2 Instructions

## [A]

    (a) Valid.

    (b) Valid.

    (c) "char" is a keyword and we cannot use keyword as a variable.

    (d) lvalue required,as we cannot take any expression on LHS.

    (e) a3 doesn't specify any operation.

    (f) Valid.

    (g) Valid.

    (h) spaces are not allowed in variable names.

    (i) Valid.

    (j) "?"(symbol) is not any valid operator.

    (k) lavlue required as LHS should not have any constant value or any expression.

    (l) Valid.

    (m) Length of character is one.

## [B]

    (a) -84

    (b)  4

    (c) INFINITE

    (d) 23.750000

## [C]

Operators are performed from LHS in the given expressions.

    (a) / / /

    (b) / * / +

    (c) = = = +

    (d) = - + * / %

    (e) = % / * +

    (f) = = % / +

## [D]

    (a) (x + 3) * x * x * x / ((y - 4) * (y + 5));

    (b) 2 * v + 6.22 * (c + d) / (g + v);

    (c) 7.7 * b (x * y + a) / c - 0.8 + 2 * b / ((x + a)*(1 / y));

    (d) (12 * x * x * x ) / (4 * x) + (8 * x * x) / (4 * x) + (x / (8 * x)) + 8 / (8 * x);

## [E]

    (a)  0 2 0.000000 2.000000

    (b) a=2 b=-2 c=2 d=-2

    (c) 2

    (d) Compile error

    (e)  Respective values of a & b

## [F]

    (a) True

    (b) False

    (c) True

    (d) True

    (e) False

    (f) True

## [G]

    (a)  10*x

    (b)  5

    (c)  5

    (d)  -9

    (e)  0.285714

## [H]

(a)

    #include<stdio.h>
    int main()
    {
    int number,sum=0;
    printf("Enter number\n");
    scanf("%d",&number);
    while(number!=0)
    {
        sum+=number%10;
        number/=10;
    }
    printf("Sum of digits is %d",sum);
    return 0;
    }

OR

    #include<stdio.h>
    #include<conio.h>
    int main()
    {
    int num,a,b,c,d,e;
    printf("Enter a five digit number : ");
    scanf("%d", &num);
    e=num%10;
    d=(num/10)%10;
    c=(num/100)%10;
    b=(num/1000)%10;
    a=(num/10000);
    printf("%d is the sum of the digits of the number %d.", a+b+c+d+e, num);
    getch();
    return 0;
    }

(b)

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
    printf("Reverse of number %d is %d",temp,reverse);
    return 0;
    }

OR

      #include<stdio.h>
    #include<conio.h>
    int main()
    {
    int num,a,b,c,d,e;
    printf("Enter a five digit number : ");
    scanf("%d", &num);
    e=num%10;
    d=(num/10)%10;
    c=(num/100)%10;
    b=(num/1000)%10;
    a=(num/10000);
    num = e*10000+d*1000+c*100+b*10+a;
    printf("\n%d", num);
    getch();
    return 0;
    }

(c)

    #include<math.h>
    #include<stdio.h>
    int main()
    {
    float side1,side2,side3,s_p;
    printf("Enter sides of triangle\n");
    scanf("%f %f %f",&side1,&side2,&side3);
    s_p=(side3+side2+side1)/2.0;
    printf("Area of triangle is %f",sqrt(s_p*(s_p-side1)*(s_p-side2)*(s_p-side3)));
    return 0;
    }

OR

    #include<stdio.h>
    #include<conio.h>
    #include<math.h>
    int main()
    {
    	float a , b , c , s , area;

    printf("\nEnter three sides of the triangle : ");
    scanf("%f%f%f", &a, &b, &c);

    //Finding area of the triangle by the Heron's Formula
    s = (a+b+c)/2;
    area = sqrt(s*(s-a)*(s-b)*(s-c));
    //sqrt() is a funtion that find the square root.

    printf("\nArea : %f", area);

    getch();
    return 0;
    }

(d)

    #include<stdio.h>
    #include<math.h>
    int main()
    {
    printf("Enter x and y coordinates \n");
    float x,y;
    scanf("%f %f",&x,&y);
    printf("Polar coordinates are (%f,%f).\n",sqrt(pow(x,2.0)+pow(y,2.0)),atan(y/x));
    return 0;
    }

OR

    #include<stdio.h>>
    #include<conio.h>
    #include<math.h>
    int main()
    {
    float x, y, r, theta;

    printf("Enter the x and y coordinates : ");
    scanf("%f%f", &x, &y);

    r = sqrt(x*x + y*y);
    theta = atan(y/x);
    //atan() is a function to find the tan inverse

    printf("\nCoordinates in polar form : %.2f(cos(%.2f) + i.sin(%.2f))", r, theta, theta);
    //%.2f means only two decimal palces will be printed.

    getch();
    return 0;
    }

(e)

    #include<stdio.h>
    #include<math.h>
    int main()
    {   float l1,l2,g1,g2;
    printf("Enter values of latitude (l1,l2)\n");
    scanf("%f %f",&l1,&l2);
    printf("Enter values of longitude(g1,g2) in degrees\n");
    scanf("%f %f",&g1,&g2);
    printf("The Distance between them is %f\n",(3963*acos(sin(l1)*sin(l2)+cos(l1)*cos(l2)*cos(g2-g1))));
    return 0;
    }

OR

    #include<stdio.h>
    #include<conio.h>
    #include<math.h>
    int main()
    {
    float l1,l2,g1,g2, D;

    printf("\nEnter (two) the values of lattitude : ");
    scanf("%f%f", &l1, &l2);

    printf("\nEnter (two) the values of longitude : ");
    scanf("%f%f", &g1, &g2);

    D = 3963*acos(sin(l1)*sin(l2) + cos(l1)*cos(l2)*cos(g2-g1));

    printf("\nDistance : %f", D);

    getch();
    return 0;
    }

(f)

    #include<math.h>
    #include<stdio.h>
    int main()
    {
    printf("Enter temperature and velocity of wind\n");
    float temp,vel,wcf=0;
    scanf("%f %f",&temp,&vel);
    wcf=35.74+0.6215*temp+(0.4275*temp-35.75)*pow(vel,0.16);
    printf("Wind Chill factor of Temperature %f and Velocity %f is %f",temp,vel,wcf);
    return 0;
    }

OR

       #include<stdio.h>
    #include<conio.h>
    #include<math.h>
    int main()
    {
    float t, v, wcf;

    printf("\nEnter the vakues of temperature and wind velocity: ");
    scanf("%f%f", &t, &v);

    wcf = 35.74 + 0.6215*t + (0.42751*t - 35.75)*pow(v, 0.16);
    //pow(a,b) function is used to calculate a^b

    printf("Wind Chill Factor : %f", wcf);

    getch();
    return 0;
    }

(g)

    #include<stdio.h>
    #include<math.h>
    int main()
    {
    printf("Enter the value of angle\n");
    float angle;
    scanf("%f",&angle);
    printf("The sine of angle = %f.\n",sin(angle));
    printf("The cosine of angle = %f.\n",cos(angle));
    printf("The tangent of angle = %f.\n",tan(angle));
    printf("The cotangent of angle = %f.\n",(1/tan(angle)));
    printf("The cosecant of angle = %f.\n",(1/sin(angle)));
    printf("The secant of angle = %f.\n",(1/cos(angle)));
    return 0;
    }

(h)

    #include<stdio.h>
    int main()
    {
    printf("Enter two numbers\n");
    int c,d;
    scanf("%d %d",&c,&d);
    printf("Before Interchange C=%d and D=%d.\n",c,d);
    c=c+d;
    d=c-d;
    c=c-d;
    printf("After Interchange C=%d and D=%d.\n",c,d);
    return 0;
    }

(i)

    #include<stdio.h>
    #include<conio.h>
    int main()
    {
    int n100, n50, n10, n5, n2, n1, num;

    printf("\nEnter the amount : ");
    scanf("%d", &num);

    //Numbers of notes of 100
    n100 = num / 100;
    num = num % 100;

    //Numbers of notes of 50
    n50 = num / 50;
    num = num % 50;

    //Numbers of notes of 10
    n10 = num / 10;
    num = num % 10;

    //Numbers of notes of 5
    n5 = num / 5;
    num = num % 5;

    //Numbers of notes of 2
    n2 = num / 2;
    num = num % 2;

    //Numbers of notes of 1
    n1 = num / 1;

    printf("\n\nTo give amount of %d you have to give : \n");
    printf("%d of notes of hundred.\n", n100);
    printf("%d of notes of fifty.\n", n50);
    printf("%d of notes of ten.\n", n10);
    printf("%d of notes of five.\n", n5);
    printf("%d of notes of two.\n", n2);
    printf("%d of notes of one.\n", n1);

    getch();
    return 0;
    }
