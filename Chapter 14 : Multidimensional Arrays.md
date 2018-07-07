# Chapter-14 Multidimensional Arrays
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

(c)

              #include<stdio.h>
	      int main()
	      {
	        int i,j;
		int a[4][4],trans[4][4];
		for(i=0;i<4;i++)
		{
		 for(j=0;j<4;j++)
		 {
		   scanf("%d",&a[i][j]);
		   }
		 |
		 for(i=0;i<4;i++)
		 {
		    for(j=0;j<4;j++)
		    {
		     trans[i][j]=a[j][i];
		     }
		   }
		   for(i=0;i<4;i++)
		   {
		    for(j=0;j<4;j++)
		    {
		     printf("%d ",trans[i][j]);
		     }
		     printf("\n");
		    }
		    return 0;
		    }
		    
(d)

(e)

            1. &u      =  e. F9C
            2. &j      =  b. F9E
            3. pj      =  b. F9E
            4. *pj     =  c. 35
            5. i       =  g. unspecified (60)
            6. pi      =  e. F9C
            7. *pi     =  g. unspecified (25)
            8. (pi+2)  =  i. F9E
            9. (*pi+2) =  g. unspecified (27)
           10.*(pi+2)  =  c. 35
	    
(f)

            1. = j. 2
            2. = g. 1
            3. = None, it prints the address of a[2][0]th element.
            4. = h. 11
            5. = b. 18
            6. = g. 1
            7. = e. 0
            8. = k. 5
            9. = j. 2
           10. = d. 3
	   
(g)

            1. = f. 12
            2. = j. 8
            3. = m. 6
            4. = c. 4
            5. = a. 9
            6. = i. 1
            7. = d. 3
            8. = k. 5
            9. = h. 7
           10. = e. 2
	   
(h)

            #include<stdio.h>
	    int main()
	    {
	       int i,j,count=0;
	       printf("Enter no. of rows & coulumns = ");
	       scanf("%d",&n);
	       int a[n][n];
	       for(i=0;i<n;i++)
	       {
	         for(j=0;j<n;j++)
		 {
		   scanf("%d",&a[i][j]);
		 }
	       }
	       for(i=0;i<n;i++)
	       {
	         for(j=0;j<n;j++)
		 {
		   if(a[i][j]==a[j][i])
		   count++;
		  }
		}
		int d=n*n;
		if(count==d)
		printf("This is Symmetric Matrix");
		else
		printf("This is not a Symmetric Matrix");
		return 0;
		}
		
(i)

               #include<stdio.h>
	       int main()
	       {
	         int i,j;
		 int a[6][6],b[6][6],sum[6][6];
		 for(i=0;i<6;i++)
		 {
		   for(j=0;j<6;j++)
		   {
		     scanf("%d",&a[i][j]);
		    }
		  }
		  for(i=0;i<6;i++)
		 {
		   for(j=0;j<6;j++)
		   {
		     scanf("%d",&b[i][j]);
		    }
		  }
		 for(i=0;i<6;i++)
		 {
		   for(j=0;j<6;j++)
		   {
		     sum[i][j]=a[i][j]+b[i][j];
		    }
		  } 
		  for(i=0;i<6;i++)
		 {
		   for(j=0;j<6;j++)
		   {
		     printf("%d ",sum[i][j]);
		    }
		    printf("\n");
		  }
		  return 0;
		  }
		  
(j)

            #include<stdio.h>
	    int main()
	    {
	      int i,j,k;
	      int a[3][3],b[3][3],c[3][3];
	      for(i=0;i<3;i++)
	      {
	       for(j=0;j<3;i++)
	       {
	         scanf("%d",&a[i][j]);
		}
	       }
	        for(i=0;i<3;i++)
	      {
	       for(j=0;j<3;i++)
	       {
	         scanf("%d",&b[i][j]);
		}
	       }
	       	for (i = 0; i<3; i++)
	       {
	     	for (j = 0; j<3; j++)
		{
			c[i][j] = 0;
			for (k = 0; k<3; k++)
			{
				c[i][j] = ans[i][j] + a[i][k] * b[k][j];
			}
		}
	       }
	       for(i=0;i<3;i++)
	       {
	        for(j=0;j<3;j++)
		{
		 printf("%d ",c[i][j]);
		}
		printf("\n");
	     }
	     return 0;
	     }
		
	     
	       
		  
		 
