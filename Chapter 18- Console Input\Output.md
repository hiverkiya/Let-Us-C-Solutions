# [Console Input/Output] Solutions

## [A]

     (a)
       If upper case letter is entered so lower case of it will 
      be printed otherwise is lower case is entered so uppercase will 
      be printed.
    (b) 2    2.537   Life is like that
    (c) the person who  wins is the one who thinks he can!
    (d) The sixth sick sheikh's sixth ship is sick

## [B]
    
    (a)'a' is an array of characters, which is initialized
	at the time of declaration, so it cannot be modified.
	i.e. writing 'a++' is illegal.
    (b)Wrong format specifier used, in scanf()

    (c)n is undefined in scanf().
    (d)1. i is undefined.
	2. We cannot save string in a char type pointer 
	from scanf() function.

    (e)No error
    (f)sprintf() first argument should be of array of characters char*,
	instead of char type. 

    (g)No error but the warning, "format specifier" should
	not be used in scanf() or sscanf() functions.

## [C]

  	(a)2. gets(str);
  	(b)2. getche()
  	(c) 1. scanf()
  	(d)1. getch() : This is a function defined in file conio.h
	and used to get a single character from keyboard, without 
	displaying it on screen, and no need to press enter after 
	you entered the character.

	2. getche() : This is a function same as getch(), but the only 
	is that getche() displays the chacracter you enter on screen
	when you hit the button while getch() do the same without displaying
	it on screen. e in getche() function means echoes means displays.
	It's prototype is present in conio.h


	3. getchar() : getchar() is not a function, but it is an macro,
	present in stdio.h file. It is used to get character from keyboard 
	after pressing enter.

	4. fgetchar() : fgetchar() is same as getchar(), the only difference 
	between them is that fgetchar() is a function while getchar() is the 
	macro, both are present in the same file stdio.h
	  (e)1. Characters, format specifications and escape sequences
	Because : format specifications manage the space that a number 
	or float will take and escape sequences move the cursor and do 
	many formatting in an array of characters i.e. strings.
	  (f)4. Specifies how many columns will be used to print the
	number.

## [D]

  (a) 
  
  	#include<stdio.h>

	void xgets(char *str)
	{
	scanf("%[^\n]s", str);
	}

	void xputs(char *str)
	{
	printf("%s\n", str);
	}
  (b)
  
  	#include<stdio.h>
	#include<conio.h>

	int getint();

	int main()
	{
	int num;
	num = getint();
	printf("\nNumber : %d\n", num);
	_getch();
	return 0;
	}

	int getint()
		{
	int num = 0;
	char number[20];
	scanf("%s", number);
	sscanf(number, "%d", &num);
	return num;
	}
  (c)
  
  	#include<stdio.h>
	#include<conio.h>

	double getfloat();

	int main() /*Main is written to check the getfloat function*/
	{
	double num;
	num = getfloat();
	printf("\nNumber : %lf\n", num);
	_getch();
	return 0;
	}

	double getfloat()
	{
	double num = 0;
	char number[20];
	scanf("%s", number);
	sscanf(number, "%lf", &num);
	return num;
	}
  (d)
  
  	For first column : %26s
	For second column : %18s
	For third column : %3.2lf
