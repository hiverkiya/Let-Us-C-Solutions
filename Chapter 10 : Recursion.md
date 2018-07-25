# [Chapter 10: Recursion ] Solutions

## [A]
  
    (a) Infinite Print C adds wings to your thoughts.
    (b) C adds wings to your thoughts.
  
## [B]

   (a) 
   
      #include<stdio.h>
      #include<conio.h>

    int nonrec_calc(int);
      int rec_calc(int);

      int main()
    {
	int num, sum;

	printf("Enter a five digit number : ");
	scanf("%d", &num);

	sum = nonrec_calc(num);
	printf("\n\nSum of digits using non-recursive function : %d\n", sum);
	
	sum = rec_calc(num);
	printf("\n\nSum of digits using recursive function: %d\n", sum);
	
	_getch();
	return 0;

    }

    //Non recursive function
    int nonrec_calc(int num)
    {
	int a, sum = 0, i;
	for (i = 0; num; i++)
	{
		a = num % 10;//obtaining the ladt digit
		sum = sum + a;//summing up the digits
		num = num / 10;//decreasing the number by one digit
	}
	return (sum);
    }

      //Recursive function
    int rec_calc(int num)
    {
	int sum = 0;
	if (num == 0)
		return sum;
	sum = num % 10 + rec_calc(num / 10);
	return sum;
    }
      
   (b) 
        
       int func(int num);
        #include <stdio.h>
      int main()
    {   int number;

    printf("Enter number\n");
    scanf("%d",&number);
    func(number);
    return 0;
      }
      int func(int num)
      {
    int i;
    for(i=2;i<=num;i++)
    {
        if(num%i==0)
        {
            printf("%d\n",i);
            func(num/i);
            break;
        }
    }
    return 0;
    }
  
  (c)
   
      #include<stdio.h>
    #include<conio.h>

    void fs(int first, int second, int term);

    int main()
      {
	fs(0, 1, 25);
	_getch();
	return 0;
    }

    void fs(int fis, int sec, int term)
    {
	int num;
	if (term == 0)
		return;
	num = fis + sec;
	fis = sec;
	sec = num;
	printf("%d, ", num);
	fs(fis, sec, term - 1);
    }
   
   (d)
   
   (1) Without Recursion  
          
          void nonrec_bin(int);
          #include<stdio.h>
          int main()
          {
            int number;
            printf("Enter number\n");
            scanf("%d",&number);
            nonrec_bin(number);
            return 0;
            }
          void nonrec_bin(int num)
      {
	int sum = 0;
	for (; num; num /= 2)
	{
		//Next digit will placed at first position.
		sum += num % 2;
		sum *= 10;
	}
	printf("%d", sum);
    }
   
    
   
   (2) With recursion
          
          #include<stdio.h>
      int bin(int);
      int main()
      {   int number;
    printf("Enter number\n");
    scanf("%d",&number);
    bin(number);
    return 0;
      }
      int bin(int number)
        {
    if(number>1)
    {
        bin(number/2);
    }
    printf("%d",number%2);

    return 0;
    }
  
  (e)
   
    int sum(int);
     int main()
      {   int number,ans;
    printf("Enter number\n");
    scanf("%d",&number);
    ans=sum(number);
    printf("%d",ans);
    return 0;
      }
  
    int sum(int x)
     {
	if (x == 0)
		return x;
	x = x + sum(x - 1);
	return x;
      }
