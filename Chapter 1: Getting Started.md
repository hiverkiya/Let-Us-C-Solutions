# Chapter-1 : Getting Started

### [A]

   REASON:- A character constant is a constant which uses single quotation around characters.
       
    Invalid:- '3.15' eLearning' 'Quest'
  
   REASON:- No Comma/Space in integer constant & No exponentiation operator available.
   
    Invalid:- "35,550" "2^3" "4 6 5 2"
   
  
## [B] 
REASON:- No special symbol except underscore allowed in variable naming
    
       B'day $hello  #HASH _main() total% %name% stack-queue	
    
REASON:- Keyword cannot be used as a variable.

    	int
REASON:- Variable name should start with an alphabet.
    	
    	Same as 1st

## [C]
    
    (a) True
   
    (b) True
   
    (c) True
   
    (d) True
   
    (e) True
    
    (f) True
   
    (g) True
   
    (h) True
   
    (i) True
   
    (j) False
    
    (k) True
   
    (l) False
 
## [D]
         
    (a) Escape Sequence 
   
    (b) Real Constant
  
    (c) Integer Constant
   
    (d) Character Constant
   
    (e) Exponential Form
   
    (f) Function
   
    (g) Format Specifier
   
    (h) Statement Terminator
   
    (i) Literal
   
    (j) Identifier
  
    (k) Address of Operator
  
    (l) Output Function
   
    (m) Input Function
    
## [E] 
    
    (a) Statement Terminator is missing, and it couldn't be figured out whether the expression is (a+b)*(b-35)
    
       or a+(b*b)-35 because of unavailability of parentheses.
    
    (b) Nesting of comments is not allowed.
    
    (c) "&" Operator is Missing.
    
    (d) Statement terminator operator ";" is missing in integer declaration and scanf & printf functions.
    
## [F]

   (a)
   
   	#include<stdio.h>
	int main()
	{
  	  float bs,gs;
  	  printf("Enter basic salary of Rakesh.\n");
  	  scanf("%f",&bs);
      printf("Gross salary of Rakesh is %f.\n",(bs+(0.4*bs)+(0.2*bs)));
  	  return 0;
	}
	
   OR
   
   	#include<stdio.h>
	#include<conio.h>
	int main()
	{
	 int sal;
	 float gros_sal;
  	 printf("Enter the basic salary of Ramesh : ");
	 scanf("%d", &sal);
	 //salary calculated
	 gros_sal=sal+(sal*40/100)+(sal*20/100);
	 printf("%f is the gross salary of Ramesh.", gros_sal);
	 getch();
	 return 0;
	}
   	

   (b)
   
   	#include<stdio.h>
	int main()
	{ 
	  float meters,feet,inches,centi_m,km;
  	  printf("Enter the distance in km\n");
   	  scanf("%f",&km);
   	  meters=km*1000;
   	  centi_m=meters*100;
   	  feet=3.28084*meters;
   	  inches=12*feet;
   	  printf("The distance in meters = %f\n",meters);
   	  printf("The distance in centimeters = %f\n",centi_m);
   	  printf("The distance in feet = %f\n",feet);
   	  printf("The distance in inches = %f\n",inches);
   	  return 0;
     }

   OR
   
   	#include<stdio.h>
	#include<conio.h>
	int main()
	{
 	 float dis;
	 printf("Enter the distance between cities in kilo metres : ");
	 scanf("%f", &dis);
	 printf("\n%f is the distance between them in meters.", dis*1000);
	 printf("\n%f is the distance between them in feet.", dis*3280.8399);
	 printf("\n%f is the distance between them in inches.", dis*39370.0788);
	 printf("\n%f is the distnace between them in centimeters", dis*100000);
     getch();
	 return 0;
    }
  
  (c) 
    
    #include<stdio.h>
    int main()
    {
      printf("Enter marks of student\n");
      float array[5],aggregate=0,percentage;
      int i;
      for(i=0;i<5;i++)
      {
       scanf("%f",&array[i]);
       aggregate+=array[i];
      }
       printf("Aggregate Marks of Student are :- %f.\n",aggregate);
       percentage=aggregate/500*100;
       printf("Percentage of Students is %f.\n",percentage);
       return 0;
     }
    
   OR
   
   	#include<stdio.h>
	#include<conio.h>
	int main()
	{
	 float a,b,c,d,e;
     printf("Enter the marks out of 100 in five subjects of the student : ");
	 scanf("%f%f%f%f%f", &a,&b,&c,&d,&e);
	 //his total marks
	 printf("\n%f is the aggregate marks obtained by him.", a+b+c+d+e);
     //his percentage marks
     printf("\n%f is the percentage marks obtained by him.", (a+b+c+d+e)/5);
	 getch();
	 return 0;
	}
  
  (d)
   
    #include<stdio.h> 
    int main()
    {
     float temp_in_c,temp_in_f;
     printf("Enter the temperature in Fahrenheit\n");
     scanf("%f",&temp_in_f);
     printf("Temperature in Celsius = %f.",(temp_in_f-32)/1.8);
     return 0;
    }
    
   OR
   
   	#include<stdio.h>
	#include<conio.h>
	int main()
	{
	 float f,c;
 	 printf("Enter the temperature in Fahrenheit : ");
	 scanf("%f", &f);
	 //conversion of temperature
	 c=(f-32)*100/180;
	 printf("\n%f is that temperature in celcius.", c);
	 getch();
	 return 0;
	}
 
 (e) 
   
    #define PI 3.14159265
    #include<stdio.h>
    int main()
    {
     printf("Enter the length and breadth of rectangle\n");
	 float length,breadth;
	 scanf("%f %f",&length,&breadth);
	 printf("Enter the radius of circle\n");
	 float radius,area=0;
	 scanf("%f",&radius);
     printf("Area of Rectangle is %f and Perimeter is %f.\n",length*breadth,2*(length+breadth));
     printf("Area of Circle is %f and Circumference is %f.\n",PI*radius*radius,2*PI*radius);
	 return 0;
    }
    
   OR
   
   	#include<stdio.h>
	#include<conio.h>
	int main()
	{
	 float l,b,r;
	 printf("Enter the length and breadth of the rectangle : ");
  	 scanf("%f%f", &l,&b);
	 //rectangle calculations
	 printf("\n%f is the area of the rectangle.", l*b);
	 printf("\n%f is the perimeter of the rectangle.", l+b);
	 //circle calculations
	 printf("\n\nEnter the radius of the circle : ");
	 scanf("%f", &r);
	 printf("\n%f is the area of the circle.", 3.14*r*r);
	 printf("\n%f is the perimeter of the circle.", 2*3.14*r);
	 getch();
	 return 0;
	}
	
   (f)
   
    #include <stdio.h>
     int main()
    {   
     int length=1189,breadth=841,temp,i;
     for(i=0;i<=8;i++)
     {
      printf("The size of A(%d) sheet = %d mm x %d mm.\n",i,length,breadth);
      temp=length;
      length=breadth;
      breadth=temp/2;
     }
     return 0;
    }

   OR
   
   	#include<stdio.h>
	#include<conio.h>
	int main()
	{
	 int A0_a, A0_b, A1_a, A1_b, A2_a, A2_b, A3_a, A3_b, A4_a, A4_b, A5_a, A5_b, A6_a, A6_b, A7_a, A7_b, A8_a, A8_b;
	 A0_a = 1189;
	 A0_b = 841;
	 printf("\nA0 : %dmm x %dmm ", A0_a, A0_b);
	 A1_a = A0_b;
	 A1_b = A0_a/2;
	 printf("\nA1 : %dmm x %dmm ", A1_a, A1_b);
	 A2_a = A1_b;
	 A2_b = A1_a/2;
	 printf("\nA2 : %dmm x %dmm", A2_a, A2_b);
	 A3_a = A2_b;
	 A3_b = A2_a/2;
	 printf("\nA3 : %dmm x %dmm", A3_a, A3_b);
	 A4_a = A3_b;
	 A4_b = A3_a/2;
	 printf("\nA4 : %dmm x %dmm", A4_a, A4_b);
	 A5_a = A4_b;
	 A5_b = A4_a/2;
	 printf("\nA5 : %dmm x %dmm", A5_a, A5_b);
	 A6_a = A5_b;
	 A6_b = A5_a/2;
	 printf("\nA6 : %dmm x %dmm", A6_a, A6_b);
	 A7_a = A6_b;
	 A7_b = A6_a/2;
	 printf("\nA7 : %dmm x %dmm", A7_a, A7_b);
	 A8_a = A7_b;
	 A8_b = A7_a/2;
	 printf("\nA8 : %dmm x %dmm", A8_a, A8_b);
	 getch();
     return 0;
	}
	
	
