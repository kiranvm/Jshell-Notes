﻿# JShell
## Introduction
Java shell gives you the benefit of quick validations with out the need of writing the supporting classes and functions for running the required code. 

This is comparable to interpreters of Languages like Python, Perl etc where you can type a line and see what response it will be giving out.

Jshell tries to achieve Begineer Friendliness by trying to minimize learning curve.
JShell is a prompt to execute Java Syntax statement.

eg:

<code>
jshell> Integer.MAX_VALUE+1

-2147483648
</code>

<b> REPL (Read Evaluate Print Loop) </b>
 
 This is the behaviour of all the shells/prompts. Jshell does the same.

## Setup
Jshell is supported from Java 9 onwards.
Download from here : https://www.java.com/en/download/
Check the version of java and ensure it is 9 or above:

<code>
$ java -version
</code>

## Running Jshell
Incase of linux
<code>
$ jshell
</code>

Incase of windows, go to bin folder in Java installation folder.
Execute the jshell.exe file.

## Type of statements
1. Java statements

<code>
jshell> 1+1

2
</code>

2. JShell Commands

 <code>
 jshell> /exit
 </code>
 
 
 See list of JShell Commands here: https://docs.oracle.com/javase/10/jshell/commands.htm#JSHEL-GUID-34165A38-E6D0-459D-9947-4DEA9845A71A
 
 ## Features
 1. Auto Complete
    Press Tab to auto complete
    
 2. Retaining variables and application logic.
    
    <code>
     jshell> int i   

     jshell> i = 20  

     jshell> int func(int c){return c*10;}

     |  created method func(int)

     jshell> func(100)  
     $6 ==> 1000jshell> int i   
66
​
67
     jshell> i = 20  
68
​
69
     jshell> int func(int c){return c*10;}
70
​
71
     |  created method func(int)
72
​
73
     jshell> func(100)  
74
     $6 ==> 1000
75
​
76
     jshell> func(20)  
77
     $7 ==> 200

     jshell> func(20)  
     
     $7 ==> 200
     
    </code>  
   This is similar to python shell.
 
 3. Scratch Variables  
 
 As you have seen in the output. Scratch variables are temperory variables created by JShell. These are usually denoted with a $ in prefix. $6 & $7 in line item 2 are scratch variables. /vars command lists all the variables you have right now.
 
 <code>
 
 jshell> /vars  
 
 |    int x = 10  
 
 |    int $6 = 1000  
 
 |    int $7 = 200
 
 </code>
 
 4. History of commands  
 
 Use up and down arrow to list previous commands. Alternatively you can use /history to see all commands you typed so far.  
 
 <code>

 /help  
 int x = 10;  
 x+10;  
 $2
 </code> 
 
 /list is a better option which lists only java statements and helps you to reuse the statements. 
 
 <code>
 jshell> /list  
 
    1 : int x = 10;  
 
    3 : $2
 
 </code>  
 
 <code>
 
 jshell> /1  
 
 int x = 10;  
 
 x ==> 10
 
 </code>  
 
 /methods gives the list of methods you created  
  <code>
 jshell> /methods
 
 |    int func(int)
 
 </code>
  
 5. Reverse Lookup  
 Search for a statement/command that you executed in reverse chronological order by pressing ctrl+r .
 
 5. Forward Lookup  
 Search for a statement/command that you executed in chronological order by pressing ctrl+s .
 
 6. Complete reset of state  
 Use /reset to reset complete state of the shell now.
  
 7. Multi-line statements (Code-Blocks)
 <code>jshell> if(x == 10){  
    ...> System.out.println("x is 10");  
    ...> }  
 x is 10
 </code> 
 
 8. Internal Library Functions  
 <code>jshell> Arrays.sort(new int[]{6,4,2,1});   
 jshell> int[] temp = new int[]{6,5,4,3,2,1};  
 temp ==> int[6] { 6, 5, 4, 3, 2, 1 }   
 jshell> Arrays.sort(temp);  
 jshell> temp  
 temp ==> int[6] { 1, 2, 3, 4, 5, 6 }
 </code>
 
 9. Forward References  
 Allows you to create variables/methods that are not yet created when you use them.  
     <code>jshell> int add(){  
        ...>   return i+j;  
        ...> }  
     |  created method add(), however, it cannot be invoked until variable j is declared  
     jshell> add();  
     |  attempted to call method add() which cannot be invoked until variable j is declared  
     jshell> int j = 20;  
     j ==> 20  
     jshell> add()  
     $5 ==> 30
     </code>
 10. Importing libraries
  JShell automatically imports certain set of imports.
  To see auto import list type /imports.  
  <code>jshell> /imports  
        |    import java.io.*  
        |    import java.math.*  
        |    import java.net.*  
        |    import java.nio.file.*  
        |    import java.util.*  
        |    import java.util.concurrent.*  
        |    import java.util.function.*  
        |    import java.util.prefs.*  
        |    import java.util.regex.*  
        |    import java.util.stream.*
  </code>  
  Otherwise import works just like the way it is in other shells(Press tab to auto complete).  
      <code>
        jshell> import java.  
        applet.     awt.        beans.      io.         lang.       math.       
        net.        nio.        rmi.        security.   sql.        text.       
        time.       util.       
        
        jshell> import java.time.
        Clock               DateTimeException   DayOfWeek           
        Duration            Instant             LocalDate           
        LocalDateTime       LocalTime           Month               
        MonthDay            OffsetDateTime      OffsetTime          
        Period              Year                YearMonth           
        ZoneId              ZoneOffset          ZonedDateTime       
        chrono.             format.             temporal.           
        zone.               
      </code> 
  
  11. Java Documentation Lookup
  JShell provides lookup of function format and documentation within the shell. 
  <code>
  jshell> String k="Hello World";
  k ==> "Hello World"  
  jshell> k.compareTo(
  k   
  Signatures:
  int String.compareTo(String anotherString)  
  <press tab again to see documentation>
  jshell> k.compareTo(
  int String.compareTo(String anotherString)
  <no documentation found>
  </code>
  
  12. Edit Pad  
  For longer code blocks, it is difficult if we want to edit it and re-run. JShell provides an editor for editing previously executed commands.
  Use /list command to see the statements/code blocks you have created. Access EditPad with the command /edit <statement line number>  
  <code>jshell> /list        
           1 : int i=10;  
           2 : int add(){  
                 return i+j;   
               }  
        jshell> /edit 2  
        |  modified method add()  
        jshell> class Person{  
           ...> String name;  
           ...> int age;  
           ...> }  
        |  created class Person  
        jshell> /edit Person
  </code>
  
  13. Saving commands  
  JShell gives the option to save the commands to a file. This can be retrieved later so that the previous state can be retained if you are working in a new session.  
  <code>jshell> /save myCommands.jsh</code>  
  <code>jshell> /open myCommands.jsh</code>
  
  14. Startup Script  
  JShell gives you the option to add a startup script. So that every time reset is done or new instance is started. This startup file will be run.  
  <code>jshell> int i=10;  
        i ==> 10 </code>   
  <code>jshell> /save startup.jsh  
        jshell> /set start startup.jsh -retain DEFAULT  
        jshell> /reset  
        |  Resetting state.  
        jshell> i  
        i ==> 10
</code>  
  # References
  1. Most of the notes here are from the Java Brains course [https://javabrains.io/courses/java_jshellbasics/]
  
