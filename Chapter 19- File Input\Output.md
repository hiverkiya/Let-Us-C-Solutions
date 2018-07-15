# [Chapter 19: File Input/Output] Solutions

## [A]

  (a)
        
    Argument of openfile() is of FILE** type, while
    in main FILE* is passed in the function.
  (b)
    
    1. null is not defined, NULL should be used at that place.
    2. exit() function should have an int type argument, which is 
    not present there.
    3. putch() is defined in conio.h file which is also not present.
  (c)
  
    "tr" is not any valid file opening mode, it should be
    "r", "rt" or "rb". And a .dat should be open in binary mode,
    that is in "rb" mode.
  (d)
  
    1. fgets() do not return EOF, so while loop statement is
    invalid.
    2. We are storing 81 characters in str variable, 80 characters 
    form the file and 1 character is added automatically the NULL 
    character that caused overflow of the array.
      3. fputs() accepts three arguments, char* and FILE*, but only
    one argument is passed.
  (e)
      
      ch is not defined in this scope.
  (f)
  
    1. sizeof operator do not have spce between it.
    2. close() function is undefined. Use fclose();
  (g)
  
    1. Cannot use fwrite() function on the file opened in 
    "r" (read only) mode.
    2. close() function is undfined. Use fclose();


  (h)
  
    1. open() and close() functions are UNIX platofrm specific.
    Use _open() or _close() and include io.h file if you are
    using Visual Studio;
(i) 
      
      1. close() and open() functions are not defined, with the same reason
      stated above.
    2. fopen() returns FILE* but it is assigned to an int type variable.
    3. READ | BINARY are undefined
    
 # [B]
 
 (a)  
    
    4. stdio.h
 (b)
 
    3. I am a boy\n\0
 (c)
    
     T,T,T,F.
 (d)
    
    4. All the above.
 (e)
 
      No, it is not necessary that a file is created in text mode
      must always be opened in text mode, it can also opened in binary mode,
    for subsequent operations. Binary or text are depend upon the content
    storage mode, a file with extension .txt can also be a binary file.
 (f)
 
      1. If "myfile.c" exist in the disk, so simple
      FILE pointer fp points to the file.

      2. If "myfile.c" do not exist in the disk, so as 
      the opening mode is "r" read only, so no new file is
      created and fopen() returns a NULL assigned to fp.
 (g)
 
    When we get any character from keyboard, so this procedure
    takes place.
	- We enter character from keyboard.
	- Characters entered are go in Standard Input Stream
	- function like scanf() or getch() fetch that character from
	  the Standard Input Stream, and not from the keyboard.

    So, hitting Enter key after the character key, store Enter also in 
      Standard Input Stream, so the next function scanf() or getch(), do
      not wait to get character from the keyboard, but take the Enter key,
    hit previously from the Standard Input Stream. So, to solve this problem
      we have to clear our buffer completely before functions scanf("%c") or getch().
    This function is performed by fflush(stdin).
 (h)
 
    1. If 'myfile.c' do not exist in the disk, so 
    a new file is created, and fp points to that 
    new file in binary mode.

      2. If 'myfile.c' exists on the disk, so fp points to
    that file in binary mode.
 (i) 
 
    If we have to store something in a file, so we should open
    this file in write mode. And opening the file in binary mode,
    saves lots of space and works faster, so I will choose the mode
    "wb+".
# [C]

	(a)
	
		#include<stdio.h>
		#include<conio.h>
		#include<stdlib.h>
		int main()
	{
	FILE *fp;
	int i = 1;
	char ch;
	fp = fopen("File (a).txt", "r+");
	if (fp == NULL)
	{
		puts("\nFile can't be open");
		exit(1);
	}
	/*Line no. before first line*/
	printf("%d. ", i);
	i++;
	do
	{
		ch = fgetc(fp);
		if (ch == '.')
		{
			printf("%c", ch);
			if (fgetc(fp) == EOF)
				continue;

			/*Printing the line number*/
			printf("\n%d. ", i);

			i++;
			continue;
		}
		printf("%c", ch);
	} while (ch != EOF);
	fclose(fp);
	_getch();
	return 0;
		}
	(b)
	
		#include<stdio.h>
		#include<conio.h>
		#include<stdlib.h>
		int main()
	{
	FILE *f1, *f2;
	char ch, buffer[10];

	//Desrination File
	f1 = fopen("File (b)1.txt", "a+");
	if (f1 == NULL)
	{
		printf("File do not exist or can't be open");
		exit(1);
	}

	//Source File
	f2 = fopen("File (b)2.txt", "r+");
	if (f2 == NULL)
	{
		printf("File do not exist or can't be open");
		exit(2);
	}

	fseek(f1, 0, SEEK_END);
	//Goes to last character

	ch = fgetc(f2);

	while (ch != EOF)
	{
		fputc(ch, f1);
		ch = fgetc(f2);
	}

	rewind(f1);
	while (fgets(buffer, 9, f1) != NULL)/*Displaying the content*/
		printf("%s", buffer);

	fclose(f1);
	fclose(f2);
	_getch();
	return 0;
		}
	(c)
	
		#include<stdio.h>
		#include<conio.h>
		#include<stdlib.h>
		#include<string.h>

		void sort_names(char**, int);
		void swap(char*, char*);

		int main()
		{
	char ch = 'i', *help[30], name[50], *p;
	int i, j, tot_names;
	FILE *fp;
	fp = fopen("File (c).txt", "r+");
	if (fp == NULL)
	{
		printf("\nCannot open the file.\n");
		exit(1);
	}
	for (i = 0; ch != EOF; i++)
	{
		ch = fgetc(fp);
		for (j = 0; ch != '\n'; j++)
		{
			if (ch == EOF)
				break;

			name[j] = ch;
			ch = fgetc(fp);
		}

		//To terminate the string
		name[j] = '\0';

		/*Saveing the name is array of pointers*/
		p = (char*)malloc(50);
		strcpy(p, name);
		help[i] = p;
	}
	tot_names = i - 1;

	sort_names(help, tot_names);

	//Displaying the content
	for (j = 0; j <= tot_names; j++)
		puts(help[j]);

	fclose(fp);
	_getch();
	return 0;
		}

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

	for (i = 0; i <= tot_names; i++)
	{
		for (j = i + 1; j <= tot_names; j++)
		{
			/*If the name starts with same letter,
			so it checks the next letter of that name*/
			for (k = 0; name_list[i][k] == name_list[j][k]; k++);

			if (name_list[i][k] > name_list[j][k])
				swap(name_list[j], name_list[i]);
		}
	}
		}
	(d)
	
		#include<stdio.h>
		#include<conio.h>
		#include<string.h>
		int main()
	{
	char str[50];
	FILE *f1, *f2;
	f1 = fopen("File (d)1.txt", "r");
	f2 = fopen("File (d)2.txt", "w");
	while (fgets(str, 49, f1) != NULL)
	{
		_strupr(str);
		fputs(str, f2);
	}
	_getch();
	return 0;
		}
	(e)
	
		#include<stdio.h>
		#include<conio.h>
		#include<stdlib.h>
		int main()
	{
	FILE *f1, *f2, *fp;
	char ch1 = 'a', ch2 = 'a';
	f1 = fopen("File (e)1.txt", "r");
	f2 = fopen("File (e)2.txt", "r");
	fp = fopen("File (e)3.txt", "w");

	if (f1 == NULL)
	{
		printf("Can't open the file1\n");
		exit(1);
	}
	if (f2 == NULL)
	{
		printf("Can't open the file1\n");
		exit(2);
	}

	puts("\nWork on progress\n.\n.\n.\n.\n");
	
	while (1)
	{
		if (ch1 != EOF)
		{
			ch1 = fgetc(f1);
			/*A line is ends when a . is encounter*/
			while (ch1 != '.')
			{
				if (ch1 == EOF)
					break;
				fputc(ch1, fp);
				ch1 = fgetc(f1);
			}
			if (ch1 != EOF)
				fputc('.', fp);
		}
		if (ch2 != EOF)
		{
			ch2 = fgetc(f2);
			/*A line is ends when a . is encounter*/
			while (ch2 != '.')
			{
				if (ch2 == EOF)
					break;
				fputc(ch2, fp);
				ch2 = fgetc(f2);
			}
			if (ch2 != EOF)
				fputc('.', fp);
		}
		/*Getting out of the loop after end of both files*/
		if (ch1 == EOF && ch2 == EOF)
			break;
	}
	printf("\nTask completed.\nExiting . . . \n");
	_getch();
	return 0;
		}
(f)
	
	#include<stdio.h>
		#include<conio.h>
		#include<stdlib.h>
		#include<Windows.h>

		void getkey();
		void gotoxy(short, short);
		void box(short, short, short, short);

		int main()
		{
	box(0, 1, 79, 23);
	FILE *fp;
	char str[85];
	int i, j = 1;
	fp = fopen("File (f).txt", "r");
	if (fp == NULL)
	{
		printf("FIle do not exist, or can't open the file.");
		exit(1);
	}
	i = 2;
	while (fgets(str, 76, fp) != NULL)
	{
		gotoxy(1, 0);
		/*Printing page number*/
		printf("%d", j);
		gotoxy(32, 0);
		/*Printing the file name.*/
		printf("File (f).txt");
		gotoxy(3, i);
		/*Printing the file's content.*/
		printf("%s", str);
		i++;
		if (i == 20)
		{
			gotoxy(32, i + 4);
			printf("Press any key...");
			getkey();
			system("cls");
			box(0, 1, 79, 23);
			/*Re-initializing variable for new page*/
			i = 2;
			/*Page number increamentation*/
			j++;
		}
	}
	getkey();
	system("cls");
	gotoxy(3, 10);
	printf("File Ends\n");
	_getch();
	return 0;
		}

		void getkey()
		{
	char ch;
	ch = _getch();
	if (ch == 0)
				ch = _getch();
		}
		void gotoxy(short col, short row)
		{
	HANDLE h = GetStdHandle(STD_OUTPUT_HANDLE);
	COORD position = { col,row };
	SetConsoleCursorPosition(h, position);
		}
		void box(short x1, short y1, short x2, short y2)
	{
	int i;
	gotoxy(0, 1);
	printf("%c", 218);/*Making upper-left corener*/
	gotoxy(79, 1);
	printf("%c", 191);/*Making upper-right corner*/
	gotoxy(0, 23);
	printf("%c", 192);/*Making lower-left corner*/
	gotoxy(79, 23);
	printf("%c", 217);/*Making lower-right corner*/
	
	for (i = x1 + 1; i < x2; i++)
	{
		gotoxy(i, y1);
		printf("%c", 196);/*This will make upper side of the box*/
		gotoxy(i, y2);
		printf("%c", 196); /*This will make lower side of the box*/
	}

	for (i = y1 + 1; i < y2; i++)
	{
		gotoxy(x1, i);
		printf("%c", 179); //This will make left side of the box
		gotoxy(x2, i);
		printf("%c", 179); //This will make right side of the box
	}
		}
	(g)
	
		#include<stdio.h>
		#include<conio.h>
		#include<ctype.h>

		void encode(FILE*, FILE*);
	void decode(FILE*, FILE*);
		void display(FILE*);

	int main()
	{
	FILE *sf, *df;
	/*Source File*/
	sf = fopen("File (g)1.txt", "r");
	/*Destination File*/
	df = fopen("File (g)2.txt", "w");

	/*Displaying decoded file before encoding*/
	display(sf);
	
	/*Encoding file*/
	encode(sf, df);
	/*Displaying encoded file after encoding*/
	display(df);
	
	/*Decoding file*/
	decode(df, sf);
	/*Displaying file after decoding*/
	display(sf);

	_getch();
	return 0;
	}

	void encode(FILE *sf, FILE *df)
	{
	char ch;
	while (1)
	{
		ch = fgetc(sf);
		if (ch == EOF)
			break;
		if (isalpha(ch) || ch == ' ' || ch == '\n')
		{
			switch (ch)
			{
			case '\n':
				fputc('@', df);
				break;
			case 'a':
				fputc('0', df);
			case 'A':
				fputc('!', df);
				break;
			case 'b':
				fputc('0', df);
			case 'B':
				fputc('#', df);
				break;
			case 'c':
				fputc('0', df);
			case 'C':
				fputc('$', df);
				break;
			case 'd':
				fputc('0', df);
			case 'D':
				fputc('%', df);
				break;
			case 'e':
				fputc('0', df);
			case 'E':
				fputc('&', df);
				break;
			case 'f':
				fputc('0', df);
			case 'F':
				fputc('*', df);
				break;
			case 'g':
				fputc('0', df);
			case 'G':
				fputc('(', df);
				break;
			case 'h':
				fputc('0', df);
			case 'H':
				fputc(')', df);
				break;
			case 'i':
				fputc('0', df);
			case 'I':
				putc('+', df);
				break;
			case 'j':
				fputc('0', df);
			case 'J':
				fputc('/', df);
				break;
			case 'k':
				fputc('0', df);
			case 'K':
				fputc('{', df);
				break;
			case 'l':
				fputc('0', df);
			case 'L':
				fputc('}', df);
				break;
			case 'm':
				fputc('0', df);
			case'M':
				fputc(';', df);
				break;
			case 'n':
				fputc('0', df);
			case 'N':
				fputc(':', df);
				break;
			case 'o':
				fputc('0', df);
			case 'O':
				fputc('[', df);
				break;
			case 'p':
				fputc('0', df);
			case 'P':
				fputc(']', df);
				break;
			case 'q':
				fputc('0', df);
			case 'Q':
				fputc('"', df);
				break;
			case 'r':
				fputc('0', df);
			case 'R':
				fputc('`', df);
				break;
			case 's':
				fputc('0', df);
			case 'S':
				fputc('\\', df);
				break;
			case 't':
				fputc('0', df);
			case 'T':
				fputc('|', df);
				break;
			case 'u':
				fputc('0', df);
			case 'U':
				fputc('=', df);
				break;
			case 'v':
				fputc('0', df);
			case 'V':
				fputc('-', df);
				break;
			case 'w':
				fputc('0', df);
			case 'W':
				fputc('_', df);
			case 'x':
				fputc('0', df);
			case 'X':
				fputc('<', df);
				break;
			case 'y':
				fputc('0', df);
			case 'Y':
				fputc('^', df);
				break;
			case 'z':
				fputc('0', df);
			case 'Z':
				fputc('?', df);
				break;
			case ' ':
				fputc('1', df);
				break;
			}
		}
		else
			fputc(ch, df);
		}
	}

	void decode(FILE *ef, FILE *df)
	{
	char ch;
	while (1)
	{
		ch = fgetc(df);
		if (ch == EOF)
			break;
		switch (ch)
		{
		case '@':
			fputc('\n', ef);
			break;
		case '0':
			ch = fgetc(df);
			switch (ch)
			{
			case '!':
				fputc('a', ef);
				break;
			case '#':
				fputc('b', ef);
				break;
			case '$':
				fputc('c', ef);
				break;
			case '%':
				fputc('d', ef);
				break;
			case '&':
				fputc('e', ef);
				break;
			case '*':
				fputc('f', ef);
				break;
			case '(':
				fputc('g', ef);
				break;
			case ')':
				fputc('h', ef);
				break;
			case '+':
				fputc('i', ef);
				break;
			case '/':
				fputc('j', ef);
				break;
			case '{':
				fputc('k', ef);
				break;
			case'}':
				fputc('l', ef);
				break;
			case ';':
				fputc('m', ef);
				break;
			case ':':
				fputc('n', ef);
				break;
			case '[':
				fputc('o', ef);
				break;
			case ']':
				fputc('p', ef);
				break;
			case '"':
				fputc('q', ef);
				break;
			case '`':
				fputc('r', ef);
				break;
			case '\\':
				fputc('s', ef);
				break;
			case '|':
				fputc('t', ef);
				break;
			case '=':
				fputc('u', ef);
				break;
			case '-':
				fputc('v', ef);
				break;
			case '_':
				fputc('w', ef);
				break;
			case '<':
				fputc('x', ef);
				break;
			case '^':
				fputc('y', ef);
				break;
			case '?':
				fputc('z', ef);
				break;
			}
			break;
		case '!':
			fputc('A', ef);
			break;
		case '#':
			fputc('B', ef);
			break;
		case '$':
			fputc('C', ef);
			break;
		case '%':
			fputc('D', ef);
			break;
		case '&':
			fputc('E', ef);
			break;
		case '*':
			fputc('F', ef);
			break;
		case '(':
			fputc('G', ef);
			break;
		case ')':
			fputc('H', ef);
			break;
		case '+':
			putc('I', ef);
			break;
		case '/':
			fputc('J', ef);
			break;
		case '{':
			fputc('K', ef);
			break;
		case '}':
			fputc('L', ef);
			break;
		case';':
			fputc('M', ef);
			break;
		case ':':
			fputc('N', ef);
			break;
		case '[':
			fputc('O', ef);
			break;
		case ']':
			fputc('P', ef);
			break;
		case '"':
			fputc('Q', ef);
			break;
		case '`':
			fputc('R', ef);
			break;
		case '\\':
			fputc('S', ef);
			break;
		case '|':
			fputc('T', ef);
			break;
		case '=':
			fputc('U', ef);
			break;
		case '-':
			fputc('V', ef);
			break;
		case '_':
			fputc('W', ef);
		case '<':
			fputc('X', ef);
			break;
		case '^':
			fputc('Y', ef);
			break;
		case '?':
			fputc('Z', ef);
			break;
		case '1':
			fputc(' ', ef);
			break;
		default:
			fputc(ch, ef);
		}
	}
	}

	void display(FILE *fp)
	{
	char str[50];
	while (fgets(str, 49, fp) != NULL)
		printf("%s", str);
	puts("\n\n");
	_getch();
	}
	(h)
	
		#include<stdio.h>
	#include<Windows.h>
	#include<string.h>
	#include<conio.h>

	void display(char*);
	void add_info(int, char*, float);
	void transaction(int, char, float);

	struct customer
	{
	int accno;
	char name[30];
	float balance;
	};

	struct trans
	{
	int accno;
	char trans_type;
	float amount;
	};

	int main()
	{
	add_info(1, "Siraj", 1000);
	puts("\n\t\tBefore Transaction");
	display("customer.dat");
	transaction(1, 'd', 1000);
	puts("\n\t\tAfter Transaction");
	display("customer.dat");
	_getch();
	return 0;
	}

	void display(char *file)
	{
	FILE *fp;
	struct customer holder;
	fp = fopen(file, "rb");
	while (fread(&holder, sizeof(holder), 1, fp) == 1)
	{
		printf("\n%d", holder.accno);
		printf(":\t%s", holder.name);
		printf("\t%f\n", holder.balance);
	}
	fclose(fp);
	}

	void add_info(int accno, char *name, float bal)
	{
	FILE *fp;
	struct customer holder;
	fp = fopen("customer.dat", "rb+");
	if (fp == NULL)
		fp = fopen("customer.dat", "wb");
	fseek(fp, 0, SEEK_END);
	holder.accno = accno;
	strcpy(holder.name, name);
	holder.balance = bal;
	fwrite(&holder, sizeof(holder), 1, fp);
	fclose(fp);
	}

	void transaction(int accno, char ttype, float amount)
	{
	FILE *fp, *temp;
	struct customer holder;
	fp = fopen("customer.dat", "rb");
	temp = fopen("temp.dat", "wb");
	while (fread(&holder, sizeof(holder), 1, fp) == 1)
	{
		if (holder.accno == accno)
		{
			switch (ttype)
			{
			case 'd':
			case 'D':
				holder.balance += amount;
				break;
			case 'w':
			case 'W':
				if ((holder.balance - amount) < 100)
				{
					system("cls");
					printf("\nYour account balance is low.\n");
					printf("Transaction failed!!");
					_getch();
				}
				else
					holder.balance -= amount;
				break;
			default:
				system("cls");
				puts("Wrong transaction type!!");
				puts("\nTry Again!!");
				fclose(fp);
				fclose(temp);
				remove("temp.dat");
				return;
			}
		}
		fwrite(&holder, sizeof(holder), 1, temp);
	}
	fclose(fp);
	fclose(temp);
	remove("customer.dat");
	rename("temp.dat", "customer.dat");
	}
	(i)
	
		#include<stdio.h>
		#include<conio.h>
		#include<string.h>
			#include<Windows.h>

		struct date
		{
	int d, m, y;
	};

	struct employee
	{
	char empcode[6];
	char empname[20];
	struct date join_date;
	float salary;
	};

	/*To display list in way they are actually saved in disk.*/
	void display(char*);
	/*To make file before sorting them*/
	void add_info(char*, char*, struct date, float);
	/*Sort by date of joining*/
	void sortbydoj(char*);
	void swap(struct employee*, struct employee*);

	int main()
	{
	struct date d = {13, 1, 1995};
	add_info("EMP01","Siraj", d,  50000.00);
	d.d = 17; d.m = 5; d.y = 1994;
	add_info("EMP04","Karan", d,45000.00);
	d.d = 7; d.m = 7; d.y = 1995;
	add_info("EMP03","Deepak", d,45000.00);
	d.d = 2; d.m = 11; d.y = 1995;
	add_info("EMP02","Azad",d,45000.00);
	d.d = 15; d.m = 1; d.y = 2001;
	add_info("EMP04", "Vijay", d, 21000.00);
	d.d = 24; d.m = 5; d.y = 1993;
	add_info("EMP06", "Shanu", d, 55000.00);
	sortbydoj("Record.dat");
	_getch();
	return 0;
	}


	void display(char *file)
	{
	FILE *fp;
	struct employee e;
	fp = fopen(file, "rb");
	while (fread(&e, sizeof(e), 1, fp) == 1)
	{
		printf("\n%s", e.empcode);
		printf("\t%s", e.empname);
		printf("\t%d", e.join_date.d);
		printf("\t%d", e.join_date.m);
		printf("\t%d", e.join_date.y);
		printf("\t%f\n", e.salary);
	}
	fclose(fp);
	}

	void add_info(char *code, char *name, struct date doj, float salary)
	{
	FILE *fp;
	fp = fopen("Record.dat", "rb+");
	if (fp == NULL)
		fp = fopen("Record.dat", "wb");
	struct employee e;
	strcpy(e.empcode, code);
	strcpy(e.empname, name);
	e.join_date = doj;
	e.salary = salary;
	fseek(fp, 0, SEEK_END);
	fwrite(&e, sizeof(e), 1, fp);
	fclose(fp);
	}

	void swap(struct employee *a, struct employee *b)
	{
	struct employee temp;
	temp = *a;
	*a = *b;
	*b = temp;
	}

	void sortbydoj(char *file)
	{
	int i = 0, j, count;
	FILE *fp1;
	struct employee e[100], temp;
	fp1 = fopen(file, "rb");
	if (fp1 == NULL)
	{
		puts("\nUnable to open file or the file do not exist.");
		exit(1);
	}
	while (1)
	{
		/*Saving the data in the array of structures*/
		if (fread(&e[i], sizeof(e[i]), 1, fp1) != 1)
			break;
		i++;
	}

	/*Total number of records*/
	count = i;

	for (i = 0; i < count; i++)
	{
		for (j = i + 1; j < count; j++)
		{
			if (e[i].join_date.y >= e[j].join_date.y)
				if (e[i].join_date.y > e[j].join_date.y)
					swap(&e[i], &e[j]);
				else
					if (e[i].join_date.m >= e[j].join_date.m)
						if (e[i].join_date.m > e[j].join_date.m)
							swap(&e[i], &e[j]);
						else if (e[i].join_date.d >= e[j].join_date.d)
							swap(&e[i], &e[j]);
		}
	}


	/*Printing the array after sorting by date of joining*/

	printf("Employee Id\tName\tdd  mm  yyyy\tSalary\n");
	for (i = 0; i < count; i++)
	{
		printf("\n%-12s", e[i].empcode);
		printf("\t%s", e[i].empname);
		printf("\t % 2d", e[i].join_date.d);
		printf("% 2d", e[i].join_date.m);
		printf("% 2d", e[i].join_date.y);
		printf("\t%2.2f\n", e[i].salary);

	}
	}
	(j)
	
			#include<stdio.h>
	#include<conio.h>
	#include<windows.h>
	#include<stdlib.h>

	void add_info(struct blood);
	void display(char*);
	void lessthen25(char*);

	struct blood
	{
	char name[20];
	char address[40];
	int age;
	int blood_type;
	};

	int main()
	{
	lessthen25("Blood Donors Record.txt");
	_getch();
	return 0;
	}

	void add_info(struct blood data)
	{
	FILE *fp;
	fp = fopen("Blood Donors Record.txt", "r+");
	if (fp == NULL)
		fp = fopen("Blood Donors Record.txt", "w");
	fseek(fp, 0, SEEK_END);
	fprintf(fp, "%-20s", data.name);
	fprintf(fp, "%-40s ", data.address);
	fprintf(fp, "%-2d ", data.age);
	fprintf(fp, "%d\n", data.blood_type);
	fclose(fp);
	}

	void display(char *file)
	{
	FILE *fp;
	fp = fopen(file, "r");
	char str[20];
	while (fgets(str, 19, fp) != NULL)
		printf("%s", str);
	fclose(fp);
	}

	void lessthen25(char *file)
	{
	FILE *fp;
	struct blood data;
	int age;
	char str[68];
	fp = fopen(file, "r");
	while (fgets(str, 67, fp) != NULL)
	{
		age = (str[62] - 48) * 10 + (str[63] - 48);
		if (age < 25)
			printf("%s", str);
	}
	fclose(fp);
	}
	(k)
	
		#include<stdio.h>
	#include<conio.h>
	#include<string.h>
	#include<stdlib.h>
	#include<Windows.h>

	void add_info(char*, char*);
	void display(char*);
	void disbys(int, char*);

	int main()
	{
	disbys(1, "Students.txt");
	_getch();
	return 0;
	}

	void add_info(char *name, char *file)
	{
	FILE *fp;
	fp = fopen(file, "r+");
	if (fp == NULL)
		fp = fopen(file, "w");
	fseek(fp, 0, SEEK_END);
	fputs(name, fp);
	putc('\n', fp);
	fclose(fp);
	}

	void display(char *file)
	{
	FILE *fp;
	char name[30];
	fp = fopen(file, "r");
	if (fp == NULL)
	{
		printf("File do not exist.");
		_getch();
		exit(1);
	}
	while (fscanf(fp, "%s", name) != -1)
		puts(name);
	fclose(fp);
	}

	void disbys(int num, char *file)
	{
	FILE *fp;
	int i;
	char name[30];
	fp = fopen(file, "r");
	if (fp == NULL)
	{
		printf("File do not exist.");
		_getch();
		exit(2);
	}

	for (i = 1; fscanf(fp, "%s", name) != -1; i++)
	{
		if (i == num)
		{
			switch (num)
			{
			case 1:
				printf("%dst name is : ", num);
				break;
			case 2:
				printf("%dnd case is : ", num); 
				break;
			case 3:
				printf("%drd name is : ", num); 
				break;
			default:
				printf("%dth name is : ", num);
			}
			printf("%s\n\n", name);
			break;
		}
	}
	if (fscanf(fp, "%s", name) == -1)
		printf("There's only %d names.\n", i);

	rewind(fp);
	while (fscanf(fp, "%s", name) != -1)
		if (name[0] == 'S' || name[0] == 's')
			puts(name);
	fclose(fp);
	}
	(l)
	
		#include<stdio.h>
	#include<conio.h>
	#include<string.h>
	#include<Windows.h>
	#include<stdlib.h>
	
	struct data
	{
	int rollno;
	char name[20];
	};

	void add_info(int, char*);
	void display(char*);
	void update_list(char*);

	int main()
	{
	add_info(1, "Azad Ansari");
	add_info(2, "Deepak Mathpal");
	add_info(3, "Rahul Khowal");
	add_info(4, "Siraj");
	add_info(5, "Priya Saxena");
	add_info(6, "Rajkumari");
	add_info(7, "Varun Taneja");
	add_info(8, "Manish Kumar");
	add_info(9, "Shabnam");
	update_list("Transaction.txt");
	display("New List.dat");
	_getch();
	return 0;
	}

	void add_info(int rollno, char *name)
	{
	struct data e;
	FILE *fp;
	fp = fopen("Students.dat", "rb+");
	if (fp == NULL)
		fp = fopen("Students.dat", "wb");
	e.rollno = rollno;
	strcpy(e.name, name);
	fseek(fp, 0, SEEK_END);
	fwrite(&e, sizeof(e), 1, fp);
	fclose(fp);
	}

	void display(char *fname)/* Display the MASTER FILE*/
	{
	FILE *fp;
	struct data e;
	fp = fopen(fname, "rb");
	if (fp == NULL)
	{
		puts("Can't open the file.\nExiting...\n");
		_getch();
		exit(3);
	}
	while (fread(&e, sizeof(e), 1, fp) == 1)
		printf("%2d\t%-10s\n", e.rollno, e.name);
	}

	void update_list(char *tfile)
	{
	FILE *tf, *mf, *uf;
	char code, name[20];
	int rollno, i;
	struct data dat_of_mf;
	tf = fopen(tfile, "r");
	if (tf == NULL)
	{
		printf("\nTransaction file is not found");
		printf("\nexiting...\n");
		_getch();
		exit(1);
	}
	mf = fopen("Students.dat", "rb");
	if (mf == NULL)
	{
		printf("\nMaster file is not found\nexiting...\n");
		_getch();
		exit(2);
	}
	uf = fopen("New List.dat", "wb+");
	while (1)
	{
		code = fgetc(tf);
		if (code == 'D') 
		{
			fseek(tf, 1, SEEK_CUR);
			rollno = fgetc(tf) - 48;
			while (1)
			{
				fread(&dat_of_mf, sizeof(dat_of_mf), 1, mf);
				if (dat_of_mf.rollno < rollno)
					fwrite(&dat_of_mf, sizeof(dat_of_mf), 1, uf);
				else
					break;
			}
			while (fgetc(tf) == '\n');
			fseek(tf, -1, SEEK_CUR);
		}
		else if (code == 'A')
		{
			/* Skipping the space after trasnsaction code*/
			fseek(tf, 1, SEEK_CUR);
			rollno = fgetc(tf) - 48;
			/*Skipping the space after trasnsaction code*/
			fseek(tf, 1, SEEK_CUR);
			for (i = 0; 1; i++)
			{
				name[i] = fgetc(tf);
				if (name[i] == '\n' || name[i] == EOF)
				{
					name[i] = '\0';
					break;
				}
			}
			dat_of_mf.rollno = rollno;
			strcpy(dat_of_mf.name, name);
			fwrite(&dat_of_mf, sizeof(dat_of_mf), 1, uf);
		}
		else
		{
			while (fread(&dat_of_mf, sizeof(dat_of_mf), 1, mf) == 1)
				fwrite(&dat_of_mf, sizeof(dat_of_mf), 1, uf);
			break;
		}
	}
	fclose(uf);
	fclose(mf);
	fclose(tf);
	}
(m)
	
		#include<stdio.h>
	#include<conio.h>
	#include<stdlib.h>
	#include<string.h>
	#include<Windows.h>

	struct empo
	{
	int eid;
	char name[20];
	char sex;
	int salary;
	};

	int main()
	{
	addemp(1, "Kishor Dass", 'M', 100);
	addemp(2, "Amit Kumar Mandal", 'M', 200);
	addemp(3, "Prakash Babu Sharma", 'M', 300);
	addemp(4, "Mohd Seraj Alam", 'M', 400);
	addemp(5, "Priya Saxena", 'F', 500);
	addemp(6, "Aabha Chaudhary", 'F', 600);
	addemp(7, "Varun Tanjea", 'M', 700);
	addemp(8, "Ankit Bhardwaj", 'M', 800);
	change_sal(1, 1000);
	disemp();
	_getch();
	return 0;
	}

	void addemp(int eid, char *name, char sex, int salary)
	{
	struct empo help;
	FILE *fp;
	fp = fopen("Emp.txt", "rb+");
	if (fp == NULL)
		fp = fopen("Emp.txt", "wb");
	fseek(fp, 0, SEEK_END);
	help.eid = eid;
	strcpy(help.name, name);
	help.sex = sex;
	help.salary = salary;
	fwrite(&help, sizeof(help), 1, fp);
	fclose(fp);
	}

	void change_sal(int id, int new_salary)
	{
	struct empo help;
	int size = sizeof(help);
	FILE *fp;
	fp = fopen("Emp.txt", "rb+");
	if (fp == NULL)
		fp = fopen("Emp.txt", "wb");
	while (fread(&help, sizeof(help), 1, fp) == 1)
	{
		if (help.eid == id)
		{
			fseek(fp, -size, SEEK_CUR);
			help.salary = new_salary;
			fwrite(&help, sizeof(help), 1, fp);
			break;
		}
	}
	fclose(fp);

	}	

	void delemp(int id)
	{
	struct empo help;
	int size = sizeof(help);
	FILE *fp;
	fp = fopen("Emp.txt", "rb+");
	if (fp == NULL)
		fp = fopen("Emp.txt", "wb");
	while (fread(&help, sizeof(help), 1, fp) == 1)
	{
		if (help.eid == id)
		{
			fseek(fp, -size, SEEK_CUR);
			help.salary = 0;
			fwrite(&help, sizeof(help), 1, fp);
			break;
		}
	}
	fclose(fp);
	}

	void disemp()
	{
	struct empo help;
	FILE *fp;
	fp = fopen("Emp.txt", "rb");
	if (fp == NULL)
	{
		puts("\nFile is unable to open or did not exist.\nExiting. . .");
		exit(1);
	}
	while (fread(&help, sizeof(help), 1, fp) == 1)
	{
		printf("\n%2d", help.eid);
		printf("\t%-20s", help.name);
		printf("\t%c", help.sex);
		printf("\t%d\n", help.salary);
	}
	fclose(fp);
	}
(n)
	
		#include<stdio.h>
	#include<conio.h>
	#include<stdlib.h>
	#include<string.h>
	#include<Windows.h>

	#define FOUND (strcmp(word, "a") == 0 || strcmp(word, "an") == 0\
	|| strcmp(word, "the") == 0 || strcmp(word, "A") == 0\
	|| strcmp(word, "An") == 0 || strcmp(word, "The") == 0)

	void delart(char*);

	int main()

	{
	delart("Temp.txt");
	_getch();
	return 0;
	}

	void delart(char *file)
	{
	FILE *fp, *nf;
	int i;
	char word[20];
	fp = fopen(file, "r+");
	nf = fopen("NEW FILE.txt", "w");
	if (fp == NULL)
	{
		puts("\nCannot open the file.\n");
		exit(1);
	}
	for (i = 0; 1; i++)
	{
		word[i] = fgetc(fp);
		if (word[i] == EOF)
			break;
		if (word[i] == ' ')
		{
			word[i] = '\0';
			if (FOUND)
			{
				/*Replacing the word with the space*/
				strcpy(word, " ");
				fputs(word, nf);
			}
			else
			{
				fputs(word, nf);
				fputc(' ', nf);
			}
			i = -1;
			/*After the loop ends, i increament by 1,
			so -1 becomes 0 and	next character saved
			in the word[0]*/
		}
	}
	}
(o)
	
		#include<stdio.h>
	#include<conio.h>
	#include<stdlib.h>
	#include<string.h>
	#include<Windows.h>

	struct employee
	{
	int empno;
	char name[30];
	int basic, grade;
	};

	void addemp(int, char*, int, int, char*);
	void display(FILE*);
	void miss(FILE*);
	int main()
	{
	FILE *fp;
	addemp(1,"Kishor Dass", 100,  1, "File (o).txt");
 	addemp(2,"Amit Kumar Mandal", 101,2, "File (o).txt");
 	addemp(3,"Prakash babu Sharma", 100, 3, "File (o).txt");
 	addemp(4, "Mohd Seraj Alam", 123, 1, "File (o).txt");
 	addemp(5, "Priya Saxena", 100, 2, "File (o).txt");
 	addemp(9, "Varun Taneja", 120, 3, "File (o).txt");
	addemp(13, "Shahrukh", 123, 3, "File (o).txt");
	addemp(20, "Paras Chugh", 452, 1, "File (o).txt");
	puts("\nList of the employees.\n\n");
	fp = fopen("File (o).txt", "rb+");
	display(fp);
	_getch();
	system("cls");
	miss(fp);
	_getch();
	fclose(fp);
	return 0;
	}

	void addemp(int eid, char *name, int bas, int grad, char *file)
	{
	FILE *fp;
	struct employee dat;
	fp = fopen(file, "rb+");
	if (fp == NULL)
	{
		fp = fopen(file, "wb");
		if(fp == NULL)
		{
			printf("\nCannot open the file.\n");
			exit(1);	
		}
	}
	dat.empno = eid;
	strcpy(dat.name, name);
	dat.basic = bas;
	dat.grade = grad;
	fseek(fp, 0, SEEK_END);
	fwrite(&dat, sizeof(dat), 1, fp);
	fclose(fp);
	}

	void display(FILE *fp)
	{
	struct employee dat;
	while (fread(&dat, sizeof(dat), 1, fp) == 1)
	{
		printf("%2d", dat.empno);
		printf("\t%-20s", dat.name);
		printf("\t % 4d", dat.basic);
		printf("\t % 3d\n", dat.grade);
	}
	}

	void miss(FILE *fp)
	{
	int i = 1;
	struct employee dat;
	rewind(fp);
	puts("\nEmployees with following IDs are missing.");
	while (fread(&dat, sizeof(dat), 1, fp) == 1)
	{
		while(dat.empno != i)
		{
			printf("%d, ", i);
			i++;
		}
		i++;
	}
	}
(p)
	
		#include<stdio.h>
	#include<conio.h>
	#include<stdlib.h>
	#include<string.h>
	#include<Windows.h>

	#define EndOfWord word[i] == ' ' || word[i] == ','\
	 || word[i] == '.' || word[i] == '\n'

	int count_word(FILE*);
	void count_4_words(FILE*);

	int main()
	{
	FILE *fp;
	fp = fopen("File (p).txt", "r");
	if (fp == NULL)
	{
		puts("\nCan't open the file.");
		exit(1);
	}

	int count = count_word(fp);
	printf("\nThere are total %d words in file.\n", count);
	_getch();
	system("cls");
	count_4_words(fp);
	_getch();
	return 0;
	}

	int count_word(FILE *fp)
	{
	int i, count = 0;
	char word[20];
	for (i = 0; 1; i++)
	{
		word[i] = fgetc(fp);
		if (word[i] == EOF)
			break;

		/*A word ends if a space or comma or etc. encounter.*/
		if (EndOfWord)
		{

			/*If the 'word' variable contain only one letter and viz.
			'.' or ',' or ' ' or '\n' so it skips it as 
			it is not count as a word*/
			if (i != 0)		
				count++;

			i = -1;
		}
	}
	return count;
	fclose(fp);
	}

	void count_4_words(FILE *fp)
	{
	int i, count = 0;
	char word[20];
	if (fp == NULL)
	{
		puts("\nCan't open the file.");
		exit(1);
	}
	puts("\nTotal number of four letter words are following.\n");
	for (i = 0; 1; i++)
	{
		word[i] = fgetc(fp);
		if (word[i] == EOF)
			break;

		/*A word ends if a space or comma or etc. encounter.*/
		if (EndOfWord)
		{
			/*If the 'word' variable contain only one letter and viz.
			'.' or ',' or ' ' or '\n' so it skips it as
			it is not count as a word*/
			if (i != 0)		
			{
				if (i == 4)
				{
					/*Terminating the word before printing it*/
					word[i + 1] = '\0';
					puts(word);	
				}
			}
			i = -1; 
		}
	}
	fclose(fp);
	}
(q)

	#include<stdio.h>
	#include<conio.h>
	#include<stdlib.h>
	#include<string.h>
	#include<Windows.h>

	#define EndOfWord word[i][j] == ' ' || word[i][j] == ','\
	 || word[i][j] == '.' || word[i][j] == '\n'

	void swap(char*, char*);
	void list(FILE *);

	int main()
	{
	FILE *fp;
	fp = fopen("File (q).txt", "r");
	if (fp == NULL)
	{
		puts("\nCannot open the file.\n");
		exit(1);
	}
	list(fp);
	_getch();
	return 0;
	}

	void swap(char *one, char *two)
	{
	char three[20];
	strcpy(three, one);
	strcpy(one, two);
	strcpy(two, three);
	}

	void list(FILE *fp)
	{
	char word[30][20];
	int i = 0, j, count = 0, k1 = 0, k2 = 0;
	/* 'count' is used to count total number of words in the list,
	and k1 and k2 are used to locate k1th and k2th characters
	in Ist and IInd words respectively and 'i' is the first word 
	and 'j' is second*/
	for (j = 0; 1; j++)
	{
		word[i][j] = fgetc(fp);
		if (word[i][j] == EOF)
			break;
		/*A word may be ends with a space or a comma etc.*/
		if (EndOfWord)
		{
			if (j != 0)
			{
				word[i][j] = '\0';
				i++;
				/*It means, first word is successfully saved
				in word[i][j]. Increament in i takes 2-d array
				in next 1d array and save next word in it.*/
				count++;
			}
			/*If a word saved, so second word should be saved 
			with second index 0.*/
			j = -1;
		}
	}


	/*	Loop below is for sorting the words by alphabatical order a to z,
	and all words should have only upper or only lower case words.*/
	for (i = 0; i < count; i++)
	{
		for (j = i + 1; j < count; j++)
		{
			if (word[i][k1] > word[j][k2])
			{
				swap(word[i], word[j]);
				k1 = k2 = 0;
				/*If second word is smaller alphabatically, 
				so it will come in first by swapping them together*/
				continue;	
			}
			if (word[i][k1] < word[j][k2])
			{
				k1 = k2 = 0;
				/*If first word is smaller alphabatically, so next word
				is compared without making any changes*/
				continue;
			}
			if (word[i][k1] == word[j][k2])
			{
				/*If both the words are identical, so no action is taken*/
				if (word[i][k1 + 1] == '\0' && word[j][k2 + 1] == '\0')	
				{
					k1 = k2 = 0;
					continue;
				}
				/*	If one word is end and second is not so next character is
				ckecked of second word with the first character of first word,
				that means, only k2 increases and k1 remains same	*/
				if (word[i][k1 + 1] != '\0')
					k1++;
				if (word[j][k2 + 1] != '\0')
					k2++;
				/*Next character is checked of the same word, so j should be 
				decreament as it is also increamenting after every loop*/
				j--;
			}

		}
	}
	system("cls");
	printf("\nTotal number of words in the list is : %d\n", count);
	puts("Alphabatical listing of words is : ");
	for (i = 0; i < count; i++)
		printf("\n%-2d : %s", i + 1, word[i]);
	fclose(fp);
	}
(r)
	
	#include<stdio.h>
	#include<conio.h>
	#include<stdlib.h>
	#include<string.h>

	void frev(FILE*);

	int main()
	{
	FILE *fp;
	fp = fopen("File (r).txt", "r");
	if (fp == NULL)
	{
		puts("File cannot be opened.\n");
		exit(1);
	}
	frev(fp);
	fclose(fp);
	_getch();
	return 0;
	}

	void frev(FILE *fp)
	{
	char word[11];
	int i;
	for (i = 0; 1; i++)
	{
		word[i] = fgetc(fp);
		if (word[i] == EOF)
			break;
		if (word[i] == ' ' || word[i] == '\n')
		{
			/*Convert that space/newline to NULL character 
			to complete the word for printing*/
			word[i] = '\0';
			
			_strrev(word);
			printf("%s ", word);
			/*When i increament so i becomes 0 and a
            new word start to save in the word variable*/
			i = -1;
		}
	}
	}
(s)
	
	#include<stdio.h>
	#include<conio.h>
	#include<stdlib.h>
	#include<string.h>
	#include<Windows.h>

	void pagebreak(FILE *fp);

	int main()
	{
	FILE *fp;
	fp = fopen("NOTE.txt", "r");
	if (fp == NULL)
	{
		puts("Can't open the file.");
		exit(1);
	}
	pagebreak(fp);
	fclose(fp);
	_getch();
	return 0;
	}

		void pagebreak(FILE *fp)
	{
	/*Dot counts the numebr of lines*/
	int dot = 0;
	char ch;
	while (1)
	{
		ch = fgetc(fp);
		if (ch == EOF)
			break;
		printf("%c", ch);
		/*If a full stop appears so the line is terminated here*/
		if (ch == '.')
		{
			/*If dot == 50 so, 50 lines have been printed, 
			so a page breakmsg should be appear here*/
			if (dot == 50)
			{
				printf("Press any key. . .");
				_getch();
				system("cls");
				/*Dot variable reinitialization*/
				dot = 1;
			}
			else
				dot++;
		}

	}
	}
	
