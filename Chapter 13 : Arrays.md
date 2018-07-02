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
