# [Periodic Test -2] Solutions

## [A]
 
    (1) clrscr()
    (2) Pointers
    (3) & (Ampersand)
    (4) Macro Expansion 
    (5) Address
    
## [B]

    (1) False
    (2) True
    (3) True
    (4) True
    (5) False

## [C]

   (1) 
     
      The stack can be easily allocated as well as freed again, so it is a natural choice. All the variable addresses are           relative to the stack pointer that is incremented at each function call or return. Fast easy way to allocate and             cleanup memory used by these variables.
      
   (2) 
      
      When we want to make changes to original value's we use "call by reference" ,other way if we want to work on some             temporary copy of original values we use "call by value".

   (3)
   
      Sizeof a pointer is independent of type of the variables because the type of every pointer variable is implicitly             unsigned integer.
      
   (4)
   
      Hole concept is found in the structures in c language where the compiler leaves certain holes in the memory alignment         when it allocates memory on the page boundaries.Thats the reason u get the sizeof structure some times greater than           the sum of all the fields in the structure . 
         Also called structure padding ,structure paddding can be avoided by using a preprocessor directive #pragma 1 the              compiler will alocate memory in multiples of one.
   
   (5)  
      
       Stopping condition can be any conditional statement (most cases), or it can be exception depending upon the                  implementation.Any recursive function without stoppage condition goes to infinite loop and blow up the stack.

## [D]

   (1)
      
    #include<stdio.h>
    int fun(int,int,int,int);
    int main()
    {
    printf("Enter four integers\n");
    int a,b,c,d;
    scanf("%d %d %d %d",&a,&b,&c,&d);
    fun(a,b,c,d);
    return 0;
    }
    int fun(int a,int b,int c,int d)
    {
    printf("Sum is %d.\n",a+b+c+d);
    printf("Product is %d.\n",a*b*c*d);
    printf("Average is %f.\n",(float)(a+b+c+d)/4.0);
    return 0;
    }
   (2)
  
    int func(int);
    #include <stdio.h>

    int main()
    {   int number;
    printf("Enter Number\n");
    scanf("%d",&number);
    func(number);
    return 0;
    }
    int func(int num)
    {
    int counter_var;
    for(counter_var=2;counter_var<=num;counter_var++)
    {
        if(num%counter_var==0)
        {
            printf("%d\n",counter_var);
            func(num/counter_var);
            break;
        }
    }
    return 0;
    }

    
   (3)
     
     #define PI 3.14159265
    #include<stdio.h>
    int main()
    {   float radius;
    printf("Enter radius\n");
    scanf("%f",&radius);
    printf("The area of circle is %f.\n",PI*radius*radius);
    printf("The circumference of circle is %f.\n",2*PI*radius);
    printf("Volume of sphere is %f.\n",4.0/3.0*PI*radius*radius*radius);
    printf("Enter height of cone\n");
    float height;
    scanf("%f",&height);
    printf("Volume of cone is %f.\n",PI*radius*radius*(height/3.0));
    return 0;
    }
  
  (4)
  
     #include <stdio.h>
    int main()
    {
    int integerType;
    float floatType;
    double doubleType;
    char charType;
    // Sizeof operator is used to evaluate the size of a variable
    printf("Size of int: %ld bytes\n",sizeof(integerType));
    printf("Size of float: %ld bytes\n",sizeof(floatType));
    printf("Size of double: %ld bytes\n",sizeof(doubleType));
    printf("Size of char: %ld byte\n",sizeof(charType));
    return 0;
    }
   

       
    
