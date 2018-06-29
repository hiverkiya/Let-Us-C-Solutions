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
    (3) False
    (4) True
    (5) False

## [C]

## [D]

   (1)
   (2)
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
   

       
    
