# Chapter-1 Getting Started

## [A]
	
   REASON:- A character constant is a constant which uses single quotation around characters.
       
    Invalid:- '3.15' eLearning' 'Quest'
  
   REASON:- No Comma/Space in integer constant & No exponentiation operator available.
   
    Invalid:- "35,550" "2^3" "4 6 5 2"
  
## [B] 
    
    1. REASON:- No special symbol other than underscore is allowed in variable naming.
	        B'day $hello  #HASH _main() total% %name% stack-queue	
    2. REASON:- Keyword cannot be used as a variable.
    	int
    3. REASON:- Variable name should start with an alphabet.
    	1st

## [C]
    
    (a) True
    (b) True
    (c) True
    (d) True
    (e) False
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

    (a) Statement Terminator is missing, and it couldn't be figured out whether the expression is (a+b)*(b-35) or a+(b*b)-35 because of unavailability of parentheses.
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
   	 printf("Gross salary of Rakesh is %f.\n",(bs-(0.4*bs)-(0.2*bs)));
  	  return 0;
	}

   (b)
   
   	#include<stdio.h>
	int main()
	{ float meters,feet,inches,centi_m,km;
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

	
	
