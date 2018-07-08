# Chapter-13 Arrays

## [A]

    (a)  200 100
    (b)  ASCII Value Table
    (c)  49
    
## [B]


    (a)  int followed by char  is illegal
         No '&' sign in scanf function  
    (b)  No & sign in scanf function
    (c)  No error.
    
## [C]

    (a)  An array is a collection of the same data type placed next to each other in memory.
    (b)  No: Array index is comes inside [ ].
         No: Array index must have a constant, here size is a variable.
         No: c is an int, and it cannot contain an array
    (c)  Third Element.
    (d)  first is array size, second is particular element.
    (e)  
      (1)  True.
      (2)  False.
      (3)  False.
      (4)  True.
      
## [D]

(a)

        #include<stdio.h>
        int main()
         {
           int i,count=0,num;
           int a[25];
           for(i=0;i<25;i++)
           {
             scanf("%d",&a[i]);
           }
           scanf("%d",&num);
           for(i=0;i<25;i++)
           { 
             if(num==a[i])
             count++;
           } 
            if(count>0)
            printf("The number is present %d times",count);
            else
            printf("Number doesn't exit in array");
            return 0;
           }
           
(b)

         #include<stdio.h>
         #define MAX 5

        void selection(int*);
        void bubble(int*);
        void insertion(int*);

         void swap(int*, int*);
         void show(int*); //display the array.

       int main() 
         {
	int a[MAX] = { 5,1,4,2,7 }, b[MAX] = { 5, 2, 3, 9, 0 }, c[MAX] = {6, 23,1, 6, 2};
	printf("\nSelection sort.");
	selection(a);
	show(a);
	printf("\nBubble sort.");
	bubble(b);
	show(b);
	printf("\nInsertion sort.");
	insertion(c);
	show(c);
	return 0;
     }
      void selection(int *a)
      {
	 int i, j;
	for (i = 0; i < MAX; i++)
		for (j = i + 1; j < MAX; j++)
			if (a[i] > a[j])
				swap(&a[i], &a[j]);
     }

        void bubble(int *a)
       {
	   int i, j;
	   for (i = 0; i < MAX; i++)
		for (j = 0; j < MAX - 1; j++)
			if (a[j] > a[j + 1])
				swap(&a[j], &a[j + 1]);
     }
        void insertion(int *a)
       {
	 int key, j, k;

	/* Grabs the next key on each iteration. */
	for (int i = 1; i < MAX; i++)
	{
		/* Selecting the number. */
		key = arr[i];

		/* Finding the position to insert viz. j */
		for (j = 0; arr[j] < key; j++);

		/* Shifting numbers to left. */
		for (k = i; k > j; k--)
			arr[k] = arr[k - 1];

		/* Inserting the number. */
		arr[j] = key;
	      }
       }

          void swap(int *a, int *b)
            {
	         int temp;
	         temp = *a;
	         *a = *b;
	         *b = temp;
            }
         void show(int *a)
           {
	         int i;
	         printf("\n");
	   for (i = 0; i < MAX; i++)
		 printf("%d\t", a[i]);
     	printf("\n");
       }
       
(c)

        #include<stdio.h>
	int main()
	 {
	   int i,j,isPrime;
	   int a[100];
	   for(i=0;i<100;i++)
	    a[i]=i+1;
	    for(i=0;i<100;i++)
	      { 
	        isPrime=1;
		 for(j=2;j<a[i];j++)
		 {
		  if(a[i]%j==0)
		  {
		  isPrime=0;
		  break;
		  }
		 }
		 if(isPrime==1)
		 printf("%d\n",a[i]);
		}
		return 0;
	   }
	   
(d)

       #include<stdio.h>
       int main()
       {
         int i,pos,neg,even,odd;
	 int a[25];
	 for(i=0;i<25;i++)
	 scanf("%d",&a[i]);
	 for(i=0;i<25;i++)
	 {
	   if(a[i]<0)
	    neg++;
	    else if(a[i]>0)
	    pos++;
	    else if(a[i]%2==0)
	    even++;
	    else if(a[i]%2!=0)
	    odd++;
	  }
	  printf("Negatives = %d\n",neg);
	  printf("Positives = %d\n",pos);
	  printf("Even = %d\n",even);
	  printf("Odd = %d\n",odd);
	  return 0;
	  }

(e)

        #include<stdio.h>
	int main()
	{
	  int i,n;
	  printf("Enter size of array = ");
	  scanf("%d",&n);
	  int a[n];
	  for(i=0;i<n;i++)
	  {
	    scanf("%d",&a[i]);
	  }
	  for(i=0;i<n;i+=2)
	  {
	    temp=a[i];
	    a[i]=a[i+1];
	    a[i+1]=temp;
	   }
	   for(i=0;i<n;i++)
	   {
	     printf("%d\n",a[i]);
	   }
	   return 0;
	   }
	   
## [E]

      (a)  Error: There will be a comma before variable in printf function.
      (b)  Error: There will be a comma before variable in printf function.
      (c)  7
           9
           11
           13
           15
      (d)  0
           0
	   0
	   0
	   0
      (e)  3 2 15
      
## [F]

      (a)  No Error.
      (b)  No Error.
      (c)  j is not an pointer. It cannot save address.
      (d)  No Error.
      (e)  i is undeclared.
      
## [G]

      (a)  Other data maybe overwritten.
      (b)  Address of 0th element or base address.
      (c)  Unused elements will be filled with zero's or garbage value.
      (d)  Other data maybe overwritten.
      (e)  Address of the first element of the array.
      (f)  To manipulate parts of an array.
      (g)  0
      
## [H]

      (a)  True.
      (b)  float *ptr;
      (c)  j=*ptr;
      (d)  *( s + 2 )
      
## [I]

(a)

       #include<stdio.h>
       int main()
       {
         int n,i,d=0;
	 printf("Enter size of array = ");
	 scanf("%d",&n);
	 int a[n],b[n];
	 for(i=0;i<n;i++)
	 {
	   scanf("%d",&a[i]);
	 }
	 for(i=n-1;i>=0;i--)
	  {
	    b[d]=a[i];
	    d++;
	  }
	  for(i=0;i<n;i++)
	  {
	   printf("%d\n",b[i]);
	  }
	  return 0;
	  }
	  

(b)

       #include<stdio.h>
       int main()
       {
          int n,i,j;
	  printf("Enter size of array = ");
	  printf("(size must be even");
	  scanf("%d",&n);
	  int a[n];
	  for(i=0;i<n;i++)
	  {
	    scanf("%d",&a[i]);
	  }
	  for(i=0,j=n-1;i<n/2;i++,j--)
	  {
	   if(a[i]==a[j])
	   printf("a[%d] & a[%d] are equal",i,j);
	   else
	   printf("a[%d] & a[%d] are not equal",i,j);
	   }
	   return 0;
	   }
	   
(c)

          #include<stdio.h>
          int main()
          {
	    int i;
	    int a[25];
	    int *ptr;
	    for(i=0;i<25;i++)
	   {
	    scanf("%d",&a[i]);
	   }
	    ptr=&a;
	    for(i=0;i<25;i++)
	  {
		if(*ptr>a[i])
		*ptr=a[i];
	  }
	  printf("%d",*ptr);
	return 0;
         }
	 
(d) 

         #include<stdio.h>
	 int modify(int *);
	 int main()
	 {
	   int i;
	   int a[10]={1,2,3,4,5,6,7,8,9,10};
	   modify(a);
	  for(i=0;i<10;i++)
	   {
	     printf("%d\n",a[i]);
	   }
	   return 0;
	 }
	   int modify(int *a)
	   {
	     int i;
	     for(i=0;i<10;i++)
	     {
	      a[i]=a[i]*3;
	      }
	      return a;
	  }  
	  


       
	
	  
	 


       

          
	   

       

      
	   


          
       
      
	  
	
