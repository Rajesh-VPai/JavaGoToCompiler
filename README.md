# JavaGoToCompiler
JavaGoToCompiler is a JavaCC program that parsers goto for Java
GoTo Compiler is an parser where Dataflow/ControlFlow techniques are used to parse goto in Java Code. It specifically flags off infinite loops in the usage of goto. It is meant as a demonstration that the theoretical “Spaghetti Code” (refer wiki Spaghetti Code) does not exist for the computer if the code runs at least 1 time.For more details on Dataflow  and Control Flow refer Wiki Dataflow, wiki Controlflow.
#Packages
GoTo Compiler constists of 1 package:
    1) JavaCC

# RUNNING THE PROGRAMS
    1) TestFile:Java with GoTo:Basic0Pass.jj
    2) Working Commands
    3) Command Directory :C:\Rajesh_Docus\Projects\GoToCompiler\newtest1
    4) Order of Commands is important:
    5) State: Files :-    SimpleNode.java, Token.java     SHOULD EXIST
    6) FileToTest: Basic1Pass.jj
    7) Windows PATH Variable: C:\Program Files\Java\jdk1.8.0_112\bin;
    8) JAVA CLASSPATH: C:\Program Files\Java\jdk1.8.0_112\javacc-6.0\javacc-6.0\bin\lib\javacc.jar;
    9) JAVACC VERSION:6.0_1
    10) 1) jjtree JavaParser.jjt
    11) 2) javacc JavaParser.jj
    12) 3) Paste SimpleNode.java, Token.java,
    13) 4) javac *.java
    14) 
    15) 5) java JavaParser Basic0Pass.jj Basic0Pass.java1
    16) OR
    17) 5) java JavaParser Basic0Pass.java Basic0Pass.java1
    18) 
    19) 6) Delete all files EXCEPT : JavaParser.jjt , Basic0Pass.jj, log4j.properties  & STATE FILES
    20) 7)GoTo 1
OR 
    1) TestFile:Java with GoTo:Basic1Pass.jj
    2) Working Commands
    3) Command Directory :C:\Rajesh_Docus\Projects\GoToCompiler\newtest1
    4) Order of Commands is important:
    5) State: Files :-   SimpleNode.java, , Token.java      SHOULD EXIST
    6) FileToTest: Basic1Pass.jj
    7) Windows PATH Variable: C:\Program Files\Java\jdk1.8.0_112\bin;
    8) JAVA CLASSPATH: C:\Program Files\Java\jdk1.8.0_112\javacc-6.0\javacc-6.0\bin\lib\javacc.jar;
    9) JAVACC VERSION:6.0_1
    10) 1) jjtree JavaParser.jjt
    11) 2) javacc JavaParser.jj
    12) 3) Paste  SimpleNode.java, Token.java,
    13) 4) javac *.java
    14) 
    15) 5) java JavaParser Basic1Pass.jj Basic1Pass.java1
    16) OR
    17) 5) java JavaParser Basic1Pass.java Basic1Pass.java1
    18) 
    19) 6) Delete all files EXCEPT : JavaParser.jjt , Basic1Pass.jj, log4j.properties  & STATE FILES
    20) 7)GoTo 1

# GoTo Compiler Theory:
	Note to Reader: I have delibrately not assigned Label2 & Label3 which can be above the code segment discussed, below or inbetwee or any permutation. This is left to the Reader to analyse for himself/herself. The Theory discussed below (if understood very well) covers all the permutations. Hence a simple lemma is chosen.

	The core of the parsing is based on the below segment of code:
			Label0: go to Label5
             	
Label1: If(condition1) then{
					Goto Label2
  }
LabelERR1: Elseif (condition2) then {
	Goto Label3
  }
LabelERR2: Else {
       Goto Next_line.
	}
                  Next_line: x=x+1
                  

Even the above “seemingly nonsensical code” follows the basic Dataflow/ControlFlow rules/techniques/grammar (other than Java grammar or C grammar).
