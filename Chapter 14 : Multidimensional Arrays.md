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

	#include<stdio.h>
	#include<conio.h>
	#include<Windows.h>

	#define FALSE 0
	#define TRUE 1

	//scan codes for arrow keys.
	#define UP 72
	#define DOWN 80
	#define LEFT 75
	#define RIGHT 77

	void gotoxy(short, short);
	void box(short, short, short, short);
	void update(short, short, short, short, int *a);
	int getkey();
	int check(int *a);
	void action(int key, int a[4][4]);
	void swap(int*, int*);

	int main()
	{
	int a[4][4] = {
		1, 4, 15, 7,
		8, 10, 2, 11,
		14, 3, 6, 13,
		12, 9, 5, 32
	};
	int key, flag = FALSE;

	gotoxy(30, 20);
	printf("\nArrange the numbes in ascending order.\nPress any key to start. . .");
	_getch();
	system("cls");//clrscr(); in TurboC++
	box(0, 0, 24, 8);
	while (flag == FALSE)//Game ends when flag becomes TRUE
	{
		update(0, 0, 24, 8, (int*)a);
		key = getkey();
		action(key, a);// It moves the numbers
		flag = check((int*)a);/*It make flag TRUE on completion of game*/
	}
	system("cls");
	gotoxy(30, 20);
	printf("\nYou've done it dude.!!\nExiting. . . ");
	_getch();
	_getch();
	return 0;
	}

	//It prints the numbers in the boxes.
	void update(short x1, short y1, short x2, short y2, int *a)
	{
	int i, j, num, k = 0;
	for (j = y1; j < y2; j++)//row
	{
		for (i = x1; i < x2; i++)//col
		{
			if (i > x1 && i < x2 && j > y1 && j < y2)
			{
				if ((i + 3) % 6 == 0 && j % 2 == 1)
				{
					gotoxy(i, j);
					num = a[k];
					if (num == 32)
						printf("  ");
					else
						printf("%d", num);
					k++;
				}
			}
		}
	}
	}

	//It draw box.
	void box(short x1, short y1, short x2, short y2)
	{
	int i, j;
	for (i = x1; i <= x2; i++) // col
	{
		for (j = y1; j <= y2; j++) //row
		{
			/*====printing corners========*/
			if (i == x1 && j == y1)
			{
				gotoxy(i, j);
				printf("%c", 218);
			}
			if (i == x2 && j == y1)
			{
				gotoxy(i, j);
				printf("%c", 191);
			}
			if (i == x1 && j == y2)
			{
				gotoxy(i, j);
				printf("%c", 192);
			}
			if (i == x2 && j == y2)
			{
				gotoxy(i, j);
				printf("%c", 217);
			}
			/*================================*/


			if (i < x2 && i > x1)
			{
				if ((i) % 6 == 0)//Vertical division coerners
				{
					if (j == y1)
					{
						gotoxy(i, j);
						printf("%c", 194); //T
					}
					if (j == y2)
					{
						gotoxy(i, j);
						printf("%c", 193);//Reverse T
					}
					if (j == y1 + 2 || j == y1 + 4 || j == y1 + 6)
					{
						gotoxy(i, j);
						printf("%c", 197);//+
					}
				}
				else if (j % 2 == 0)// Horizontal line
				{
					gotoxy(i, j);
					printf("%c", 196);
				}
			}



			if (j > y1 && j < y2)
			{
				if ((j % 2 == 0))
				{
					if (i == x1)
					{
						gotoxy(i, j);
						printf("%c", 195);//Rotate left T
					}
					if (i == x2)
					{
						gotoxy(i, j);
						printf("%c", 180);//Rotate right T
					}
				}
				else if (i % 6 == 0)
				{
					gotoxy(i, j);
					printf("%c", 179);//Vertical lines
				}
			}
		}
	}
	}
	
	//gotoxy in compilers other than TurboC++
	void gotoxy(short col, short row)
	{
	HANDLE h = GetStdHandle(STD_OUTPUT_HANDLE);
	COORD position = { col, row };
	SetConsoleCursorPosition(h, position);
	}

	int getkey()
	{
	int ch;
	ch = _getch();
	if (ch == 0)
		ch = _getch();
	return ch;
	}

	//It check if the puzzle is solved or not.
	int check(int *a)
	{
	int i;
	for (i = 0; i < 15; i++)
		if (a[i] > a[i + 1])
			return FALSE;
	return TRUE;
	}

	//It moves the number.
	void action(int key, int a[4][4])
	{
	int i, j;
	for (i = 0; i < 4; i++)
		for (j = 0; j < 4; j++)
			if (a[i][j] == 32)
				goto BREAK;
	BREAK:
	switch (key)
	{
	case RIGHT:
		if (j - 1 < 0) 
			return;
		swap(&a[i][j], &a[i][j - 1]);/*Moves the botton to right*/
		return;
	case DOWN:
		if (i - 1 < 0)
			return;
		swap(&a[i][j], &a[i - 1][j]);/*Moves the botton down*/
		return;
	case LEFT:
		if (j + 1 > 3)
			return;
		swap(&a[i][j], &a[i][j + 1]);/*Moves the botton left*/
		return;
	case UP:
		if (i + 1 > 3)
			return;
		swap(&a[i][j], &a[i + 1][j]);/*Moves the botton up*/
		return;
	default:
		return;
	}
	}

	void swap(int *a, int *b)
	{
	int temp;
	temp = *a;
	*a = *b;
	*b = temp;
	}

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
		
(k)

	#include<stdio.h>
	#include<conio.h>

	void shift(int *base)
	{
	int *web, fir, sec, i;
	web = base;
	fir = *base;//saving first value in fir variable
	sec = *(base + 1);//saving second value insec variable

	for (i = 0; i<3; i++)//shifting the values by saving them in next to next addresses
		*(web + i) = *((base + 2) + i);

	*(web + 3) = fir;
	*(web + 4) = sec;
	}

	int main()
	{
	int a[5], i;

	printf("Enter 5 numbers : ");
	for (i = 0; i<5; i++)//scanning values
		scanf("%d", &a[i]);

	shift(a);//calling function

	printf("\n\nList after shifting it's rows by two positions.\n\n");
	for (i = 0; i<5; i++)//printing values after shifting

		printf("%d ", a[i]);
	_getch();
	return 0;
	}
(l)
	
	#include<conio.h>
	#include<stdio.h>

	int a[20][20],m;
	int determinant(int f[20][20],int a);
	int main()
	{
 	 int i,j;
 	 printf("\n\nEnter order of matrix : ");
 	 scanf("%d",&m);
 	 printf("\nEnter the elements of matrix\n");
 	 for(i=1;i<=m;i++)
 	 {
 	 for(j=1;j<=m;j++)
 	 {
 	 printf("a[%d][%d] = ",i,j);
 	 scanf("%d",&a[i][j]);
 	 }
 	 }
 	 printf("\n\n---------- Matrix A is --------------\n");    
 	 for(i=1;i<=m;i++)
   	  {
          printf("\n");
          for(j=1;j<=m;j++)
          {     
               printf("\t%d \t",a[i][j]);
          }
  	   }
 	 printf("\n \n");
 	 printf("\n Determinant of Matrix A is %d .",determinant(a,m));
 	 getch();
	}

	int determinant(int f[20][20],int x)
	{
	  int pr,c[20],d=0,b[20][20],j,p,q,t;
	  if(x==2)
 	 {
 	   d=0;
  	  d=(f[1][1]*f[2][2])-(f[1][2]*f[2][1]);
    return(d);
 	  }
 	 else
  	{
    for(j=1;j<=x;j++)
    {        
      int r=1,s=1;
      for(p=1;p<=x;p++)
        {
          for(q=1;q<=x;q++)
            {
              if(p!=1&&q!=j)
              {
                b[r][s]=f[p][q];
                s++;
                if(s>x-1)
                 {
                   r++;
                   s=1;
                  }
               }
             }
         }
     for(t=1,pr=1;t<=(1+j);t++)
     pr=(-1)*pr;
     c[j]=pr*determinant(b,x-1);
     }
     for(j=1,d=0;j<=x;j++)
     {
       d=d+(f[1][j]*c[j]);
      }
     return(d);
  		 }
	}

(m) 

	#include<stdio.h>
	#include<conio.h>
	#include<math.h>

	int main()
	{
	int a[15] = { -6,-12,8,13,11,6,7,2,-6,-9,-10,11,10,9,2 },
		i, sum = 0;
	float min, hell = 0, sd, n = 0;

	printf("Your data is :");

	for (i = 0; i<15; i++)//sum of the data
	{
		printf(" %d,", a[i]);
		sum = sum + a[i];
		n++;
	}
	min = sum / n;//calculating mean of the data.

	for (i = 0; i<15; i++)//finding standard deviation of the data
		hell = hell + pow((a[i] - min), 2);

	sd = (sqrt(hell)) / n;

	printf("\n\nMean of the data = %f\n\nStandard deviation of data = %f", min, sd);

	_getch();
	return 0;
	}
(o)

	#include<stdio.h>
	#include<conio.h>
	#include<math.h>

	int main()
	{
	float x[11][2] = {
		34.22, 102.43,
		39.87, 100.93,
		41.85, 97.43,
		43.23, 97.81,
		40.06, 98.32,
		53.29, 98.32,
		53.29, 100.07,
		49.12, 91.59,
		40.71, 94.85,
		55.15, 94.65,

	},
		xysum = 0, xsum = 0, ysum = 0, x2sum = 0, y2sum = 0, n = 11, r;
	int i;

	for (i = 0; i<11; i++)
	{
		xsum = xsum + x[i][0];
		ysum = ysum + x[i][0];
		xysum = xysum + x[i][0] * x[i][1];
		x2sum = x2sum + x[i][0] * x[i][0];
		y2sum = y2sum + x[i][1] * x[i][1];
	}

	r = (xysum - xsum*ysum) / (sqrt((n*x2sum - xsum*xsum)*(n*y2sum - ysum*ysum)));

	printf("Coefficient of correlation (r) = %f", r);

	_getch();
	return 0;

	}
(p)

	#include<stdio.h>
	#include<conio.h>

	#define n 10

	int main()
	{
	double set[n][2] = {
		3.0, 1.5,
		4.5, 2.0,
		5.5, 3.5,
		6.5, 5.0,
		7.5, 6.0,
		8.5, 7.5,
		8.0, 9.0,
		9.0, 10.5,
		9.5, 12.0,
		10.0, 14.0
	};
	double help[n], sx = 0, sy = 0, sxy = 0, sx2 = 0, a, b, xbar, ybar;
	int i;

	for (i = 0; i < n; i++)
	{
		sx += set[i][0];
		sy += set[i][1];
		sxy += set[i][0] * set[i][1];
		sx2 += set[i][0] * set[i][0];
	}
	
	xbar = sx / n;
	ybar = sy / n;

	b = (n*sxy - sx*sy) / (n*sx2 - sx*sx);
	a = ybar - b*xbar;

	printf("\nRequired equation is\n\ny = %.2lf + %.2lfx", a, b);
	_getch();
	return 0;
	}
(q)

	#include<stdio.h>
	#include<conio.h>
	#include<math.h>
	int main()
	{
	float x[10], y[10], dis = 0;
	int i, j;
	printf("Enter the coordinates of 10 points ~ \n\n");
	
	for (i = 0; i<10; i++)
		scanf("%f%f", &x[i], &y[i]);

	for (i = 0; i<10; i++)
		dis = dis + sqrt(pow((x[i + 1] - x[i]), 2) + pow((y[i + 1] - y[i]), 2));

	printf("The total distance between first and last point is %f", dis);

	_getch();
	return 0;
	}

(n) 	

	#include<stdio.h>
	#include<conio.h>
	#include<math.h>
	int main()
	{
	float a[6][4] = {
		//	Plot No. 	 a      b      angle
		1,		137.4,	80.9,	0.78,
		2,		155.2,	92.62,	0.89,
		3,		149.3,	97.93,	0.89,
		4, 		160.0,	100.25,	1.35,
		5, 		155.6,	68.95,	1.25,
		6,		149.7,	120.0,	1.75,
	},
		ar[6],//areas
		max;
	int i, x = 0;//plot no.

	for (i = 0; i<6; i++)
	{
		ar[i] = (0.5)*a[i][1] * a[i][2] * sin(a[i][3]);
		if (max<ar[i])
		{
			max = ar[i];
			x = a[i][0];
		}
	}

	printf("\n\n\nAreas of the triangles are ~ ");

	for (i = 0; i<6; i++)
		printf("\n%f : %2f,", a[i][0], ar[i]);

	printf("\n\n\nNumber %d. triangle has maximum area of %2f.", x, max);

	_getch();
	return 0;
	}
(r)

	#include<stdio.h>
	#include<conio.h>

	#define MAX 10

	void lAdd(int *l, int *q, int *r, int num);
	void rAdd(int *l, int *q, int *r, int num);
	void show(int *q, int *rside);
	int rFetch(int *l, int *q, int *r);
	int lFetch(int *l, int *q, int *r);

	int main()
		{
	int que[MAX];
	int left, right;
	left = right = -1;

	rAdd(&left, que, &right, 10);
	rAdd(&left, que, &right, 20);
	rAdd(&left, que, &right, 30);
	show(que, &right);

	lAdd(&left, que, &right, 5);
	show(que, &right);

	lFetch(&left, que, &right);
	show(que, &right);

	rFetch(&left, que, &right);
	show(que, &right);

	_getch();
	return 0;
	}

	/*Insertion from right*/
	void rAdd(int *lside, int *q, int *rside, int num)
	{
	if (*rside == MAX - 1)
	{
		printf("\nDequeue is full, no more insertion is possible.\n");
		return;
	}

	if (*rside == -1)
		*rside = 0;
	else
		(*rside)++;
	q[*rside] = num;
	}

	/*Insertion from left*/
	void lAdd(int *lside, int *q, int *rside, int num)
	{
	int i;

	if (*rside == MAX - 1)
	{
		printf("\nDequeue is full, no more insertion is possible.\n");
		return;
	}

	for (i = *rside; i >= 0; i--)
		q[i+1] = q[i];

	q[0] = num;

	if (*lside == -1)
		*lside = 0;
	(*rside)++;
	}

	/*Dislays the list*/
	void show(int *q, int *rside)
	{
	int i;

	printf("\n\nList\n");
	for (i = 0; i <= *rside; i++)
		printf("%d\t", q[i]);
	printf("\n\n");
	}

	/*Retrieval from left*/
	int lFetch(int *lside, int *q, int *rside)
	{
	int item = q[0], i;
	if (*rside == -1)
	{
		printf("\nList is empty.\n");
		return NULL;
	}

	for (i = 0; i < *rside; i++)
		q[i] = q[i + 1];

	(*rside)--;
	return item;
	}

	/*Retrieval from right*/
	int rFetch(int *lside, int *q, int *rside)
	{
	if (*rside == -1)
	{
		printf("\nList is empty.\n");
		return NULL;
	}
	int item = q[*rside];
	(*rside)--;
	return item;
	}
(s)

	#include<stdio.h>
	#include<conio.h>

	static int error = 0;

	void grd(int *a)//checking the 3x3 grids
	{
	int i, j, x, p, sum = 0;
	for (p = 0; p <= 54; p += 27)/*Moving dowbn the grid*/
	{
		for (x = 0; x <= 6; x += 3)/*Moving right of the grid*/
		{
			sum = 0;
			for (i = 0; i <= 18; i += 9)//Moving down the column in a gird
				for (j = 0; j <= 2; j++)//Moving right of row ina grid
					sum += *(a + i + j + x + p);
			if (sum != 45)
			{
				error += 1;
				return;
			}
		}
	}
	}

	void row(int *a)//checking the rows
	{
	int i, j, sum = 0;
	for (i = 0; i <= 72; i += 9)/*Moving donw the row*/
	{
		sum = 0;//reinitialisation of sum
		for (j = 0; j <= 8; j++)//Moving right of the row
			sum += *(a + i + j);
		if (sum != 45)
		{
			error += 1;//if there's error
			return;
		}

	}

	}

	void col(int *a)//checking the columns
	{
	int i, j, sum = 0;
	for (i = 0; i <= 8; i++)//Moving right of the column
	{
		sum = 0;//reinitialisation of sum
		for (j = 0; j <= 72; j += 9)//Moving down of the column
			sum += *(a + i + j);
		if (sum != 45)
		{
			error += 1;//if ther's error
			return;
		}
	}

	}

	int main()
	{
	int gam[9][9] = {
		5,3,4,6,7,8,9,1,2,
		6,7,2,1,9,5,3,4,8,
		1,9,8,3,4,2,5,6,7,
		8,5,9,7,6,1,4,2,3,
		4,2,6,8,5,3,7,9,1,
		7,1,3,9,2,4,8,5,6,
		9,6,1,5,3,7,2,8,4,
		2,8,7,4,1,9,6,3,5,
		3,4,5,2,8,6,1,7,9
	};
	
	grd(gam[0]);
	row(gam[0]);
	col(gam[0]);
	
	if (error)
		printf("\n\nThe Solution of your sudoku is wrong.\n");
	else
		printf("\n\nSolution of you sudoku is right.\n");
	
	_getch();
	return 0;
	}
	     
	       
		  
		 
