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
   else if(hard>50 && carbon>=0.7 && tensile<=5600 || hard<=50 && carbon<0.7 && tensile<=5600 || hard<=50 && carbon>=0.7 &&tensile>5600)
   printf("Grade is 6");
   else
   printf("Grade is 5");
   return 0;
   }
   
   
