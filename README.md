#JShell
##Introduction
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

##Setup
Jshell is supported from Java 9 onwards.
Download from here : https://www.java.com/en/download/
Check the version of java and ensure it is 9 or above:

<code>
$ java -version
</code>

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
 
  #References
  1. Most of the notes here are from the Java Brains course [https://javabrains.io/courses/java_jshellbasics/]
  