# Chapter-1 Getting Started

## [A]
  
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
	
