# [Chapter 9: Pointers] Solutions

## [A]

    (a) 5 2
  
    (b) 25 4
  
    (c) 
  
  	1006 1006 1006
  
      13.500000 13.500000 13.500000 13.500000 13.500000   #as it is a pointer 
## [B]

  (a) Error: 
      1. pass() cannot return a value as its return type is void.
      2. we cannot assign pass() to other variable as its return type is void
      3. We cannot define variables inbetween function name and its body.
  
  (b) Error: Invalid conversion fro int to int*. Cannot pass address
      in the function whose argument accepts integer.
  
  (c)  Error:
       1. Can't assign a function returning void, to other variable.
       2. m is not declared in the argument declaration feild of function.
  
  (d) Error:
      1. Can't assign a function returning void, to other variable.
      2. function() cannot return anything with return type void. 
  
  ## [C]
  
   (a)
       
    #include<stdio.h>
    #include<conio.h>
    #include<math.h>

    void calc(int, int, int, int, int, int*, int*, float*);

    int main()
    {
	int a, b, c, d, e, sm, av;
	float sd;

	printf("Enter five numbers : ");
	scanf("%d%d%d%d%d", &a, &b, &c, &d, &e);

	calc(a, b, c, d, e, &sm, &av, &sd);

	printf("\nSum : %d\n\nAverage : %d\n\nStandard Deviation : %f\n", sm, av, sd);

	getch();
	return 0;
    }
    void calc(int a, int b, int c, int d, int e, int *sm, int *av, float *sd)
    {
	int i;
	*sm = a + b + c + d + e;
	*av = *sm / 5;
	*sd = pow(a - *av, 2) + pow(b - *av, 2) + pow(c - *av, 2) + pow(d - *av, 2) + pow(e - *av, 2);
	*sd = sqrt(*sd / 5);
    }
   
   (b)
   
    #include<stdio.h>
    #include<conio.h>

    void calc(int, int, int, float*, float*);

    int main()
      {
	float av, pr;
	int a, b, c;
	printf("Enter the marks of the student in three subjects out of 100 :");
	scanf("%d%d%d", &a, &b, &c);

	calc(a, b, c, &av, &pr);

	printf("\n\nAverage of the marks : %f\n\nPercentage of the student : %f", av, pr);
	getch();
	return 0;
    }
    void calc(int a, int b, int c, float *av, float *pr)
    {
	*av = (a + b + c) / 3;
	*pr = *av / 3;
    }
   
   (c)
   
    #include<stdio.h>
    #include<conio.h>
    #include<math.h>

    int fact(int);
    float sine(float value_at);
    int main()
    {
	float x, sum;
	printf("Enter the angle in radians : ");
	scanf("%lf", &x);
	sum = sine(x); //calling the sum of he series
	printf("\n\nsin(%lf) = %lf", x, sum);
	getch();
	return 0;
    }

    float sine(float x)
    {
	int i, j, sign = 1;
	float sum = 0;
	for (i = 0, j = 1; i < 5; i++, j += 2, sign *= -1)
		sum = sum + /*pow(-1, i)*/sign*pow(x, j) / fact(j);
	return sum;
    }

    int fact(int num)
    {
	int ans = 1;
	while (num > 0)
	{
		ans *= num;
		num--;
	}
	return ans;
    }
   
   (d)
   
    #include<stdio.h>
    #include<conio.h>

    void chng(int*, int*, int*);

    int main()
    {
	int a, b, c;
	printf("Enter three numbers : ");
	scanf("%d%d%d", &a, &b, &c);

	printf("\n\nYou've Entered\n\na : %d	b : %d	c : %d\n", a, b, c);
	chng(&a, &b, &c);

	printf("\nAfter Shifting\n\na : %d	b : %d	c : %d\n", a, b, c);
	getch();
	return 0;

    }
    void chng(int *a, int *b, int *c)
    {
	int x;
	x = *c;
	*c = *b;
	*b = *a;
	*a = x;
    }
   
   (e)
   
    #include<stdio.h>
    #include<conio.h>
    #include<math.h>

    float ar(float, float, float);
    int main()
    {
	float area, a, b, c;
	printf("Enter the sides of the triangle : ");
	scanf("%f%f%f", &a, &b, &c);
	if (a + b >c && b + c >a && a + c>b)
	{
		area = ar(a, b, c);
		printf("\n\nArea of the triangle : %f", area);
	}
	else
		printf("\n\nThe triangle you entered is invalid.");
	getch();
	return 0;
    }
    float ar(float a, float b, float c)
    {
	float area;
	float S = (a + b + c) / 2;
	area = sqrt(S*(S - a)*(S - b)*(S - c));
	return (area);
    }
   
   (f)
   
    #include<stdio.h>
    #include<conio.h>
    #include<math.h>

    float dis(int, int, int, int);
    float ar(int, int, int, int, int, int);
    int main()
    {
	int x1, x2, x3, y1, y2, y3, x, y;
	float A1, A2, A3, A;
	printf("Enter the cordinates of first point of the trianlge : ");
	scanf("%d%d", &x1, &y1);
	printf("\n\nEnter the cordinates of second point of the trianlge : ");
	scanf("%d%d", &x2, &y2);
	printf("\n\nEnter the cordinates of third point of the trianlge : ");
	scanf("%d%d", &x3, &y3);
	printf("\n\nEnter the points to check it's position : ");
	scanf("%d%d", &x, &y);
	A1 = ar(x1, y1, x2, y2, x, y);
	printf("A1 : %f\n", A1);
	A2 = ar(x1, y1, x3, y3, x, y);
	printf("A2 : %f\n", A2);
	A3 = ar(x, y, x2, y2, x3, y3);
	printf("A3 : %f\n", A3);
	A = ar(x1, y1, x2, y2, x3, y3);
	printf("A : %f\n", A);
	if (!(A1 + A2 + A3>A || A1 + A2 + A3<A))
		printf("\n\nThe point (%d,%d) lies inside of triangle.", x, y);
	else
		printf("\n\nThe point (%d,%d) lies outside of triangle.", x, y);
	getch();
	return 0;
    }

    float dis(int x1, int y1, int x2, int y2)
    {
  	float distance;
	distance = sqrt(pow((x2 - x1), 2) + pow((y2 - y1), 2));
	return (distance);
     }

    float ar(int x1, int y1, int x2, int y2, int x3, int y3)
    {
	float a, b, c, area, S;
	a = dis(x1, y1, x2, y2);
	b = dis(x1, y1, x3, y3);
	c = dis(x2, y2, x3, y3);
	S = (a + b + c) / 2;
	area = sqrt(S*(S - a)*(S - b)*(S - c));
	return (area);
    }
   
   (g)
   
    #include<stdio.h>
    #include<conio.h>

    int gcd(int, int);

    int main()
    {
	int a, b, cd, max, min;
	printf("Enter two numbers : ");
	scanf("%d%d", &a, &b);
	if (a>b)//for making a greater number
	{
		max = a;
		min = b;
	}
	else
	{
		max = b;
		min = a;
	}
	a = max;
	b = min;
	cd = gcd(a, b);//returning the greatest divisor
	printf("\n\nGreatest common divisor of the givn numbers is %d", cd);
	getch();
	return 0;
    }

    int gcd(int a, int b)
    {
	static int x, temp;
	if (b == 0)
		return (a);
	x = a / b;
	temp = a;
	a = b;
	b = temp - x*b;
	gcd(a, b);
    }
