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
