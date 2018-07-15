# [Chapter 20: More Issues on Input/Output] Solutions

## [A]
  
      (a)	
        Let the file name is �prog.c� so its executable file will be �prog.exe�. Now,
	type this command in the command prompt
	(1) - To copy the content of one file into another.
	prog.exe > File1.txt < File2.txt
	Input from file1 and put output in file 2

	(2)
	 To create a new file and add some text to it.
	prog.exe < NewFile.txt
	Input from keyboard and output in the file specified.

	(3) To display contents of an existing file.
	prog.exe > File1.txt
	Input from the file1 and output in the screen
    
    (b) False,True,True
    
    (c) Syntax error in second argument

## [B]
    (a)
    
 	#include<stdio.h>
	#include<conio.h>
	#include<string.h>
	#include<stdlib.h>

	#define EndOfWord word[i] == ' ' || word[i] == ',' \
	|| word[i] == '\n' || word[i] == '.'

	int main(int ac, char *av[])
	{
	FILE *fp, *temp;
	int i, j;
	char word[10], ch;
	if (ac != 4)
	{
		puts("Wrong number of arguements\n.");
		printf("Write like this : ");
		printf("\"change\" \"old_word\"");
		printf("\"new_word\" \"file_name\"\n");
		exit(1);
	}
	fp = fopen(av[3], "r");
	temp = fopen("temp.txt", "w");
	if (fp == NULL)
	{
		perror("Error : ");
		exit(1);
	}
	for (i = 0; (word[i] = fgetc(fp)) != EOF; i++)
	{
		if (EndOfWord)
		{
			ch = word[i];
			word[i] = '\0';
			if (!strcmp(av[1], word))
				fputs(av[2], temp);
			else
				fputs(word, temp);
			fputc(ch, temp);
			i = -1;
		}
	}
	fclose(fp);
	fclose(temp);
	remove(av[3]);
	rename("temp.txt", av[3]);
	return 0;
	}
(b)

	#include<stdio.h>
	#include<conio.h>
	#include<string.h>
	#include<stdlib.h>

	int main(int ac, char *av[])
	{
	int i, a, b;
	a = b = 0;
	if (ac != 4)
	{
		puts("Wrong number of arguements");
		printf("\n.Write like this : ");
		printf("\"calc\" \"switch\"");
		printf("\"number 1\" \"number 2\"\n");
		exit(1);
	}
	for (i = 0; av[2][i] != '\0'; i++)
	//Converting av[2][i] string into numeric and saving in "a".
	{
		a *= 10;
		a = av[2][i] - 48;
	}
	for (i = 0; av[3][i] != '\0'; i++)
	//Converting av[3][i] string into numeric and saving in "b".
	{
		b *= 10;
		b = av[3][i] - 48;
	}
	switch (av[1][0])
	{
	case '+':
		printf("%d %c %d = %d", a, av[1][0], b, a + b);
		break;
	case '-':
		printf("%d %c %d = %d", a, av[1][0], b, a - b);
		break;
	case '/':
		printf("%d %c %d = %.2f", a, av[1][0], b, float(a) / float(b));
		break;
	case '*':
		printf("%d %c %d = %d", a, av[1][0], b, a * b);
		break;
	case '%':
		printf("%d %c %d = %d", a, av[1][0], b, a % b);
		break;
	case '<':
		if (a < b)
			printf("%d %c %d is True.", a, av[1][0], b);
		else
			printf("%d %c %d is False.", a, av[1][0], b);
		break;
	case '>':
		if (a > b)
			printf("%d %c %d is True.", a, av[1][0], b);
		else
			printf("%d %c %d is False.", a, av[1][0], b);
		break;
	case '=':
		if (a == b)
			printf("%d %c %d is True.", a, av[1][0], b);
		else
			printf("%d %c %d is False.", a, av[1][0], b);
		break;
	default:
		printf("Operator '%c' is not found.\n", av[1][0]);
	}
	_getch();
	return 0;
	}
