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
    (b) / + * /
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

(c)

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
     
     
    



