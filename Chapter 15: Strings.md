# [Chapter 15: Strings] Solutions

## [A]
    (a)
        A
        A
    (b)
            t organised! learn C!!
            Get organised! learn C!!
            Get organised! learn C!!
            t
    (c) 
   
    N N
    N N
    o o
    o o


    t t
    t t
    w w
    w w
    o o
    o o


    v v
    v v
    i i
    i i
    r r
    r r
    u u
    u u
    s s
    s s
    e e
    e e
    s s
    s s


    w w
    w w
    o o
    o o
    r r
    r r
    k k
    k k


    s s
    s s
    i i
    i i
    m m
    m m
    i i
    i i
    l l
    l l
    a a
    a a
    r r
    r r
    l l
    l l
    y y
    y y
   
    (d) 
        
        Garbage or error, that t is not initialized.
    (e)
    
    Hello[garbage characters because NULL character is missing]
    Hello
    (f)
    Morning
    (g) e
    (h) 1 2 4

## [B]
 
    (a) 

    Error: As the str3 is declared but not defined, so it is only
    void pointer, so without allocating memory to it, we cannot
    store anything to it.
    (b) No Error
    (c) Error: In arr++ statement. As you can see that arr[8] is initilized
        at the time of declaration. So in that case we cannot assign anything 
        to arr, and statement arr++ is execute as arr = arr + 1, which is 
    illegal.
## [C]
    
    (a) string,character
    (b) NULL,'\0'
    (c) 9 characters, and 10th character space is for \0 character.
    (d) contiguous.
## [D]
    (a)
    gets() is more appropriate for reading a multi-word string.
    
    (b) str1 : Alice
        str2 : in
        str3 : wonder
        str4 : land
    (c) #include<stdio.h>
    #include<conio.h>
    #include<string.h>
    int main()
    {
	char sen[100];
	int i;
	printf("Enter your sentence. (Less than 100 chracters)\n\n");
	gets_s(sen);
	printf("After how muany characters you want to extract the line : ");
	scanf("%d", &i);
	i--;
	if (i<0)
		i = 0;
	printf("%s\t", &sen[i]);
	_getch();
	return 0;
    }
    (d)
    #include<stdio.h>
    #include<conio.h>
    int main()
    {
	char str[100];
	int i, num, fin = 0;
	printf("Enter a string of numbers : ");
	gets_s(str);
	for (i = 0; str[i] != '\0'; i++)/*Run until string is not terminated.*/
	{
		num = str[i] - 48;/*Converting the character number into integer number.*/
		fin = fin * 10 + num;/*Combining the individual numbers to form a single integers*/
	}
	printf("\nNumber : %d", fin);
	_getch();
	return 0;
    }
    (e) #include<stdio.h>
    #include<conio.h>
    #include<string.h>
    int main()
    {
	char x[50] = "a", z[50];
	char y[50] = "b";
	int i;
	for (i = 0; i <= 5; i++)
	{
		printf("%s\t", x);//printing x
		strcpy(z, x);/*copying x into z*/
		strcpy(x, y);/*copying y into x*/
		strcat(y, z);/*adding (concatinating) z in y*/
	}
	_getch();
	return 0;
    }
    (f) #include<stdio.h>
    #include<conio.h>
    int main()
    {
	char isbn[15];
	int i, sum = 0;
	printf("\nEnter 10 digit ISBN number : ");
	gets_s(isbn);
	for (i = 0; i <= 9; i++)
	{
		isbn[i] -= 48;/*Converting characters into numerals*/
		sum = sum + ((i + 1)*isbn[i]);/*checking the condition of the ISBN validity*/
	}
	if (sum % 11)/*If not divisble by 11*/
		puts("\nISBN number is wrong.");
	else
		puts("\nISBN number is valid.");
	_getch();
	return 0;
    }
    (g)
    #include<stdio.h>
    #include<conio.h>
    int main()
    {
	char num[20];
	int i, sum = 0;
	printf("\nEnter the 16 digit credit card number : ");
	scanf("%s", num);

	for (i = 0; i <= 15; i++)//Traversing all numbers
	{
		num[i] -= 48;//converting each character in numeral
		if ((i % 2))//if the number is on right so it will directly get summed
			sum = sum + num[i];
		else//if number is on left, so it will first get doubled
		{
			num[i] *= 2;
			if (num[i] >= 10)//if number is greater then or equal to 10 so it will subtracted from 9
				num[i] -= 9;
			sum = sum + num[i];	//summing number
		}
	}
	if (!(sum % 10))//if sum is divisble by 10 so number is valid
		printf("\nNumber is valid.");
	else
		printf("\nNumber is not valid.");
	_getch();
	return 0;
}
