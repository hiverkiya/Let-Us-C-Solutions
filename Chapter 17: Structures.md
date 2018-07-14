# [Chapter 17: Structures] Solutions  

## [A] 
      
       (a) 1004 1008 1058
       (b)
             CrankShaft 102133
             CrankShaft 102133
             CrankShaft 102133
      (c) 2 If you are driven by success make sure that it is a quality drive
  
## [B]
 
      (a)age cannot be used without any object reference.
      (b) book is not any structure name. 
            b do not belong to any structure.
      (c) variable v in printf statement, should have some index,
      as it is an array of strcuture.
      (d)
       1. In f() function, structure is passed by value, so "." operator
       should be used.
      2. In g() function, structure is passed by its address, so "->"
      operator should be used.
      (e)   NO ERROR

## [C]
      
      (a) Array
      (b) 1 & 2 are true.
      (c) True,False,False.
      (d) 2 & 4
      (e)   
            1.  =  g. 25


      2.  =  h. 8
      i[7] = 2, s[7] = x=8/y=75,
      so s[7].x = 8 


      3.  =  b. 2
      3[i] = i[3] = 15,
      (s+2)->y = 75,
      75/15 = 3,
      s[3].y = 2


      4.  =  a. 75
      i[1] = 20, 1[2] = 15,
      20-15 = 5,
      i[5] = 75


      5.  =  f. 15
      s[3] = 2
      i[2] = 15


      6.  =  l. 20


      7.  =  e. 16
      *(1+i) = 20,
      *(i+4) = 8,
      *i = 10,
      20*8/10 = 16


      8.  =  a. 85
      i[0] = 10, i[4] = 8
      s[10-8].y = 75,
      75+10 = 85


      9.  =  k. 10
      *(i+1) = 20, *i = 10,
      s+(20/2) = x=8/y=75,
      *(s+2).x = 8,
      8+2 = 10


      10. =  d. 7
      i[6] = 6,
      ++6 = 7
## [D] 
      
      (a) 
      #include<stdio.h>
	#include<conio.h>
	#include<Windows.h>
	struct studata
	{
	int roll;
	char name[50];
	char depart[50];
	char course[20];
	int yoj;
	}nos[450] = { 03, "Kishor", "IT", "B.tech", 2014,
	10, "Mohammad Siraj Alam", "Computer Science", "B.Tech", 2014,
	53, "Deepak", "Computer Applications", "BCA", 2013,
	13, "Karan", "Mechanical", "Diploma", 2013,
	1, "Aakash", "Tool and Die", "Diploma", 2012,
	2, "Ramesh", "IT", "B.tech", 2014
	};
	void student_in_year(int year)
	{
	int i;
	printf("\n\t\tYear of joining : %d\n\n", year);
	for (i = 0; i <= 450; i++)
	{
		if (nos[i].yoj == year)
		{

			printf("\nRoll Number : %d", nos[i].roll);
			printf("\nName : %s", nos[i].name);
			printf("\nDepartment : %s", nos[i].depart);
			printf("\nCourse : %s\n", nos[i].course);
		}
	}
	}
	void student_data(int enroll)
	{
	int i;
	printf("\nRoll number : %d", enroll);
	for (i = 0; i <= 450; i++)
	{
		if (nos[i].roll == enroll)
		{
			printf("\nName : %s", nos[i].name);
			printf("\nDepartment : %s", nos[i].depart);
			printf("\nCourse : %s\n", nos[i].course);
			printf("\nYear of joining : %d\n", nos[i].yoj);
		}
	}
	}
	int main()
	{
	int yoj, roll;
	printf("\nEnter year of joining of the students : ");
	scanf("%d", &yoj);
	student_in_year(yoj);
	_getch();
	system("cls");
	printf("\nEnter the roll number of the studnet you want data : ");
	scanf("%d", &roll);
	student_data(roll);
	_getch();
	return 0;
	}
(b)

	#include<stdio.h>
	#include<conio.h>
	#include<Windows.h>

	/*Function to perform withdrawal or deposition*/
	void action(int, int, int);

	/*Print the balance below 100 Rs.*/
	void below100();

	struct acc_holder
	{
	long int acc_num;
	char name[30];
	int bal;
	} sbi[200] = { 1, "Siraj", 1000000,
	2, "Azad", 1233044,
	3, "Deepak", 99,
	4, "Rihan", 33,
	5, "Rahul Khowal", 200000
	};

	int main()
	{
	int accnum, amount, code;
	printf("\nEnter your account number : ");
	scanf("%d", &accnum);
	printf("Enter 1 for deposit and 0 for withdrawal : ");
	scanf("%d", &code);
	if (code)
	{
		printf("\nEnter amount to be deposit : ");
		scanf("%d", &amount);
	}
	else
	{
		printf("\nEnter amount to withdraw : ");
		scanf("%d", &amount);
	}
	action(accnum, amount, code);
	_getch();
	system("cls");
	printf("All members with account balance less than 100 are following : ");
	below100();
	_getch();
	return 0;
	}

	void below100()
	{
	int i;
	for (i = 0; i < 200; i++)
	{
		if (sbi[i].bal < 100 && sbi[i].bal > 0)
		{
			printf("\nName : %s", sbi[i].name);
			printf("\nAccount Number : %d\n\n", sbi[i].acc_num);
		}
	}
	}

	void action(int accnum, int amount, int code)
	{
	int i;
	for (i = 0; i < 200; i++)
		if (sbi[i].acc_num == accnum)
			break;
	if (!code)
	{
		if (sbi[i].bal - amount < 100)
		{
			printf("\nThe balance is insufficient for the specified withdrawal");
			return;
		}
		else
		{
			sbi[i].bal -= amount;
			printf("\nYour new account balance is : %d", sbi[i].bal);
		}
	}
	else
	{
		sbi[i].bal += amount;
		printf("\nYour new account balance is : %d", sbi[i].bal);
	}

	}
(c)

	#include<stdio.h>
	#include<conio.h>
	#include<Windows.h>

	void eng_info(char*, char*);

	struct engine
	{
	char serial[4];
	int yom;
	char mat[50];
	int quantity;
	}
	maruti[10] = { "AA0", 2005, "Iron", 20,
	"BB1", 2007, "Steel", 13,
	"BB2", 1992, "Aluminium", 57,
	"CC1", 2005, "Stainless Steel", 7,
	"CC6", 2007, "Steel", 34,
	"CC7", 2010, "Steel", 14
	};

	int main()
	{
	char from[5], to[5];
	printf("\nEnter the serial number, from where you want to start the list : ");
	scanf("%s", from);
	printf("\nEnter the serial at which you wan to end the list : ");
	scanf("%s", to);
	system("cls");
	eng_info(from, to);
	_getch();
	return 0;
	}

	void eng_info(char *from, char *to)
	{
		char first_letter;
	int last_digit;
	int i;
	printf("\n\t\tEngines Information\n");
	for (i = 0; maruti[i].serial[0] != *from; i++);
	while (1)
	{
		printf("\nSerial Number : %s", maruti[i].serial);
		printf("\nYear Of Manufacture : %d", maruti[i].yom);
		printf("\nMaterail Used : %s", maruti[i].mat);
		printf("\nQuantity : %d\n", maruti[i].quantity);
		if (i == 10)
			i = 0;
		i++;
		if (maruti[i].serial[0] == *to &&  maruti[i].serial[2] == *(to + 2))
		{
			printf("\nSerial Number : %s", maruti[i].serial);
			printf("\nYear Of Manufacture : %d", maruti[i].yom);
			printf("\nMaterail Used : %s", maruti[i].mat);
			printf("\nQuantity : %d\n", maruti[i].quantity);
			return;
		}
	}
	}
(d)

	#include<stdio.h>
	#include<conio.h>
	#include<stdlib.h>
	#define Max 20

	int compare(const void * a, const void * b);

	struct cricketers
	{
	int avrun;
	char name[30];
	int age;
	int notm;
	}india[Max] = {
	122, "Sachin Tendulkar", 30, 67,
	97, "Virendra Sehwag", 35, 56,
	66, "Irfan Pathan", 32, 45,
	153, "Yusuf Pathan", 36, 21,
	101, "Yuvaraj Singh", 32, 45,
	};

	int main()
	{
	int i;
	qsort(india, 5, sizeof(struct cricketers), compare);

	/*qsort() is a standard library function.
	
	view the link below for more info
	
	http://www.tutorialspoint.com/c_standard_library/c_function_qsort.htm
	
	*/

	for (i = 0; i < 5; i++)
	{
		printf("Name : %s", india[i].name);
		printf("\nAge : %d", india[i].age);
		printf("\nTotal Test Matches played : %d", india[i].notm);
		printf("\nAverage Run : %d\n\n\n", india[i].avrun);
	}
	_getch();
	return 0;
	}

	int compare(const void * a, const void * b)
	{
	return (*(int*)a - *(int*)b);
	}
(e)

	#include<stdio.h>
	#include<conio.h>

	void printinfo(struct employee k);

	struct employee
	{
	int code;
	char name[30];
	int doj[3];
	}hcl[50] = {

	001, "Shahnawaz", 13, 1,2006,
	004, "Amit Puri", 21, 6,2008,
	102, "Irfan Moin", 12, 5, 2012,
	131, "Shabnam", 16, 1, 2014
	};

	int main()
	{
	int i, d[3];
	printf("\nEnter the current date (dd mm yyyy) : ");
	scanf("%d%d%d", &d[0], &d[1], &d[2]);
	printf("\nEmployees with greater than or equal to 3 years of tenure\n\n");
	for (i = 0; i < 4; i++)
	{
		if (d[2] - hcl[i].doj[2] > 3)
			printinfo(hcl[i]);
		else if (d[2] - hcl[i].doj[2] == 3)
		{
			if (d[1] - hcl[i].doj[1] > 0)
				printinfo(hcl[i]);
			else if (hcl[i].doj[1] == d[1])
			{
				if (d[0] - hcl[i].doj[0] >= 0)
					printinfo(hcl[i]);

			}
		}
	}
	_getch();
	return 0;
	}

	void printinfo(struct employee e)
	{
	printf("\nCode : %d", e.code);
	printf("\nName : %s", e.name);
	printf("\nDate of joining : %d-%d-%d\n", e.doj[0], e.doj[1], e.doj[2]);
	}
(f)

	#include<stdio.h>
	#include<conio.h>
	#include<string.h>
	#include<Windows.h>

	/*Count total number of books in the library*/
	int count();

	void display(int);

	/*If the author name is same so the function strcmp returns a zero*/
		void giv_author(char*);
	void adbuk();

	/*Appears the title of the specified book*/
	void which1(int);

	/*Displays all the books serially accession number*/
	void albuk();

	struct library
	{
	int an;/*Accession number*/
	char title[50];
	char author[30];
	int price;
	int flag;/*flag = 0 : Issued and,flag =  1: not issued*/
	}geclib[50] = {
	1, "Let Us C", "Yashavant Kanethkar", 258, 1,
	2, "Data Structure Through C", "Yashavant Kanethkar", 300, 1,
	3, "Let Us C++", "Yashavant Kanethkar", 220, 1,
	4, "Harry Potter : The Philosopher's Stone", "J. K. Rowling", 550, 0,
	5, "The Two Towers", "J. R. R. Tolkien", 560, 0,
	6, "The Hobbit", "J. R. R. Tolkien", 550, 1,
	7, "The Fellowship of the Ring", "J. R. R. Tolkien", 550, 0
	};

	int main()
	{
	int ans = 1, an;
	char auth[30];
	while (ans != 7)
	{
		system("cls");
		printf("\nYou are in menu section\n");
		printf("\n1. Add Book Information");
		printf("\n2. Display Book Information");
		printf("\n3. List all books of given author");
		printf("\n4. List the title of specified book");
		printf("\n5. List the counts of the books in library");
		printf("\n6. List the books in order of accession number");
		printf("\n7. Exit");
		printf("\n\n\t\tEnter you choice : ");
		scanf("%d", &ans);
		switch (ans)
		{
		case 1:
			adbuk();
			_getch();
			break;
		case 2:
			printf("\nEnter the accession number of the book : ");
			scanf("%d", &an);
			display(an);
			_getch();
			break;
		case 3:
			while (getchar() != '\n');
			printf("Enter the name of the author (case sensitive) : ");
			gets_s(auth);
			giv_author(auth);
			_getch();
			break;
		case 4:
			printf("\nEnter the accession number of book : ");
			scanf("%d", &an);
			which1(an);
			_getch();
			break;
		case 5:
			printf("\nTotal Number of books : %d", count());
			_getch();
			break;
		case 6:
			albuk();
			_getch();
			break;
		case 7:
			return 0;
		default:
			printf("\nWrong choice, Try Again!!");
			_getch();

		}
	}
	_getch();
	return 0;
	}

	int count()
	{
	int i = 0;
	while (geclib[i].an)
		i++;
	return i;
	}

	void display(int i)
	{
	i--;/*To use i as index*/
	printf("\n\n\n");
	printf("\nAccession Number : %d", geclib[i].an);
	printf("\nTitle : %s", geclib[i].title);
	printf("\nAuthor : %s", geclib[i].author);
	printf("\nPrice : %d", geclib[i].price);
	if (geclib[i].flag)/*Flag : 0*/
		printf("\nStatus : Issued");
	else
		printf("\nStatus : Available");/*Flag : 1*/
	}
	
	void giv_author(char *author)
	{
	int i = 0;
	printf("\nBooks of \"%s\" are following : \n\n", author);
	while (geclib[i].an)
	{
		if (!(strcmp(author, geclib[i].author)))
			display(geclib[i].an);
		i++;
	}
	}

	void adbuk()
	{
	int next = count();
	geclib[next].an = next + 1;

	/*fflush(stdin) or while(getch() != '\n'); to clear the buffer*/
	while (getchar() != '\n');
	printf("\nEnter the title of the book : ");
	gets_s(geclib[next].title);
	printf("\nEnter the author name of the book : ");
	gets_s(geclib[next].author);
	printf("\nEnter the price of the book : ");
	scanf("%d", &geclib[next].price);
	geclib[next].flag = 1;
	system("cls");
	}

	void which1(int an)
	{
	int i = 0;
	while (geclib[i].an)
	{
		if (geclib[i].an == an)
		{
			printf("\n\nTitle of the book : %s\n", geclib[i].title);
			return;
		}
	}
	printf("No any book found found\n");
	}

	void albuk()
	{
	int i = 0;
	while (geclib[i].an)
	{
		display(i + 1);
		i++;
	}
	}
(g)

	#include<stdio.h>
	#include<conio.h>
	struct dmy
	{
	int date;
	int month;
	int year;
	};

	int datcmp(struct dmy a, struct dmy b)
	{
	if (a.date == b.date && a.month == b.month && a.year == b.year)
		return 0;
	else
		return 1;
	}

	int main()
	{
	struct dmy a, b;
	int flag;
	printf("\nEnter the first date (dd mm yyyy) : ");
	scanf("%d%d%d", &a.date, &a.month, &a.year);
	printf("\nEnter the second date (dd mm yyyy) : ");
	scanf("%d%d%d", &b.date, &b.month, &b.year);
	flag = datcmp(a, b);
	if (flag)
		printf("\nThe dates are not same\n");
	else
		printf("\nThe dates are same\n");
	_getch();
	return 0;
	}
(h)

	#include<stdio.h>
	#include<conio.h>
	#include<malloc.h>
	#include<stdlib.h>
	#include<Windows.h>
	#define GetSize (struct node*)malloc(sizeof(struct node))

	void insert(struct node**, int);
	void del(struct node**, int);
	void display(struct node*);

	struct node
	{
	int data;
	struct node* next;
	};

	int main()
	{
	char ans = 'y';
	int num, exit = 1, action;
	struct node *start = NULL;
	printf("\nHello all, this program is of linked list, so go ahead and make your limked list\n\n");
	while (ans == 'y')
	{
		printf("\nEnter the data : ");
		scanf("%d", &num);
		insert(&start, num);
		printf("\nWant to enter another number (y/n) : ");
		while (getchar() != '\n');
		scanf("%c", &ans);
	}
	system("cls");
	while (exit != 0)
	{
		system("cls");
		display(start);
		printf("\n\n\nYou are in menu section\n\n");
		printf("\n0 : Exit\n1 : Insert\n2 : Delete\n3 : Display");
		printf("\n\n\nEnter your choice : ");
		scanf("%d", &action);
		switch (action)
		{
		case 0:
			printf("\nYou are exiting. . . .");
			_getch();
			return 0;
		case 1:
			printf("\nEnter number : ");
			scanf("%d", &num);
			insert(&start, num);
			break;
		case 2:
			printf("\nEnter number to delete : ");
			scanf("%d", &num);
			del(&start, num);
			break;
		case 3:
			display(start);
			break;
		default:
			printf("\nYou have entered a wrong option\,Try againA!!\n");
			exit = 1;
		}
	}
	_getch();
	return 0;
	}

	void insert(struct node **start, int num)
	{
	struct node *help = NULL, *curr = NULL;
	help = GetSize;
	help->data = num;/*This is our new node.*/
	help->next = NULL;
	
	if (*start == NULL)/*Inserting the first element*/
	{
		*start = help;
		return;
	}

	/*Finding the position for the number to insert*/
	for (curr = *start; curr->next != NULL; curr = curr->next);

	curr->next = help;
	}

	void del(struct node **start, int num)
	{
	struct node *curr = *start, *pre = NULL;

	/*Finding the data to be deleted */
	while (curr->data != num)
	{
		pre = curr;
		curr = curr->next;

		/*List ends and the number nor found.*/
		if (curr == NULL)
			break;
	}

	/*Deleting the first node*/
	if (curr == *start)
		*start = curr->next;
	else if (curr == NULL)/*Number not found so just return*/
	{
		printf("\nNumber is not present in the list.");
		return;
	}
	else/*Deleting in between or last node*/
		pre->next = curr->next;

	free(curr);/*Deletion*/
	}

	void display(struct node *start)
	{
	struct node *i = NULL;
	printf("\nYour list\n");
	for (i = start; i != NULL; i = i->next)
		printf("%d\t", i->data);
	}
(i)

	#include<stdio.h>
	#include<conio.h>
	#include<malloc.h>
	#include<stdlib.h>
	#include<Windows.h>

	#define GetSize (struct node*)malloc(sizeof(struct node))

	void push(struct node**, int);
	int pop(struct node**);

	struct node
	{
	int data;
	struct node* next;
	};

	int main()
	{
	char ans = 'y';
	int num, exit = 1, action;
	struct node *top = NULL;
	printf("\nHello all, this program is of stacks using linked list, so");
	printf("go ahead and make your linked list that will saved in stacks.\n\n");
	while (ans == 'y')
	{
		printf("\nEnter the data : ");
		scanf("%d", &num);
		push(&top, num);
		printf("\nWant to enter another number (y/n) : ");
		while (getchar() != '\n');
		scanf("%c", &ans);
	}
	system("cls");
	while (exit != 0)
	{

		printf("\n\n\nYou are in menu section\n\n");
		printf("\n0 : Exit\n1 : Push\n2 : Pop");
		printf("\n\n\nEnter your choice : "); +
			scanf("%d", &action);
		switch (action)
		{
		case 0:
			printf("\nYou are exiting. . . .");
			_getch();
			return 0;
		case 1:
			printf("\nEnter number : ");
			scanf("%f", &num);
			push(&top, num);
			system("cls");
			break;
		case 2:
			system("cls");
			if (num == NULL)
			{
				printf("\nStack is empty");
				break;
			}
			num = pop(&top);
			printf("\n\n%d is popped.", num);
			break;
		default:
			printf("\nYou have entered a wrong option\,Try againA!!\n");
			exit = 1;
		}
	}
	_getch();
	return 0;
	}	

	/*Push means adding an element in the stack*/
	void push(struct node **top, int num)
	{
	struct node *temp = NULL, *help = NULL;
	help = GetSize;

	if (help == NULL)
	{
		printf("\nStack is full!!");
		return;
	}

	help->data = num;
	help->next = *top;

	/*Last added element is always the top element.*/
	*top = help;
	}

	/*Pop means isolating the top element from the stacks.*/
	int pop(struct node **top)
	{
	struct node *temp = GetSize;
	int num;
	if (*top == NULL)
		return NULL;
	num = (*top)->data;
	temp = *top;
	*top = (*top)->next;
	free(temp);
	return num;
	}
(j)

	#include<stdio.h>
	#include<conio.h>
	#include<malloc.h>
	#include<stdlib.h>
	#include<Windows.h>

	#define GetSize (struct node*)malloc(sizeof(struct node))

	void add(struct node**, struct node**, int);
	int del(struct node**, struct node**);
	void display(struct node*);

	struct node
	{
	int data;
	struct node* next;
	};

	int main()
	{
		char ans = 'y';
	int num, exit = 1, action;
	struct node *start = NULL, *end = NULL;
	printf("\nHello all, this program is of queue using linked list, ");
	printf("so go ahead and make your linked list that wil saved in a queue.\n\n");
	while (ans == 'y')
	{
		printf("\nEnter the data : ");
		scanf("%d", &num);
		add(&start, &end, num);
		printf("\nWant to enter another number (y/n) : ");
		while (getchar() != '\n');
		scanf("%c", &ans);
	}
	display(start);
	system("cls");
	while (exit != 0)
	{
		display(start);
		printf("\n\n\nYou are in menu section\n\n");
		printf("\n0 : Exit\n1 : Add\n2 : Remove\n3 : Display");
		printf("\n\n\nEnter your choice : "); +
			scanf("%d", &action);
		switch (action)
		{
		case 0:
			printf("\nYou are exiting. . . .");
			_getch();
			return 0;
		case 1:
			printf("\nEnter number : ");
			scanf("%d", &num);
			add(&start, &end, num);
			display(start);
			system("cls");
			break;
		case 2:
			system("cls");
			if (num == NULL)
			{
				printf("\nQueue is empty!!");
				break;
			}
			num = del(&start, &end);
			printf("\n%d has been extracted.\n\n", num);
			break;
		case 3:
			display(start);
			break;
		default:
			printf("\nYou have entered a wrong option\,Try againA!!\n");
			exit = 1;
		}
	}
	_getch();
	return 0;
	}

	void add(struct node **start, struct node **end, int num)
	{
	struct node *help = NULL;
	help = GetSize;
	help->data = num;
	help->next = NULL;
	if (*start == NULL)
	{
		*start = help;
		*end = help;
		return;
	}
	(*end)->next = help;
	*end = help;
	}
	
	int del(struct node **start, struct node **end)
	{
	struct node *temp;
	int num;
	temp = GetSize;
	if (*start == NULL)
		return NULL;
	temp = *start;
	num = temp->data;

	*start = (*start)->next;

	free(temp);
	return num;
	}

	void display(struct node *start)
	{
		struct node *a = start;
	while (a != NULL)
	{
		printf("%d\t", a->data);
		a = a->next;
	}
	}
(k)
	#include<stdio.h>
	#include<conio.h>
	#include<malloc.h>
	#include<stdlib.h>
	#include<Windows.h>

	#define GetSize (struct node*)malloc(sizeof(struct node))

	void insert(struct node**, int);
	void del(struct node**, int);
	void display(struct node*);

	struct node
	{
	int data;
	struct node* next;
	};

	int main()
	{
	char ans = 'y';
	int num, exit = 1, action;
	struct node *start = NULL;
	printf("\nHello all, this program is of linked list, so go ahead and make your limked list\n\n");
	while (ans == 'y')
	{
		printf("\nEnter the data : ");
		scanf("%d", &num);
		insert(&start, num);
		printf("\nWant to enter another number (y/n) : ");
		while (getchar() != '\n');
		scanf("%c", &ans);
	}
	system("cls");
	while (exit != 0)
	{
		display(start);
		printf("\n\n\nYou are in menu section\n\n");
		printf("\n0 : Exit\n1 : Insert\n2 : Delete\n3 : Display");
		printf("\n\n\nEnter your choice : ");
		scanf("%d", &action);
		switch (action)
		{
		case 0:
			printf("\nYou are exiting. . . .");
			_getch();
			return 0;
		case 1:
			system("cls");
			printf("\nEnter number : ");
			scanf("%d", &num);
			insert(&start, num);
			display(start);
			break;
		case 2:
			system("cls");
			printf("\nEnter number to delete : ");
			scanf("%d", &num);
			del(&start, num);
			display(start);
			break;
		case 3:
			display(start);
			break;
		default:
			printf("\nYou have entered a wrong option\,Try againA!!\n");
			exit = 1;
		}
	}
	_getch();
	return 0;
	}

	void insert(struct node **start, int num)
	{
	struct node *help = NULL, *curr = NULL, *pre = NULL;
	help = GetSize;
	help->data = num;/*This is our new node.*/
	if (*start == NULL)/*Inserting the first element*/
	{
		help->next = NULL;
		*start = help;
		return;
	}

	for (curr = *start; curr->data <= num; pre = curr, curr = curr->next)
		if (curr->next == NULL)
			break;
	
	if (curr == *start && num < curr->data)
	{
		help->next = *start;
		*start = help;
	}
	else if (curr->next == NULL && num > curr->data)
	{
		curr->next = help;
		help->next = NULL;
	}
	else/*Insertion in between*/
	{
		pre->next = help;
		help->next = curr;
	}

	}
	
	void del(struct node **start, int num)
	{
	struct node *curr = *start, *pre = NULL;
	while (curr->data != num)
	{
		pre = curr;
		curr = curr->next;
		if (curr == NULL)
			break;
	}
	if (curr == *start)
		*start = curr->next;
	else if (curr == NULL)
	{
		printf("\nNumbe is not present in the list.");
		return;
	}
	else
		pre->next = curr->next;
	free(curr);
	}

	void display(struct node *start)
	{
	struct node *i = NULL;
	printf("\nYour list\n");
	for (i = start; i != NULL; i = i->next)
		printf("%d\t", i->data);
	}
(l)

	#include<stdio.h>
	#include<conio.h>

	int main()
	{
	int wind;
	char cat;
	printf("\nEnter the speed of the wind (in miles/hour) : ");
	scanf("%d", &wind);
	if (wind < 73)
		printf("\nCool down man, this isn't a hurricane");
	else if (wind > 73 || wind < 96)
		cat = 'I';
	else if (wind > 95 || wind < 111)
		cat = 'II';
	else if (wind > 110 || wind < 131)
		cat = 'III';
	else if (wind > 130 || wind < 156)
		cat = 'IV';
	else
		cat = 'V';
	printf("\nThe wind speed belongs to the Hurricane Category '%c'", cat);
	_getch();
	return 0;
	}
(m)

	#include<stdio.h>
	#include<conio.h>
	#include<windows.h>
	struct marks
	{
	int j[3];
	int tot;
	};

		int main()
	{
	struct marks player[5];
	int i, j, max = 0;
	for (i = 0; i < 5; i++)
	{
		system("cls");
		printf("\n\t\tMarks for player-%d", i + 1);
		for (j = 0; j < 3; j++)
		{
			printf("\nEnter marks entered by judege number %d : ", j + 1);
			scanf("%d", &player[i].j[j]);
		}
		player[i].tot = player[i].j[0] + player[i].j[1] + player[i].j[2];
		if (player[i].tot > max)
			max = player[i].tot;
	}
	for (i = 0; i < 5; i++)
	{
		if (max == player[i].tot)
		{
			printf("\nPlayer number %d is choosen as MVP\n", i + 1);
			_getch();
			return 0;
		}
	}
	}

      
