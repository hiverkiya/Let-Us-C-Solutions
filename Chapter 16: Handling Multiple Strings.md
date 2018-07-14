# [Chapter 16: Handling Multiple Strings] Solutions

## [A] 
  
    (a) 58
    
    (b) 
      An array of strings can never collect string from keyboard directly,
    it can only be initialized at the time of declaration. But still we can
    store strings from the keyboard in the array of characters indirectly, by 
    storing the string in the simple string variable and then allocate memory
    to the pointer of appropriate size and then copy the string from that simple
    string variable to the array of pointer.
    
## [B] 
    
    (a) 
    	
	#include<stdio.h>
	#include<conio.h>
	#include<malloc.h>
	#include<string.h>
	#define LINE 6/*If the number of lines are increased
	 so no need to change anything in the program just change
	 LINE macro here.*/
	#pragma warning (disable : C4267)

	void ser_rep(char **str, char *old, char *news)
	{
	int i, j, k, m, c;
	j = k = m = i = c = 0;
	char ans[10][100], *p;
        
        
	for (i = 0; i <= LINE - 1; i++)
	{
		m = 0;
		c = 0;
        /*This loop for traversing the current line character by character.*/
		for (j = 0; str[i][j] != '\0';)
		{

			if (str[i][c] == old[k])/*If the character matches*/
			{
				k++;
				c++;
				if (old[k] == '\0')/*If the whole word is found.*/
				{
                /*This loop is replacing the word character by character.*/
					for (k = 0; news[k] != '\0'; k++, m++)
						ans[i][m] = news[k];
					j = c;
					k = 0;
				}
			}
			else/*If the character/word is not matched, so as it is string is copied.*/
			{
				ans[i][m] = str[i][j];
				m++;
				j++;
				c = j;
				k = 0;
			}
		}
		ans[i][m] = '\0';/*Terminate every line by NULL character*/
		j = k = m = 0;/*Reinitialization for next line.*/
	}
	for (i = 0; i <= LINE - 1; i++)
	{
		p = (char*)malloc(strlen(ans[i]) + 1);
        /*Memory needed is 1 more for null character.
          str[i] = ans[i]; This doesn't works becuase left side is pointer and right side is simple
          char variable therefore a news pointer p is taken and copied the content of ans[i] and
          assign to the str[i].*/
		strcpy(p, ans[i]);
		str[i] = p;
	}
	}
	int main()
	{
	char *str[] = {
		"We will teach you how to...",
		"Move a mountain",
		"Level a building",
		"Erase the past",
		"Make a million",
		"...all through C!"
	};
	char str1[10], str2[10];
	puts("Enter the word you want to replace.");
	scanf("%s", str1);
	puts("Enter the word you want to put.");
	scanf("%s", str2);
	ser_rep(str, str1, str2);
	for (int i = 0; i <= LINE - 1; i++)
		puts(str[i]);
	_getch();
	return 0;
	}
(b)

	#include<stdio.h>
	#include<conio.h>
	#include<string.h>
	#include<malloc.h>
	#include<Windows.h>

	void swap(char *a, char *b)
	{
	char temp[20];
	strcpy(temp, a);
	strcpy(a, b);
	strcpy(b, temp);
	}
	void sort_names(char** name_list, int tot_names)
	{
	int i, j, k = 0;
	for (i = 0; i < tot_names; i++)
	{
		for (j = i + 1; j < tot_names; j++)
		{
			k = 0;
			while (name_list[i][k] == name_list[j][k])
				k++;
			if (name_list[i][k] > name_list[j][k])
				swap(name_list[j], name_list[i]);
		}
	}
	}
	int main()
	{
	char *nam_list[10], *p, name[20], ans = 'y';
	int i = 0, j = 0, a, b;
	while (ans == 'y')
	{
		printf("\nEnter the name : ");
		scanf("%s", name);
		p = (char*)malloc(strlen(name));
		strcpy(p, name);
		nam_list[i] = p;
		i++;
		while (getchar() != '\n');
		printf("\nWant to enter another name (y/n) : ");
		scanf("%c", &ans);
	}
	puts("\n");
	sort_names(nam_list, i);
	system("cls");
	puts("\n\t\t\tNames in sorted order are follows.\n\n");
	for (j = 0; j <= i - 1; j++)
		puts(nam_list[j]);
	_getch();
	return 0;
	}
(c)

	#include<stdio.h>
	#include<conio.h>
	#include<string.h>
	#include<malloc.h>
	#include<Windows.h>

	int main()
	{
	char *s[] = {
		"To err is human",
		"But to really mess up things...",
		"One needs to know C!!"
	};


	/*As the given strings are stored in the ROM (initialized direct in 
    the pointer saved them in ROM),	so they cannot be write only Read 
    operation can be done. So we just replace the pointer saved in the
	array of pointer to string by a new pointer in which we make changes.*/


	char *p;/*Pointer in which we will make changes*/

	for (int i = 0; i <= 2; i++)
	{
		p = (char*)malloc(sizeof(strlen(s[i]) + 1));/*Allocating memory*/
		strcpy(p, s[i]);/*Copying content to be changed from the pointer 
        initialized to the new pointer*/
		_strrev(p);/*Reverse Operation taking place*/
		s[i] = p;/*Saving the changes in the array of pointers to string.*/
		puts(s[i]);
	}

	_getch();
	return 0;
	}
(d)

	#include<stdio.h>
	#include<conio.h>
	#include<Windows.h>

	#define VS /*Uncomment this if using Visual Studio*/
	//#define TC /*Uncomment this if using Turbo C++*/

	#define LEAP (!(yr%4))/*Checing for leap year*/

	int main()
	{
	int j = 1, a = 7, i, x = 1, nod;
	int year, yr, month, m, mon, curr, next = 0;


	/*yr is for traversing the year, andn year is the
	 year given by the user. mon is for traversing the 
	 months and month is the month given by user. curr 
	 contains the starting day of the current 	month 
	 and next conatains the starting day of the next month.*/


	printf("\nEnter the year : ");
	scanf("%d", &year);
	printf("\nEnter the month : ");
	scanf("%d", &month);


	#ifdef VS
	system("cls");/*clearing screen in visula studio.*/
	#endif
	#ifdef TC
	clrscr();
	#endif


	for (yr = 1900; yr <= year; yr++)/*Traversing years*/
	{
		if (yr < year)
			m = 12; /*It will traverse the all months if 
			the year is not what user entered*/
		else
			m = month;/*It will traverse till the month user 
			want if the wanted year is encountered.*/
			
		for (mon = 1; mon <= m; mon++)//traversing all months of the year
		{
			if (mon == 2)/*If the feb is encountered*/
			{
				if (LEAP)
					nod = 29;
				else
					nod = 28;
			}
			else if (mon == 4 || mon == 6 || mon == 9 || mon == 11)
			/*Months with 30 days*/
				nod = 30;
			else/*Months with 31 days*/
				nod = 31;
			int i = 1;
			curr = next;/*Current month starts from this day*/
			while (i <= nod)
			/*This will find the day from which next month will start*/
			{
				next++;
				i++;
				if (next == 7)
					next = 0;
			}
		}
	}


	//x is dates

	j = 1, a = 7, i, x = 1;

	if (month == 1)
		printf("\n\t\tJanuary");
	if (month == 2)
		printf("\n\t\tFebraury");
	if (month == 3)
		printf("\n\t\tMarch");
	if (month == 4)
		printf("\n\t\tApril");
	if (month == 5)
		printf("\n\t\tMay");
	if (month == 6)
		printf("\n\t\tJune");
	if (month == 7)
		printf("\n\t\tJuly");
	if (month == 8)
		printf("\n\t\tAugust");
	if (month == 9)
		printf("\n\t\tSeptember");
	if (month == 10)
		printf("\n\t\tOctober");
	if (month == 11)
		printf("\n\t\tNovember");
	if (month == 12)
		printf("\n\t\tDecember");
	printf("\t %d\n\n", year);

	printf("\n\n   Sun   Mon   Tue   Wed   Thu   Fri   Sat\n\n");

	for (i = 1; x <= nod; i++)
	{
		for (j = 1; j <= 7; j++, curr--)
		{
			if (x>9)//maintaining the structure of the calender
				printf("    ");
			else
				printf("     ");

			if (curr>0)//spacing for start the calender from the given day
				printf(" ");
			else//printing of dates begin.
			{
				printf("%d", x);
				if (x <= nod)
					x++;
				if (x>nod)
					break;
			}
		}
		printf("\n\n");//next week

		if (x>nod)
			break;
	}
	_getch();
	return 0;
	}
(e)

	#include<stdio.h>
	#include<conio.h>
	#include<dos.h>

	/*********************************/
	/* function to tackle arrow keys */
	/*********************************/

	getkey() {

	union REGS i,o;

	while(!kbhit());

	i.h.ah=0;
	int86 (22,&i,&o);

	return (o.h.ah);

	}

	void main() {


	int x,y,i,lastday,key;
	int month,year,a;
	void box();

	clrscr();

	printf("Enter month: ");
	scanf("%d",&month);

	printf("\n\nEnter year: ");
	scanf("%d",&year);

	/***********************************************/
	/*   starting the program with a condition     */
	/***********************************************/


	if(month<=12 && month>=1 && year>=1900 && year<=2045)  {

	do {


	/* if up arrow key is hit */


	if(key==72) {

	if(year+1 > 2045) {
	}
	else {
	year=year+1;  /* increment of year */
	}

	}


	/* if down arrow key is hit */

	if(key==80) {

	if(year-1 < 1900) {
	}
	else {
	year=year-1;  /* decrement of year */
	}

	}


	/* if left arrow key is hit */

	if(key==75) {

	if(month-1 < 1){
	}
	else {
	month=month-1;  /* decrement of month */
	}

	}


	/* if right arrow key is hit */

	if(key==77) {

	if(month+1 > 12){
	}

	else {
	month=month+1;   /* increment of month */
	}

		}

	x=49,y=9,i=1;             /* calender printing objects */


	x = dayfinder(month,year);    /* calculating first day of the month */

	lastday = totaldays(month,year);    /* calculating total days of the month*/


	clrscr();

	box(month,year);       /* drawing boxes and headings of calender */


	/*************************/
	/* printing the calender */
	/*************************/


	while(i<=lastday) {

	gotoxy(x,y);

	printf("%2d",i);

	i++;
	x+=5;

	if(x>52) {    /* if the position of 7 days is covered, again print from
    beginning from a new line */

	x=22;
	y+=2;

	 }
	}

	gotoxy(1,1);  /* moving cursor away from calender */

	key=getkey();     /* taking the arrow key input */

	} while(key==72 || key==75 || key==77 || key==80);

	}

	else
	printf("Error! invalid input\n");


	getch();

		}
	/*********************** main ends ************************/


	/**********************************************************/
	/* function to find first day of the given month and year */
	/**********************************************************/

	int dayfinder(int month, int year)

	{

	int a,day=1;

	/* this is a general purpose formula to calculate first day */

	a=(14-month)/12;
	year=year-a;
	month=month+12*a-2;

	day=(day+year+(year/4)-(year/100)+(year/400)+((31*month)/12)) % 7;


	/* determining the position to print the first day in the calender */

	if(day==0)
	day=22;

	else if(day==1)
	day=27;

	else if(day==2)
	day=32;

	else if(day==3)
	day=37;
	
	else if(day==4)
	day=42;

	else if(day==5)
	day=47;

	else if(day==6)
	day=52;

	return (day);  /* return the position */

	}

	/********************************************************/
	/* function to draw the boxes, headings of the calender */
	/********************************************************/


	void box(int m,int y) {


	int i,j,k,l;

	/*************/
	/* inner box */
	/*************/

	/* corners of inner box */

	gotoxy(20,3);
	printf("%c",218);
	
	gotoxy(55,3);
	printf("%c",191);

	gotoxy(55,21);
	printf("%c",217);

	gotoxy(20,21);
	printf("%c",192);

	/* boundries of inner box */

	for(j=4;j<=20;j++) {

	gotoxy(20,j);
	printf("%c",179);
	
	gotoxy(55,j);
	printf("%c",179);

	}


	for(i=21;i<=54;i++) {

	gotoxy(i,3);
	printf("%c",196);

	gotoxy(i,21);
	printf("%c",196);

	}

	/*************/
	/* outer box */
	/*************/

	/* corners of outer box */

	gotoxy(17,1);
	printf("%c",218);

	gotoxy(17,23);
	printf("%c",192);

	gotoxy(58,1);
	printf("%c",191);

	gotoxy(58,23);
	printf("%c",217);

	/* boundries of outer box */

	for(k=2;k<=22;k++) {

	gotoxy(17,k);
	printf("%c",179);

	gotoxy(58,k);
	printf("%c",179);

	}


	for(l=18;l<=57;l++) {

	gotoxy(l,1);
	printf("%c",196);

	gotoxy(l,23);
	printf("%c",196);

	}

	/********************************************/
	/* writing heading on appropriate positions */
	/********************************************/


	gotoxy(22,6);
	printf("Sun");
	
	gotoxy(27,6);
	printf("Mon");

	gotoxy(32,6);
	printf("Tue");

	gotoxy(37,6);
	printf("Wed");

	gotoxy(42,6);
	printf("Thu");

	gotoxy(47,6);
	printf("Fri");

	gotoxy(52,6);
	printf("Sat");


	gotoxy(32,4);

	if(m==1)
	printf("January %d",y);

	if(m==2)
	printf("February %d",y);

	if(m==3)
	printf("March %d",y);

	if(m==4)
	printf("April %d",y);

	if(m==5)
	printf("May %d",y);

	if(m==6)
	printf("June %d",y);

	if(m==7)
	printf("July %d",y);

	if(m==8)
	printf("August %d",y);

	if(m==9)
	printf("September %d",y);

	if(m==10)
	printf("October %d",y);

	if(m==11)
	printf("November %d",y);

	if(m==12)
	printf("December %d",y);


	/*************************/
	/* printing instructions */
	/*************************/

	gotoxy(60,16);
	printf("%c : Next year",30);

	gotoxy(60,18);
	printf("%c : Previous year",31);

	gotoxy(60,20);
	printf("%c : Next month",16);

	gotoxy(60,22);
	printf("%c : Previous month",17);


	}

	/***************************************************/
	/* function to determine total days of given month */
	/***************************************************/

	int totaldays(int m,int y) {

	int days;

	/* for january */

	if(m==1)
	days=31;

	/* for february */

	if(m==2) {

	if(y%4==0)
	days=29;

	else
	days=28;

	}
	/* for march */

	if(m==3)
	days=31;

	/* for april */

	if(m==4)
	days=30;

	/* for may */

	if(m==5)
	days=31;

	/* for june */

	if(m==6)
	days=30;
	
	/* for july */

	if(m==7)
	days=31;

	/* for august */

	if(m==8)
	days=31;

	/* for september */

	if(m==9)
	days=30;

	/* for october */

	if(m==10)
	days=31;

	/* for november */

	if(m==11)
	days=30;
	
	/* for december */

	if(m==12)
	days=31;


	return days;
	}
(f)

	#include<stdio.h>
	#include<conio.h>
	#include<Windows.h>

	//#define DEVC /*Uncomment this if using DevC++*/
	#define VS /*Uncomment this if using Visual Studio*/
	//#define TC /*Uncomment this if using Turbo C++*/

	#define LEAP (!(yr%4))/*Checing for leap year*/
	#define UpArrowKey 72
	#define DownArrowKey 80
	#define LeftArrowKey 75
	#define RightArrowKey 77
	#define EscapeKey 27

	int getkey()
	{
	int ch;
	ch = _getch();
	if (ch == 0)
	{
		ch = _getch();
		return ch;
	}
	return ch;
	}
	void short_cal(int year, int month)
	{
	system("cls");
	int j = 1, a = 7, i, x = 1, nod;
	int yr, m, mon, curr, next = 0;
	for (yr = 1900; yr <= year; yr++)/*Traversing years*/
	{
		if (yr < year)
			m = 12; /*It will traverse the all months if the year is not what user entered*/
		else
			m = month;/*It will traverse till the month user want if the wanted year is encountered.*/
		for (mon = 1; mon <= m; mon++)//traversing all months of the year
		{
			if (mon == 2)/*If the feb is encountered*/
			{
				if (LEAP)
					nod = 29;
				else
					nod = 28;
			}
			else if (mon == 4 || mon == 6 || mon == 9 || mon == 11)/*Months with 30 days*/
				nod = 30;
			else/*Months with 31 days*/
				nod = 31;
			int i = 1;
			curr = next;/*Current month starts from this day*/
			while (i <= nod)/*This will find the day from which next month will start*/
			{
				next++;
				i++;
				if (next == 7)
					next = 0;
			}
		}
	}


	//x is dates

	j = 1, a = 7, i, x = 1;
	printf("\n\n\n\t\t\t\t");
	if (month == 1)
		printf("January");
	if (month == 2)
		printf("Febraury");
	if (month == 3)
		printf("March");
	if (month == 4)
		printf("April");
	if (month == 5)
		printf("May");
	if (month == 6)
		printf("June");
	if (month == 7)
		printf("July");
	if (month == 8)
		printf("August");
	if (month == 9)
		printf("September");
	if (month == 10)
		printf("October");
	if (month == 11)
		printf("November");
	if (month == 12)
		printf("December");
	printf("\t %d\n\n", year);

	printf("\n\n\n\t\t\t   Sun   Mon   Tue   Wed   Thu   Fri   Sat\n\n");

	for (i = 1; x <= nod; i++)
	{
		printf("\t\t\t");
		for (j = 1; j <= 7; j++, curr--)
		{
			if (x>9)//maintaining the structure of the calender
				printf("    ");
			else
				printf("     ");

			if (curr>0)//spacing for start the calender from the given day
				printf(" ");
			else//printing of dates begin.
			{
				printf("%d", x);
				if (x <= nod)
					x++;
				if (x>nod)
					break;
			}
		}
		printf("\n\n");//next week

		if (x>nod)
			break;
	}
	}

	int main()
	{
	int year, month, key = 0;


	/*yr is for traversing the year, andn year is the year given by the user. mon is for traversing
	the months and month is the month given by user. curr contains the starting day of the current
	month and next conatains the starting day of the next month.*/


	printf("\nEnter the year : ");
	scanf("%d", &year);
	printf("\nEnter the month : ");
	scanf("%d", &month);


	#ifdef DEVC
		system("cls");/*clearing screen in DevC++.*/
	#endif
	#ifdef VS
		system("cls");/*clearing screen in Visual Studio.*/
	#endif
	#ifdef TC
		clrscr();/*clearing screen in TurboC++.*/
	#endif

	short_cal(year, month);
	while (key != 27)
	{
		//getchar();
		//while (getkey != '\0');
		fflush(stdin);
		//while (getch() != NULL);
		//getkey();
		key = getkey();

		if (key == EscapeKey)
			return 0;
		if (key == UpArrowKey)
			short_cal(++year, month);
		if (key == DownArrowKey)
			short_cal(--year, month);
		if (key == RightArrowKey)
		{
			if (month == 12)
			{
				month = 0;
				year++;
			}
			short_cal(year, ++month);
		}
		if (key == LeftArrowKey)
		{
			if (month == 1)
			{
				month = 13;
				year--;
			}
			short_cal(year, --month);
		}
	}

	_getch();
	return 0;
	}
(g)

	#include<stdio.h>
	#include<conio.h>
	#include<Windows.h>
	#define Vowel line[i] == 'A' || line[i] == 'a' || line[i] == 'E' || line[i] == 'e' \
	 || line[i] == 'I' || line[i] == 'i' || line[i] == 'O' || line[i] == 'o' || \
 	line[i] == 'U' || line[i] == 'u'
 
	void del_vow(char *line)
	{
	int i, j;
	for (i = 0; line[i] != '\0'; i++)
		if (Vowel)
			for (j = i; line[j] != '\0'; j++)
				line[j] = line[j + 1];
	}
	int main()
	{
	char line[80];
	puts("Enter the line");
	gets_s(line);
	del_vow(line);
	printf("\nLine without vowels\n");
	puts(line);
	_getch();
	return 0;
	}
(h)

	#include<stdio.h>
	#include<conio.h>
	#include<string.h>

	#define Space 32
	#define (line[i] == 't' || line[i] == 'T') && (line[i + 1] == 'h' || \
	line[i + 1] == 'H') && (line[i + 2] == 'E' || line[i + 2] == 'e') && \
	(line[i + 3] == Space || line[i + 3] == '\0'

	void del_the(char *line)
	{
	int i, j;
	for (i = 0; line[i] != '\0'; i++)
		if ()/*if The is encounter*/
			for (j = i; line[j] != '\0'; j++)
				line[j] = line[j + 4];/*The word is skipped and other words are saved in the string*/
	}
	int main()
	{
	char line[80];
	puts("Enter the line");
	gets_s(line);
	del_the(line);
	puts("\nAfter removing all the words 'The'.\n\n");
	puts(line);
	_getch();
	return 0;
	}
(i)

	#include<stdio.h>
	#include<conio.h>
	#include<string.h>
	#include<Windows.h>
	#include<malloc.h>

	#define Space 32/*ASCII v*/

	char* last_name(char *line)/*It will return char pointer*/
	{
	char temp[20], *p;
	int i, j, l = 0;
	for (i = j = 0; line[i] != '\0'; i++)
	{
		if (line[i] == Space)/*If Sace if encounter so the first letter of the word will saved in the temp*/
		{
			temp[l] = line[j];
			l++;
			temp[l] = Space;/*after first leter we are giving a space*/
			l++;
			j = i + 1;
		}
	}
	if (line[i] == '\0')
	{
		for (; line[j] != '\0'; j++, l++)
			temp[l] = line[j];
		temp[l] = line[j];
	}
	/*As if a pointer string cannot be assigned to a simple char variable so, a pointer
     of char is made and then assign peration if performed*/
	p = (char*)malloc(sizeof(strlen(temp) + 1));/*p getting size*/
	strcpy(p, temp);/*ading content on p*/
	return p;/*assigning p to the name[i] in man function as this function returns char pointer*/
	}

	int main()
	{
	char *name[10];
	int i = 0, j;
	char ans = 'y', *p, naam[30];
	while (ans == 'y')
	{
		puts("\nEnter the full name : ");
		gets_s(naam);
		p = (char*)malloc(sizeof(strlen(naam) + 1));
		strcpy(p, naam);
		name[i] = p;
		name[i] = last_name(name[i]);
		printf("\nWant to enter another name (y/n) : ");
		scanf("%c", &ans);
		i++;
		while (getchar() != '\n');/*So that we can get the next name, otherwise \n will be saved in the buffer. (fflush(stdin) don't woirk)*/
		if (i > 9)/*Names cannot be more than 10*/
			break;
	}
	if (i >= 10)/*If trying to enter names more than 10*/
		puts("\nNo more names can be entered");
	system("cls");
	puts("\n\t\tName in the given format.");
	for (j = 0; j < i; j++)
		puts(name[j]);
	_getch();
	return 0;
	}
(j) 

	#include<stdio.h>
	#include<conio.h>

	#define VowelisOccur str[i] == 'a' || str[i] == 'A' || str[i] == 'e' || str[i] == 'E' \
	|| str[i] == 'i' || str[i] == 'I' || str[i] == 'o' || str[i] == 'O' || str[i] == 'u' \
	|| str[i] == 'U'

	int find_vows(char * str)
	{
	int i, count = 0;
	printf("\nVowels in successions : ");
	for (i = 0; str[i] != '\0'; i++)
	{
		if (VowelisOccur)/*If first vowel is occur*/
		{
			i++;/*To check next vowel*/
			if (VowelisOccur)/*If second vowel after first if occur*/
			{
				printf("%c%c ", str[i - 1], str[i]);/*Printing two simultaneous vowels*/
				count++;/*Counting Two simultaneous vowels*/
			}
		}
	}
	return count;
	}
	int main()
	{
		char str[100], tot_vow;
	printf("Enter the string : ");
	gets_s(str);
	tot_vow = find_vows(str);
	printf("\n\nTotal number of vowels in successions are : %d\n", tot_vow);
	_getch();
	return 0;
	}
(k)

	#include<stdio.h>
	#include<conio.h>
	#include<Windows.h>
	#include<malloc.h>

	#define EndofNumber 13
	#define LastElement i+2


	void rev_arr(int *arr)
	{
	int temp[12], i, max, j;
	for (i = 0; arr[i] != EndofNumber; i++);/*Counting the total number of elemeents excpet the last EndofNumber*/
	max = i - 1;/*Max is the total number of elements, as the counting starts from 0 so we subtract 1 from it*/
	i = 0;
	for (j = max; j >= 0; j--, i++)
		temp[j] = arr[i];/*temp starting from the last*/
	for (i = 0; i <= max; i++)
		arr[i] = temp[i];/*reversing the */
	}
	int main()
	{
	int num, a = 0, arr[12], i;
	char word[90];
	printf("\nEnter the number (max. 9 digits) : ");
	scanf("%d", &num);

	for (i = 0; num != 0; i++)
	{
		arr[i] = num % 10;
		num /= 10;
	}/*Saperating the digits and saving the number in array*/

	arr[i] = EndofNumber;/*Terminating array*/

	rev_arr(arr);/*The numebrs in the array are saving in the  reverse mode
				 as the saperation of the digits are takes place from last,
				 so we will reverse the numbers of the array but EndofNumber will have the same
				 position*/

	printf("\n\n\nNumber in words : ");

	for (i = 0; arr[i] != EndofNumber; i++)/*Traversing the whole array.*/
	{
		if (arr[i + 5] == EndofNumber || arr[i + 7] == EndofNumber || arr[i + 9] == EndofNumber || arr[i + 2] == EndofNumber)
		{
			if (arr[i] == 1)
			{
				if (arr[i + 1] == 1)
					printf("Eleven ");
				if (arr[i + 1] == 2)
					printf("Twelve ");
				if (arr[i + 1] == 3)
					printf("Thirteen ");
				if (arr[i + 1] == 4)
					printf("Fourteen ");
				if (arr[i + 1] == 5)
					printf("Fifteen ");
				if (arr[i + 1] == 6)
					printf("Sixteen ");
				if (arr[i + 1] == 7)
					printf("Seventeen ");
				if (arr[i + 1] == 8)
					printf("Eighteen ");
				if (arr[i + 1] == 9)
					printf("Ninteen ");
				if (arr[i + 1] == 0)
					printf("Ten ");

				i++;/*If we continue so these below words will not print as the loop is continueing from here.*/

				if (arr[i + 10] == EndofNumber)
					printf("Arab ");
				if (arr[i + 8] == EndofNumber)
					printf("Crore ");
				if (arr[i + 6] == EndofNumber)
					printf("Lac ");
				if (arr[i + 4] == EndofNumber)
					printf("Thousand ");
				if (arr[i + 3] == EndofNumber)
					printf("Hundred ");

				continue;
			}
			if (arr[i] == 2)
				printf("Twenty ");
			if (arr[i] == 3)
				printf("Thirty ");
			if (arr[i] == 4)
				printf("Fourty ");
			if (arr[i] == 5)
				printf("Fifty ");
			if (arr[i] == 6)
				printf("Sixty ");
			if (arr[i] == 7)
				printf("Seventy ");
			if (arr[i] == 8)
				printf("Eighty ");
			if (arr[i] == 9)
				printf("Ninety ");
		}
		else
		{
			if (arr[i] == 1)
				printf("One ");
			if (arr[i] == 2)
				printf("Two ");
			if (arr[i] == 3)
				printf("Three ");
			if (arr[i] == 4)
				printf("Four ");
			if (arr[i] == 5)
				printf("Five ");
			if (arr[i] == 6)
				printf("Six ");
			if (arr[i] == 7)
				printf("Seven ");
			if (arr[i] == 8)
				printf("Eight ");
			if (arr[i] == 9)
				printf("Nine ");
		}

		if (arr[i + 10] == EndofNumber)
			printf("Arab ");
		if (arr[i + 8] == EndofNumber)
			printf("Crore ");
		if (arr[i + 6] == EndofNumber)
			printf("Lac ");
		if (arr[i + 4] == EndofNumber)
			printf("Thousand ");
		if (arr[i + 3] == EndofNumber)
			printf("Hundred ");
	}
	printf("\n");
	_getch();
	return 0;
	}
(l)

	#include<stdio.h>
	#include<conio.h>
	#include<Windows.h>


	#define VisualStudio //If using Visual Studio so delete its comment and make above two macro comments
	//#define TurboC //If using Turbo C so delete its comment and make above two macro comments
	//#define DevC //If using Dev C so delete its comment and make above two macro comments

	#define EndofNumber 13/*For Terminating the array just like strings do*/

	int arr[10], x = 0, one_i = 0, two_i = 0, three_i = 0, four_i = 0, five_i = 0, six_i = 0, seven_i = 0, eight_i = 0, nine_i = 0, zero_i = 0;
	/*These variales are used in the multiple functions so I defined them globally*/

	/*These functions contains the pattern of # makes numbers*/
	void one();
	void two();
	void three();
	void four();
	void five();
	void six();
	void seven();
	void eight();
	void nine();
	void zero();

	void jumpto();/*This functions calls the functions which is the next number*/

	void rev_arr(int*);/*It will reverse the array*/

	void rev_arr(int *array)
	{
	int temp[12], i, max, j;
	for (i = 0; array[i] != EndofNumber; i++);/*Counting the total number of elemeents excpet the last EndofNumber*/
	max = i - 1;/*Max is the total number of elements, as the counting starts from 0 so we subtract 1 from it*/
	i = 0;
	for (j = max; j >= 0; j--, i++)
		temp[j] = array[i];/*temp starting from the last*/
	for (i = 0; i <= max; i++)
		array[i] = temp[i];/*reversing the */
	}

	void jumpto()
	{
	if (arr[x] == 0)
		zero();
	else if (arr[x] == 1)
		one();
	else if (arr[x] == 2)
		two();
	else if (arr[x] == 3)
		three();
	else if (arr[x] == 4)
		four();
	else if (arr[x] == 5)
		five();
	else if (arr[x] == 6)
		six();
	else if (arr[x] == 7)
		seven();
	else if (arr[x] == 8)
		eight();
	else if (arr[x] == 9)
		nine();
	if (arr[x] == EndofNumber)
	{

		/*First it will print the first line of the each number,
		then by increamenting these in loops of individual number will
		print the next line*/

		one_i++;
		two_i++;
		three_i++;
		four_i++;
		five_i++;
		six_i++;
		seven_i++;
		eight_i++;
		nine_i++;
		zero_i++;

		x = 0;/*When the first line of all the numbers has been printed then array
			  will initializes again so that we traverse the whole array again for printing the */
		printf("\n");/*Jump to next line*/
		jumpto();

	}
	return;
	}

	void one()
	{
	int j, k;
	for (; one_i < 8; one_i++)
	{
		if (one_i != 1 && one_i != 7)
			printf(" ");
		if (one_i == 1)
			k = 1;
		else if (one_i == 7)
			k = 2;
		else k = 0;
		for (j = 0; j <= k; j++)
			printf("#");
		x++;
		printf("\t");
		jumpto();
	}
	}
	void two()
	{
	int j, k;
	for (; two_i <= 7; two_i++)
	{
		if (two_i > 0 && two_i < 4)
			printf("    ");
		if (two_i == 0 || two_i == 4 || two_i == 7)
			k = 4;
		else
			k = 0;
		for (j = 0; j <= k; j++)
			printf("#");
		x++;
		printf("\t");
		jumpto();
	}
	}
	void three()
	{
	int j, k;
	for (; three_i < 8; three_i++)
	{
		if (three_i == 1 || three_i == 2 || three_i == 4 || three_i == 5 || three_i == 6)
			printf("    ");
		if (three_i == 0 || three_i == 3 || three_i == 7)
			k = 4;
		else
			k = 0;
		for (j = 0; j <= k; j++)
			printf("#");
		x++;
		printf("\t");
		jumpto();
	}
	}
	void four()
	{
	int j, k;
	for (; four_i < 8; four_i++)
	{
		if (four_i == 3)
			printf("# #");
		if (four_i == 5 || four_i == 6 || four_i == 7)
			printf("  ");
		if (four_i == 4)
			k = 4;
		else if (four_i == 3)
			k = -1;
		else
			k = 0;
		for (j = 0; j <= k; j++)
			printf("#");
		x++;
		printf("\t");
		jumpto();
	}
	}
	void five()
	{
	int j, k;
	for (; five_i < 8; five_i++)
	{
		if (five_i > 3 && five_i < 7)
			printf("    ");
		if (five_i == 0 || five_i == 3 || five_i == 7)
			k = 4;
		else
			k = 0;
		for (j = 0; j <= k; j++)
			printf("#");
		x++;
		printf("\t");
		jumpto();
	}
	}
	void six()
	{
	int j, k;
	for (; five_i < 8; five_i++)
	{
		if (five_i > 3 && five_i < 7)
			printf("#   #");
		if (five_i == 0 || five_i == 3 || five_i == 7)
			k = 4;
		else if (five_i > 3 && five_i < 7)
			k = -1;
		else
			k = 0;
		for (j = 0; j <= k; j++)
			printf("#");
		x++;
		printf("\t");
		jumpto();
	}
	}
	void seven()
	{
	for (; seven_i < 8; seven_i++)
	{
		if (seven_i != 0)
			printf("    ");
		if (seven_i == 0)
			printf("#####");
		else
			printf("#");
		x++;
		printf("\t");
		jumpto();
	}
	}
		void eight()
	{
	for (; eight_i < 8; eight_i++)
	{
		if (eight_i == 0 || eight_i == 3 || eight_i == 7)
			printf("#####");
		else
			printf("#   #");
		x++;
		printf("\t");
		jumpto();
	}
	}
	void nine()
	{
	int j, k;
	for (; eight_i < 8; eight_i++)
	{
		if (eight_i < 3 && eight_i > 0)
			printf("#   #");
		if (eight_i == 4 || eight_i == 5 || eight_i == 6)
			printf("    ");
		if (eight_i == 0 || eight_i == 7 || eight_i == 3)
			k = 4;
		else if (eight_i < 3 && eight_i > 0)
			k = -1;
		else
			k = 0;
		for (j = 0; j <= k; j++)
			printf("#");
		x++;
		printf("\t");
		jumpto();
	}

	}
	void zero()
	{
	for (; nine_i < 8; nine_i++)
	{
		if (nine_i == 0 || nine_i == 7)
			printf("#####");
		else
			printf("#   #");
		x++;
		printf("\t");
		jumpto();
	}
	}

	int main()
	{
	int num, i;
	printf("\nEnter a five digit number : ");
	scanf("%d", &num);
	for (i = 0; num != 0; i++)
	{
		arr[i] = num % 10;
		num /= 10;
	}
	arr[i] = EndofNumber;/*Terminating the number*/
	rev_arr(arr);/*Reversing the array again as the number saved in it is already in reverse mode*/


	#ifdef TurboC
	clrscr();
	#endif
	#ifdef VisualStudio
	system("cls");
	#endif
	#ifdef DevC
	system("cls");
	#endif

	printf("\n\n\n");
	jumpto();
	_getch();
	return 0;
	}




