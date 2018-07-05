# Chapter-13 Multidimensional Arrays
## [A]

        (a)  [Address of 1st 1d Array] [Garbage Value] 1
	(b)  2
             4
	     3
	     6
	     8
	     5
	     3
	     5
	     1
	(c)  2 2
	     4 4
	     3 3
	     6 6
	     8 8
	     5 5
	     3 3
	     5 5
	     1 1
	     
## [B]

        (a)  missing subscript in initialization.
	(b)  missing subscript in initialization.
	
## [C]

(a)

         #include<stdio.h>
         int main()
         {
	 int threedimen[3][2][3] = {
		{
			1, 2, 3,
			4, 5, 6
		},
		{
			7, 8, 9,
			10, 11, 12
		},
		{
			13, 14, 15,
			16, 17, 18
		}
	 };
	  printf("\nFirst element : %d", threedimen[0][0][0]);
	   printf("\nLast element : %d", threedimen[2][1][2]);
	  return 0;
          }
	     
(b)

            #include<stdio.h>
           int main()
              {
	      int arr[5][5] = {
		1,2,3,4,5,
		6,7,8,9,10,
		11,12,13,14,15,
		16,17,18,19,20,
		21,22,23,24,25
	     };
	     int i,j,max;
	     max=arr[0];
	     for(i=0;i<5;i++)
	     {
	       for(j=0;j<5;j++)
	       {
	         if(a[i][j]>max)
		 max=a[i][j];
		 }
		}
		printf("Maximum Number is = %d",max);
		return 0;
	      }
