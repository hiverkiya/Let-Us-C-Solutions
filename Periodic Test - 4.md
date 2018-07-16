# [Periodic Test-4] Solutions

## [A]
   
     (1) Hexadecimal values
     (2) Integers
     (3) Signal Handler
     (4) sigprocmask;
     (5) Complement
   
## [B]
    
    (1) False
    (2) True
    (3) False
    (4) True
    (5) True
    
    
## [C]
    
    THESE QUESTION'S ANSWERS ARE EASILY AVAILABLE ON INTERNET.
    
    
    
## [D]

  (1)
  
      #include<stdio.h>

         main()
      {
    int a, b, result;
    printf("\nEnter the numbers to be multiplied:");
    scanf("%d%d", &a, &b);       // a > b
    result = 0;
    while (b != 0)               // Iterate the loop till b == 0
    {
        if (b & 01)               // Bitwise & of the value of b with 01
        {
            result = result + a;  // Add a to result if b is odd .
        }
        a<<=1;                    // Left shifting the value contained in 'a' by 1
                                  // Multiplies a by 2 for each loop
        b>>=1;                    // Right shifting the value contained in 'b' by 1.
    }
    printf("nResult:%d",result);
      }

(2)

      #include<stdio.h>
      #include<conio.h>
      #include<ctype.h>
      void main()
      {
      FILE *f;
      char ch;
      int line=0,word=0;
      clrscr();
      f=fopen("student","w");
      printf("Enter text press ctrol+z to quit\n");
      do
      {
      ch=getchar();
      putc(ch,f);
      }
      while(ch!=EOF);
      fclose(f);
      f=fopen("student","r");
      while((ch=getc(f))!=EOF)
      {
      if(ch=='\n')
      line++;
      if(isspace(ch)||ch=='\t'||ch=='\n')
      word++;
      putchar(ch);
      }
      fclose(f);
      printf("\n no of line=%d\n",line);
      printf("no of word=%d\n",word);
      getch();
      }

(3)

      SIMILAR CODE AVAILABLE IN CHAPTER RELATED TO THIS TOPIC.

(4)
 
      #include<stdio.h>
 
      int main() {
    FILE *fp1, *fp2;
    int ch1, ch2;
    char fname1[40], fname2[40];
 
    printf("Enter name of first file :");
    gets(fname1);
 
    printf("Enter name of second file:");
      gets(fname2);
 
      fp1 = fopen(fname1, "r");
      fp2 = fopen(fname2, "r");
 
    if (fp1 == NULL) {
      printf("Cannot open %s for reading ", fname1);
      exit(1);
      } else if (fp2 == NULL) {
      printf("Cannot open %s for reading ", fname2);
      exit(1);
      } else {
      ch1 = getc(fp1);
      ch2 = getc(fp2);
 
      while ((ch1 != EOF) && (ch2 != EOF) && (ch1 == ch2)) {
         ch1 = getc(fp1);
         ch2 = getc(fp2);
      }
 
      if (ch1 == ch2)
         printf("Files are identical n");
      else if (ch1 != ch2)
         printf("Files are Not identical n");
 
      fclose(fp1);
      fclose(fp2);
      }
    return (0);
      }
