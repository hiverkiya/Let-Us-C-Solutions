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
           else if(hard>50 && carbon>=0.7 && tensile<=5600 || hard<=50 && carbon<0.7 && tensile<=5600 || hard<=50 && carbon>=0.7          &&tensile>5600)
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
    else if((x==z) || (y==z) || (x==y))
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
    int r,g,b;
    float c,m,y,k,w1,w2,w3,w_largest;
    printf("Enter the valies of RGB ranging between 0-255 = ");
    scanf("%d %d %d",r,g,b;
    if(r==0 && g==0 && b==0)
    {
    printf("Cyan = 0\n");
    printf("Magenta = 0\n");
    printf("Yellow = 0\n");
    printf("Black = 1\n");
    }
    else
    {
    w1=r/255;
    w2=g/255;
    w3=b/255;
    if(w1>w2 && w1>w3)
    w_largest=w1;
    else if(w2>w1 && w2>w3)
    w_largest=w2;
    else
    w_largest=w3;
    c=((w_largest-(r/255))/w_largest);
    printf("Cyan = %f\n",c);
    m=((w_largest-(g/255))/w_largest);
    printf("Magenta = %f\n",m);
    y=((w_largest-(b/255))/w_largest);
    printf("Yellow = %f\n",y);
    k=w_largest-1;
    printf("Black = %f\n",k);
    }
    return 0;
    }
    

    
   
