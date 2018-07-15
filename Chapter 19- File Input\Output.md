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
