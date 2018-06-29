# Chapter-5 Loop Control Instruction
## [A]

       (a)   1
             2
             3
             4
             5
             6
             7
             8
             9
             10
       (b)   2 3 3
       (c)   3 3 1
       (d)   prints it infnite times.
       (e)   prints 10 infinite times.
       (f)   prints nothing.
       
## [B]

   (a)
       
        #include<stdio.h>
         int main()
           {
	      int i,hour, extra;
	      for(i = 1 ; i <= 10 ; i++) 
	       {
              printf("\n");
		printf("Enter the working hour of the employ : ");
		scanf("%d", &hour);
		
		if(hour>40)
		{
			extra = (hour - 40)*12;
			printf("\n%d Rs. is the overtime pay of employee\n", extra);
		}
		else
			printf("\nThis employ has not done overtime.\n");
	  }
	 return 0;
         }
         
   (b)
   
          #include<stdio.h>
          int main()
          {
             int i,fact=1,num;
             scanf("%d",&num);
             printf("Ener a number = ");
             for(i=1;i<=num;i++)
             {
               fact*=num;
              }
              printf("%d",fact);
              return 0;
           }
           
   (c)
   
          #include<stdio.h>
          #include<math.h>
          int main()
          {
            int base,power,d;
            print("Enter value of base = ");
            scanf("%d",&base);
            printf("Enter value of power = ");
            scanf("%d",&power);
            d=pow(base,power);
            printf("%d",d);
            return 0;
          }
           
   (d)
   
           #include<stdio.h>
           int main()
           {
             int i;
             for(i=0;i<=255;i++)
             printf("\n%d = %c",i,i);
             return 0;
           }
           
   (e)
   
           #include<stdio.h>
          int main()
          {
          int i,rem,num=0,x;
          for(i=1;i<=500;i++)
          {
          	num=0;
           x=i;
            while(x)
            {
              rem=x%10;
              num=num+(rem*rem*rem);
              x/=10;
             }
            if(num==i)
            printf("%d is a armstrong number\n",i);
           }
           return 0;
           }

