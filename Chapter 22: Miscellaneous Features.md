# [Chapter 22: Miscellaneous Features] Solutions

## [A]
  
    (a) 0 1 2
    (b) 1.0
    (c) 4

## [B]

    (a) No Error
    (b) There are two methods to invoke a function,
	(*func)();
	func();
    (c) No Error

## [C]

  (a)
  
   	#include<stdio.h>
	#include<conio.h>

	float one(int, int);
	float two(int, int);
	float three(int, int);
	float four(int, int);

	int main()
	{
	float(*ptr[4])(int, int);
	float a, b, c, d;
	ptr[0] = one;
	ptr[1] = two;
	ptr[2] = three;
	ptr[3] = four;
	a = ptr[0](1, 2);
	b = ptr[1](2, 4);
	c = ptr[2](6, 3);
	d = ptr[3](22, 7);
	printf("a : %f\tb : %f\n", a, b);
	printf("c : %f\td : %f\n", c, d);
	_getch();
	return 0;
	}
	float one(int a, int b)
	{
	float r;
	r = (float)a / b;

	return r;
	}
	float two(int x, int y)
	{
	float ans;
	ans = (float)x / y;
	return ans;
	}
	float three(int i, int j)
	{
	float a;
	a = (float)i / j;
	return a;
	}
	float four(int m, int n)
	{
	return ((float)m / n);
	}
  (b)
  
  	#include<stdio.h>
	#include<conio.h>
	#include<stdarg.h>

	void type(int, ...);

	int main()
	{	
	type(5, 4, 6, 3, 6, 7);
	return 0;
	}

	void type(int point, ...)
	{
	if (point < 1)
	{
		printf("Nothing can be draw.");
		return;
	}
	switch (point)
	{
	case 1:
		printf("A point can be drawn.\n");
		break;
	case 2:
		printf("A line can be drawn.\n");
		break;
	case 3:
		printf("A triangle can be drawn.\n");
		break;
	case 4:
		printf("A rectangle can be drwan.\n");
		break;
	case 5:
		printf("A pentagon can be drawn.\n");
		break;
	case 6:
		printf("A hexagon can be drawn.\n");
		break;
	default:
		printf("A polygon can be drawn.\n");
	}
	}
  (c)
  
  	#include<stdio.h>
	#include<conio.h>
	#include<stdarg.h>
	#include<Windows.h>

	#define MAX 5

	typedef struct date
	{
	unsigned d : 5;
	unsigned m : 4;
	unsigned y : 12;
	}EMP;

	void swap(EMP*, EMP*);

	int main()
	{

	int i, j;
	EMP e[10], a[10];
	e[0].y = 2010; e[0].m = 12; e[0].d = 10;
	e[1].y = 1990; e[1].m = 3; e[1].d = 23;
	e[2].y = 1995; e[2].m = 4; e[2].d = 13;
	e[3].y = 2001; e[3].m = 1; e[3].d = 13;
	e[4].y = 1990; e[4].m = 3; e[4].d = 20;
	e[5].y = 1992; e[5].m = 6; e[5].d = 19;

	for (i = 0; i < MAX; i++)
		a[i] = e[i];

	for (i = 0; i < MAX; i++)
	{
		for (j = i + 1; j < MAX; j++)
		{
			if (a[j].y < a[i].y)
				swap(&a[i], &a[j]);
			if (a[j].y == a[i].y)
			{
				if (a[j].m < a[i].m)
					swap(&a[i], &a[j]);
				if (a[j].m == a[i].m)
					if (a[j].d < a[i].d)
						swap(&a[i], &a[j]);
			}
		}
	}

	system("cls");
	for (i = 0; i <= 4; i++)
	{
		printf("\nEmplyee no. %d : ", i + 1);
		printf("%2d/%2d/%4d", a[i].d, a[i].m, a[i].y);
	}
	_getch();
	return 0;
	}
	void swap(EMP *a, EMP *b)
	{
	EMP c;
	c = *a;
	*a = *b;
	*b = c;
	}
  (d)
  
  	#include<stdio.h>
	#include<conio.h>
	#include<Windows.h>

	#define MAX 2

	int main()
	{
	enum sex { male, female };
	enum level { major, minor };
	typedef struct people
	{
		enum sex gender;
		enum level age_level;
		char policy_name[10];
		unsigned int duration_in_year;
	} PEOPLE;
	PEOPLE p[MAX];
	int i, enm;
	for (i = 0; i < MAX; i++)
	{
		printf("\nEnter the gender (male = 0 or female = 1) : ");
		scanf("%d", &enm);
		enm ? (p[i].gender = female) : (p[i].gender = male);
		printf("\nEnter the age status (major = 0 or minor = 1) : ");
		scanf("%d", &enm);
		enm ? (p[i].age_level = minor) : (p[i].age_level = major);

		//Clearing input stream
		while (getchar() != '\n');

		printf("\nEnter name of the customer : ");
		gets_s(p[i].policy_name);
		printf("\nEnter the duration (in years) : ");
		scanf("%d", &p[i].duration_in_year);
	}
	system("cls");
	for (i = 0; i < MAX; i++)
	{
		printf("\n%d\t%d", p[i].gender, p[i].age_level);
		printf("\t%s\t%d", p[i].policy_name, p[i].duration_in_year);
	}
	_getch();
	return 0;
     }
