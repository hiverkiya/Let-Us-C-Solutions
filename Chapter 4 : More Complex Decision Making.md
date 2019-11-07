# Chapter-4 More Complex Decision Making
## [A]
  
    Value: 1

           0
           
           1
           
           1
           
           1
         
## [B]

    (a) Dean of students affairs
  
    (b) w=1 x=0 y=1 z=1
  
    (c) biggest=45
  
    (d) -1 1
   
    (e) 1
  
    (f) Compile error
  
## [C] 

    (a) NO ERROR.
    
    (b) NO ERROR.
   
    (c) Wrong use of "&&" Operators.
   
    (d) NO ERROR.
   
    (e) "else" used without previous "if" as first "if" is terminated with ";"
   
    (f) NO ERROR.
   
    (g) NO ERROR.However,result will be j>=65?9: 
    
    (h) lvalue required as left operand of assignment
   
    (i) Wrong use of ternary operator "? then :".
   
    (j) There is no use of ";" after printf().

## [D]

(a)  

      #include<stdio.h>
      int main()
      {
         int year;  
         scanf("%d",&year);
         if(year%4==0 || year%100==0 || year%400==0)       
         printf("%d is a leap year",year);       
         else     
         printf("%d is not a leap year",year);       
         return 0;       
     }
    
(b)

       #include<stdio.h>
       int main()
       {
         char character;
         scanf("%c",&character);
         if(character>=65 && character<=90)
         printf("%c is a capital letter",character);
         else if(character>=97 && character<=122)
         printf("%c is a small letter",character);
         else if(character>=48 && character<=57)
         printf("%c is a digit",character);
         else
         printf("%c is a special symbol",character);
         return 0;
    }
    
(c)

         #include<stdio.h>
         int main()
         {
           int hard,tensile;
           float carbon;
           scanf("%d",&hard);
           scanf("%f",&carbon);
           scanf("%d",&tensile);
           if(hard>50 && carbon<0.7 && tensile>5600)
           printf("Grade is 10");
           else if(hard>50 && carbon<0.7 && tensile<=5600)
           printf("Grade is 9");
           else if(hard<=50 && carbon<0.7 && tensile>5600)
           printf("Grade is 8");
           else if(hard>50 && carbon>=0.7 && tensile>5600)
           printf("Grade is 7");
           else 
	   if(hard>50 && carbon>=0.7 && tensile<=5600 || hard<=50 && carbon<0.7
	   && tensile<=5600 || hard<=50 && carbon>=0.7          &&tensile>5600)
          printf("Grade is 6");
          else
          printf("Grade is 5");
          return 0;
          }
          
(d)

    #include<stdio.h>
    int main()
    {
    int s1,s2,s3,largest;
    scanf("%d %d %d",&s1,&s2,&s3);
    if(s1>s2 && s1>s3)
    largest=s1;
    else if(s2>s1 && s2>s3)
    largest=s2;
    else
    largest=s3;
    if((s1+s2)>largest|| (s2+s3)>largest || (s1+s3)>largest)
    printf("Triangle is valid");
    else 
    printf("Triangle is not valid");
    return 0;
    }
    
    
(e)

    #include<stdio.h>
    int main()
    {
    int x,y,z;
    scanf("%d %d %d",&x,&y,&z);
    if(x*x+y*y==z*z)
    printf("The triangle is right angle");
    else if((x==y) && (y==z))
    {
    printf("\nThe triangle is equilateral");
    } 
    else if((x==z) && (x!=y) || (y==z) && (y!=x) || (x==y) && (x!=y))
    {
    printf("\nThe triangle is isoseles");
    }
    else
    {
    printf("\nThe triangle is scalene");
    }
    return 0;
    }
    
(f)
  
  
    #inlcude<stdio.h>
    int main()
    {
    int weigh;
    scanf("%d",&weigh);
    if(weigh<115)
    printf("Flyweight");
    else if(weigh>=115 && weigh<=121)
    printf("Bantamweight");
    else if(weigh>=122 && weigh<=153)
    printf("Featherweight");
    else if(weigh>=154 && weigh<=189)
    printf("Middleweight");
    else
    printf("Heavyweight");
    return 0;
    }
    
(g)

    #include<stdio.h>
    int main()
    {
	  float r, g, b, c, m, y, k, w = 0;
	
	printf("\nEnter the color values of R, G and B : ");
	scanf("%f %f %f", &r, &g, &b);
	
	r /= 255;
	g /= 255;
	b /= 255;
	
	if(w < r)
		w = r;
	
	if(w < g)
		w = g;
	
	if(w < b)
		w = b;
	
	
	c = (w - r) / w;
	m = (w - g) / w;
	y = (w - b) / w;
	k = 1 - w;
	
	printf("\nC : %f\nM : %f\nY : %f\nK : %f", c,m,y,k);
	return 0;
	}

(h)

    #include<stdio.h>
     int main()
    {
     int d,m;
	
	printf("\nEnter the data and month of birth : ");
	scanf("%d %d", &d, &m);
	
	printf("\nYour Zodiac is : ");
	
	if(m == 12 && d >= 22 || m == 1 && d <= 19)
		printf("Capricorn.");
	
	if(m == 1 && d >= 20 || m == 2 && d <= 17)
		printf("Aquaries.");
		
	if(m == 2 && d >= 18 || m == 3 && d <= 19)
		printf("Pisces");
	
	if(m == 3 && d >= 20 || m == 4 && d <= 19)
		printf("Aries");
		
	if(m == 4 && d >= 20 || m == 5 && d <= 20)
		printf("Taurus");
		
	if(m == 5 && d >= 21 || m == 6 && d <= 20)
		printf("Gemini");
		
	if(m == 6 && d >= 21 || m == 7 && d <= 22)
		printf("cancer");
		
	if(m == 7 && d >= 23 || m == 8 && d <= 22)
		printf("Leo");
		
	if(m == 8 && d >= 23 || m == 9 && d <= 22)
		printf("Virgo");
		
	if(m == 9 && d >= 23 || m == 10 && d <=22)
		printf("Libra");
		
	if(m == 10 && d >= 23 || m == 11 && d <= 21)
		printf("Scorpio");
		
	if(m == 11 && d >= 22 || m == 12 && d <=21)
		printf("Sagittarius.");
	return 0;
	}

(i)

      #include<stdio.h>
      int main()
      {
	  float w, h, bmi;
	
	printf("\nEnter you wight (in kg) and height (in m) : ");
	scanf("%f %f", &w, &h);
	
	bmi = w / (h * h);
	
	printf("\nYour BMI category is : ");
	
	if(bmi < 15)
		printf("Starvation");
		
	if(bmi >= 15.1 && bmi <= 17.5)
		printf("Anorexic");
		
	if(bmi >= 17.6 && bmi <= 18.5)
		printf("Underweight");
		
	if(bmi >= 18.6 && bmi <= 24.9)
		printf("Ideal");
		
	if(bmi >= 25 && bmi <= 25.9)
		printf("Overweight");
		
	if(bmi >= 30 && bmi <= 30.9)
		printf("Obese.");
		
	if(bmi >= 40)
		printf("Morbidly Obese");
	return 0;
    }
    
## [E]

(a)
	
	(1)      
        
        #include<stdio.h>
        int main()
        {
	     char ch;
	
	printf("Enter a character : ");
	scanf("%c", &ch);
	
	ch > 98 && ch < 123 ? printf("Lower case alphabet."):printf("Not a lower case alphabet.");
	return 0;
         }
      
(2)


     #include<stdio.h>
     int main()
     {
	   char chr;
	
	printf("Enter a character : ");
	scanf("%c", &chr);
	
	ch < 123 && ch > 97 || chr > 64 && chr < 92 ? printf("Not a special symbol."):printf("Special symbol.");
	return 0;
      }

(b)

       #include<stdio.h>
       int main()
        {
	int year;
	
	printf("Enter a year : ");
	scanf("%d", &year);
	
	year % 4 ? printf("%d is a not a leap year.", year):printf("%d is a leap year.", year);

	return 0;
           }
   
   OR
   
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
(c)
   
    #include<stdio.h>
    int main()
    {
    int a,b,c;
	
    printf("Enter three numbers : ");
    scanf("%d %d %d", &a,&b,&c);
	
    a>b&&a>c?printf("%d is the greatest.", a):(b>a&&b>c?printf("%d is the greatest.", b):printf("%d is the greatest.", c));
    return 0;
    }
	  
(d)	

	#include<stdio.h>
	#include<math.h>
	int main()
	{
    float theta;
    printf("Enter angle in degrees\n");
    scanf("%f",&theta);
    theta=0.0174533*theta;
    if((sin(theta)*sin(theta)+cos(theta)*cos(theta))==1)
    {
        printf("\"sin^2+cos^2=1\" is true");
    }
    else
    {
        printf("\"sin^2+cos^2=1\" is not true");
    }

    return 0;
	}
	

(e)

    #include<stdio.h>
    int main()
    {
    float sal;
    printf("Enter the salary");
    scanf("%d",&sal);
    sal>=25000 && sal<=40000 ?printf("Manager\n"):(sal>=15000 && sal<25000?printf("Accountant\n");:printf("Clerk"));
    return 0;
    }

