# [Chapter 12: The C Preprocessor] Solutions

## [A]

    (a) 3. a message from programmer to the preprocessor
      
    (b) #define SQR(X) ( X * X ) 
   
    (c)
   	1. False
        2. False
        3. True
        4. False
        5. False
        6. False
        
    (d) We can include any number of files we want to include in a program.
   
    (e)  In the first statement, we can give any path of the
	file to be included. While the name given in the second statement
	looks for the file in the default set of directories.
   
    (f) All are true.
   
    (g)  #elseif
   
    (h) 1. Before the compilation of program.
   
    (i) 1. Before the compilation of program.
   
## [B]

    (a) 2
    
    (b) 9 49
    
    (c)  
        
        a = 43.14
        
        b = 5863.727051

## [C]
    
   (a) 
   
   	Before compilation, our source code is expanded and stored in
	the file FILENAME.I, so we can open this file and check how our program
	is getting expand.

   (b) 
   
     1. #define LOWER (alpha>=97 && alpha<=122)
     2. #define UPPER (alpha>=65 && alpha<=90)
     3. #define UPPER (alpha>=65 && alpha<=90)
        #define LOWER (alpha>=97 && alpha<=122)
        #define YES (UPPER || LOWER)
     4. #define MAX(a,b) ((a>b)?a:b)
   
   (c) Code for header file areaperi.h
      
    #include<math.h>
    #define PI 3.14
    #define S(a,b,c) ((a+b+c)/2.0)
    #define TRI_AREA(a,b,c) (sqrt((S(a,b,c))*((S(a,b,c))-a)*((S(a,b,c))-b)*((S(a,b,c))-c)))
    #define TRI_PERI(a,b,c) (a+b+c)
    #define SQR_AREA(x) (x*x)
    #define SQR_PERI(x) (2*(x+x))
    #define CIR_AREA(r) (PI*r*r)
    #define CIR_PERI(r) (2*PI*r)
      
   Actual Program
   
    #include<stdio.h>
    #include<conio.h>
    #include "areaperi.h"

    int main()
    {
	int r, a, x, y, z;
	double cir_ar, cir_peri, sqr_ar, sqr_peri, tri_ar, tri_peri;

	printf("Enter the radius of the circle : ");
	scanf("%d", &r);
	printf("\nEnter the side of the square : ");
	scanf("%d", &a);
	printf("\nEnter the sides of the triangle : ");
	scanf("%d%d%d", &x, &y, &z);

	if (x + y>z && y + z>x && x + z>y)
	{
		tri_ar = TRI_AREA(x, y, z);
		tri_peri = TRI_PERI(x, y, z);
		printf("\nTriangle");
		printf("\nArea : %lf\nPerimeter : %f\n", tri_ar, tri_peri);
	}
	else
		printf("\nThe triangle You entered is invalid.\n");

	cir_ar = CIR_AREA(r);
	cir_peri = CIR_PERI(r);
	sqr_ar = SQR_AREA(a);
	sqr_peri = SQR_PERI(a);
	printf("\nCircle");
	printf("\nArea : %f\nPerimeter : %f\n", cir_ar, cir_peri);
	printf("\nSquare");
	printf("\nArea : %f\nPerimeter : %f\n", sqr_ar, sqr_peri);
	getch();
	return 0;
    }

 (d)    
  
    (1) #define MEAN(x,y) ((x+y)/2.0)
    (2) #define ABS(x) ((x<0)?(-1*x):x)
    (3)  #define U2L(c) (c+32)
    (4) #define MAX(a,b) ((a>b)?a:b)
    
 (e)   Header file code
  
        #define SI(a,b,c) ((a*b*c)/100.0)
        #define AMOUNT(si,p) (si+p)
        
   Actual file code
      
    #include<stdio.h>
    #include<conio.h>
    #include "interest.h"

    int main()
    {
	float p, t, r, si, amnt;
	printf("Enter the principal, time in year and rate of interest : ");
	scanf("%f%f%f", &p, &t, &r);
	si = SI(p, t, r);
	amnt = AMOUNT(si, p);
	printf("\nSimple Interest : %f\nAmount : %f", si, amnt);
	_getch();
	return 0;
    }
        
