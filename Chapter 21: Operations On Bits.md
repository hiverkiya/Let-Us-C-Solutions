# [Chapter 21: Operations On Bits] Solutions

# [A] 
  
    (a) 
    
      #include<stdio.h>
      #include<conio.h>

      #define _BV(x) 1<<x

    int main()
    {
	unsigned int color, j, k, andmask;
	int i;
	printf("\nEnter the number : ");
	scanf("%u", &color);
	for (i = 0; i <= 6; i++)
	{
		j = i;
		andmask = _BV(j);
		puts("");
		k = color & andmask;
		if (k > 0)
		{
			switch (i)
			{
			case 0:
				printf("Voilet, ");
				break;
			case 1:
				printf("Indigo, ");
				break;
			case 2:
				printf("Blue, ");
				break;
			case 3:
				printf("Green, ");
				break;
			case 4:
				printf("Yellow, ");
				break;
			case 5:
				printf("Orange, ");
				break;
			case 6:
				printf("Red, ");
				break;
			default:
				break;
			}
		}
	}
	_getch();
	return 0;
    }
(b)

    #include<stdio.h>
    #include<conio.h>
    #include<windows.h>
    #include<math.h>

    #define _BV(x) 1<<x

    //Binary To Decimal
    int bintodec(int *);
    void initinfo(int *);
    void addinfo(int*);

    int main()
    {
	int i, information[10], eng_daily, up_tabloid, regional;
	eng_daily = up_tabloid = regional = 0;
	unsigned int andmask, j;
	for (i = 0; i <= 9; i++)
	{
		printf("\nRespondent number %d\n", i + 1);

		addinfo(&information[i]);
		//	000100100	(people that reads english(3) daily(6),)
		andmask = _BV(2) | _BV(5);
		j = information[i] & andmask;
		if (j == andmask)
			eng_daily++;

		//	100000001	(people with Upper(0) class and tabloid(8))
		andmask = _BV(0) | _BV(8);
		j = information[i] & andmask;
		if (j == andmask)
			up_tabloid++;

		//	000001000 (people that reads in regional(5))
		andmask = _BV(3);
		j = information[i] & andmask;
		if (j == andmask)
			regional++;
	}

	printf("\nStatical Data :-\n");
	printf("\nPersons read English newspaper : %d", eng_daily);
	printf("\nPersons belongs to Upper class and read Tabloid are : %d", up_tabloid);
	printf("\nPersons read newspaper in regional language are : %d", regional);
	_getch();
	return 0;
    }

    int bintodec(int *num)
    {
	int i, dec = 0;
	for (i = 0; i <= 8; i++)
		dec += num[i] * (int)pow(2, 8 - i);
	return dec;
    }

    void initinfo(int *information)
    {
	int i;
	for (i = 0; i <= 8; i++)
		information[i] = 0;
      }

    void addinfo(int *information)
    {
	int choice, info[9];
	printf("\nChoose your economical class\n");
	printf("1. Upper Class\n2. Middle Class\n");
	printf("3. Lower Class\n");
	scanf("%d", &choice);
	initinfo(info);
	switch (choice)
	{
	case 1:
		info[0] = 1;
		break;
	case 2:
		info[1] = 1;
		break;
	case 3:
		info[2] = 1;
	default:
		break;
	}
	printf("\nChoose your language\n");
	printf("1. English\n2. Hindi\n3. Regional\n");
	scanf("%d", &choice);
	switch (choice)
	{
	case 1:
		info[3] = 1;
		break;
	case 2:
		info[4] = 1;
		break;
	case 3:
		info[5] = 1;
		break;
	default:
		break;
	}
	printf("\nChoose your newspaper category\n");
	printf("\n1. Daily\n2. Supplement\n3. Tabloid\n");
	scanf("%d", &choice);
	switch (choice)
	{
	case 1:
		info[6] = 1;
		break;
	case 2:
		info[7] = 1;
		break;
	case 3:
		info[8] = 1;
		break;
	default:
		break;
	}
	*information = bintodec(info);
	system("cls");
      }
(c)

    #include<stdio.h>
    #include<conio.h>
    #include<windows.h>
    #include<math.h>

    #define _BV(x) 1<<x

    int bintodec(int*);
    void initinfo(int*);
    void addinfo(int *);

    int main()
    {
	int game, i, count = 0;
	unsigned int andmask, j;
	addinfo(&game);
	for (i = 0; i <= 8; i++)
	{
		andmask = _BV(i);
		j = game & andmask;
		if (j == andmask)
			count++;
	}
	if (count >= 5)
		printf("\nYou are eligible for champions trophy.\n");
	else
		printf("\nYou aren't eligible for champions trophy.\n");
	_getch();
	return 0;
  		}

    int bintodec(int *num)
    {
	int i, dec = 0;
	for (i = 0; i <= 8; i++)
		dec += num[i] * (int)pow(2, 8 - i);
	return dec;
    }

    void initinfo(int *information)
    {
	int i;
	for (i = 0; i <= 8; i++)
		information[i] = 0;
    }

    void addinfo(int *game)
    {
	int info[9], i;
	printf("1. Cricket\n2. Basketball\n");
	printf("3. Football\n4.Hockey\n");
	printf("5.Lawn Tennis\n6.Table Tennis\n");
	printf("7.Carom\n8.Chess\n9.Kabaddi");
	printf("\nEnter the number of winning of games.");
	printf("Answer given should be in the form of 0 or 1.");
	printf("And should be given\n one by one for each game.\n");
	for (i = 0; i <= 8; i++)
		scanf("%d", &info[i]);
	*game = bintodec(info);
    }
(d)

    18 = (10010)binary

    here last four bits represent the type of the animal so, and first represent its nutrition method.

      0th bit = canine
    1st bit = feline
      2nd bit = cetacean
      3rd bit = marsupial
    4th bit = Herbivorous or carnivorous.

    This is an "herbivorous" animal of "feline" family.
(e)

    #include<stdio.h>
    #include<conio.h>
    #include<math.h>

    #define _BV(x) (1<<x)

    typedef unsigned short int Time;

    void time(Time, int*, int*, int*);

    int main()
    {
	Time t = 2081;
	/*Its Binary equivalent is 
	00001 000001 00001
	So, first bit of hr, min and sec are
	1, so their value will be 2^0, i.e. 1
	*/
	int hr = 0, min = 0, sec = 0;
	time(t, &hr, &min, &sec);
	printf("Hour: %d\nMin: %d\nSec: %d\n", hr, min, sec);
	return 0;
    }

    void time(Time t, int *hr, int *min, int *sec)
    {
	int i;
	for (i = 0; i < 16; i++)
	{
		if (t & _BV(i))
		{
			if (i < 5)
				*sec += int(pow(2, i));
			else if (i > 10)
				*hr += int(pow(2, i - 11));
			else
				*min += int(pow(2, i - 5));
		}
	}

    }
(f)

    #include<stdio.h>
    #include<conio.h>
    #include<math.h>

    #define _BV(x) (1<<x)

    void showinfo(int);

    int main()
    {
	int rnum, search;
	int data[] = { 273, 548, 786, 1096 };
	printf("\nEnter the room number : ");
	scanf("%d", &rnum);

	for (int i = 0; i < 4; i++)
	{
		search = 0;
		for (int j = 8; j < 16; j++)
			if (data[i] & _BV(j))
				search += int(pow(2, j - 8));
		if (rnum == search)
		{
			showinfo(data[i]);
			break;
		}
	}
	_getch();
	return 0;
    }

    void showinfo(int a)
    {
	int search = 0;
	for (int i = 0; i < 16; i++)
	{
		//If a non zero bit is encountered
		if (a & _BV(i))
		{
			if (i < 4)
			{
				printf("\n\nYear: ");
				switch(i)
				{
				case 0:
					printf("First\n");
					break;
				case 1:
					printf("Second\n");
					break;
				case 2:
					printf("Thrid\n");
					break;
				case 3:
					printf("Fourth\n");
				default:;
				}
			}
			else if (i > 7)
				/*calculating room number*/
				search += int(pow(2, i - 8));
			else
			{
				printf("Branch: ");
				switch (i)
				{
				case 4:
					printf("Mechanical\n");
					break;
				case 5:
					printf("Chemical\n");
					break;
				case 6:
					printf("Electronics\n");
					break;
				case 7:
					printf("IT\n");
				default:;

				}
			}
		}
	}
	printf("Room Number: %d\n", search);
    }

(g)

      k = 35	l = -36	m = 0
      n = 97	o = 260	p = 1

# [B]

  (a)
  
  		0101 1010
   		5       A

		1100 0011
  		  C      3

		1010 1010 0111 0101
  		 A     A        7       5

		1111 0000 0101 1010
  		 F        0      5         A 
  (b)
  
  	que: a = a|3
	ans: a |= 3

	que: a = a & 0x48
	ans: a &= 0x48

	que: b = b^0x22
	ans: b ^= 0x22

	que: c = c << 2
	ans: c <<= 2

	que: d = d >> 4
	ans: d >>= 4
  (c)
  
  	#include<stdio.h>
	#include<conio.h>
	#include<Windows.h>
	#include<math.h>

	#define _BV(x) 1<<x

	int checkbits(int, int, int);

	int main()
	{
	int status;
	status = checkbits(14, 3, 3);
	if (status)
		printf("Required bits are ON\n");
	else
		printf("Required bits are OFF\n");
	_getch();
	return 0;
	}

	int checkbits(int x, int p, int n)
	{
	unsigned int andmask = 0;
	int i, j;
	for (i = 0, j = p; i < n; i++, j--)
		andmask |= _BV(j);
	if ((x & andmask) == andmask)
		return 1;
	else
		return 0;
	}
  (d)
  
  	#include<stdio.h>
	#include<conio.h>
	#include<windows.h>
	#include<math.h>

	#define _BV(x) 1<<x

	int checkbits(unsigned char num);

	int main()
	{
	int status;
	status = checkbits(200);
	if (status)
		printf("Required bits are ON\n");
	else
		printf("Required bits are OFF\n");
	_getch();
	return 0;
	}

	int checkbits(unsigned char num)
	{
	unsigned char andmask;
	andmask = _BV(7) | _BV(6) | _BV(3);
	if ((num & andmask) == andmask)
		return 1;
	else
		return 0;
	}
  (e)
  
  	#include<stdio.h>
	#include<conio.h>
	#include<Windows.h>
	#include<math.h>

	#define _bv(x) 1<<x
	#define _ls(x,y) x<<y
	#define _rs(x,y) x>>y

	typedef unsigned short int Store;

	void bitexchange(Store*);

	int main()
	{
	Store num;
	printf("Enter number : ");
	scanf("%hu", &num);
	printf("Before exchange\n");
	printf("num : %u\n", num);
	bitexchange(&num);
	printf("After Exchange its bytes :-\n");
	printf("num : %u\n", num);
	_getch();
	return 0;
	}

	void bitexchange(Store *num)
	{
	unsigned char left, right;

	//	First byte (8-bits) goes to left side.
	left = _ls(*num, 8);

	//Second byts(8 - bits) goes to right side.
	right = _rs(*num, 8);

	*num = 0;
	*num = right | left;
	}
  (f)
  
  	#include<stdio.h>
	#include<conio.h>
	#include<windows.h>
	#include<math.h>

	#define _bv(x) 1<<x
	#define _ls(x,y) x<<y
	#define _rs(x,y) x>>y

	typedef unsigned char Bit;

	void bitexchange(Bit*);

	int main()
	{
	Bit num;
	printf("\nEnter the number : ");
	scanf("%hhd", &num);
	printf("\nBefore shifting\n");
	printf("\nnum : %d", num);
	bitexchange(&num);
	printf("\nAfter exchange");
	printf("\nnum : %d\n", num);
	_getch();
	return 0;
	}

	void bitexchange(Bit *num)
		{
	Bit left, right;
	left = _ls(*num, 4);
	right = _rs(*num, 4);
	*num = 0;
	*num = right | left;
	}
  (g)
  
  	#include<stdio.h>
	#include<conio.h>
	#include<windows.h>
	#include<math.h>

	#define _BV(x) 1<<x

	typedef unsigned char Bit;

	void oddbiton(Bit*);

	int main()
	{
	Bit num;
	printf("Enter the number : ");
	scanf("%hhd", &num);
	oddbiton(&num);
	_getch();
	return 0;
	}

	void oddbiton(Bit *num)
	{
	Bit andmask = 0;
	int i;
	for (i = 1; i < 8; i += 2)
		andmask |= _BV(i);
	*num |= andmask;
	}
  (h)
  
  	#include<stdio.h>
	#include<conio.h>
	#include<windows.h>
	#include<math.h>

	#define _BV(x) 1<<x
	#define _ls(x,y) x<<y
	#define _rs(x,y) x>>y

	int main()
	{
	unsigned char num, andmask = 0;
	printf("Enter the number : ");
	scanf("%hhd", &num);
	andmask = ~(_BV(3) | _BV(5));
	num &= andmask;
	_getch();
	return 0;
	}
  (i)
  
  	#include<stdio.h>
	#include<conio.h>

	#define _BV(x) 1<<x

	int main()
	{
	unsigned char num, andmask = 0;
	printf("Enter the number : ");
	scanf("%hhd", &num);
	andmask = _BV(3) | _BV(5);
	num |= andmask;
	_getch();
	return 0;
	}
  (j)
  
	#include<stdio.h>
	#include<conio.h>

	#define _BV(x) 1<<x

	void showbits(unsigned char);

	int main()
	{
	int i;
	i = 10;
	showbits(i);
	_getch();
	return 0;
	}

	void showbits(unsigned char num)
	{
	int i;
	unsigned char andmask;
	for (i = 7; i >= 0; i--)
	{
		andmask = _BV(i);
		((andmask&num) == 0) ? printf("0") : printf("1");
	}
	}
  
