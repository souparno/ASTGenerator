# ASTGenerator
Sample Java AST built using ANTLR v4

## Prerequisites
* [git](https://git-scm.com/) (optional)
* [Java](http://openjdk.java.net/install/index.html)
* [Gradle](https://gradle.org/install/)

## Build & Run
Once you got java and gradle installed and running
Clone this repository:
```
$ git clone git@github.com:satnam-sandhu/ASTGenerator.git
```
Build and run the ASTGenerator at once:
```
$ gradle runJar
```

or you can run it manually:

```
$ java -jar build/libs/ASTGenerator.jar
```
File `Blabla.java` present in resource directory's AST will be printed in the format of a DOT file:

```
digraph G {
00[label="compilationUnit\n classfibonacci{publicstaticvoidmain(){inta=0;intb;b=1+10;}}<EOF> "]
11[label="normalClassDeclaration\n classfibonacci{publicstaticvoidmain(){inta=0;intb;b=1+10;}} "]
22[label="classBody\n {publicstaticvoidmain(){inta=0;intb;b=1+10;}} "]
33[label="methodDeclaration\n publicstaticvoidmain(){inta=0;intb;b=1+10;} "]
44[label="methodModifier\n public "]
45[label="methodModifier\n static "]
46[label="methodHeader\n voidmain() "]
57[label="result\n void "]
58[label="methodDeclarator\n main() "]
49[label="block\n {inta=0;intb;b=1+10;} "]
510[label="blockStatements\n inta=0;intb;b=1+10; "]
611[label="localVariableDeclarationStatement\n inta=0; "]
712[label="localVariableDeclaration\n inta=0 "]
813[label="integralType\n int "]
814[label="variableDeclarator\n a=0 "]
915[label="variableDeclaratorId\n a "]
916[label="literal\n 0 "]
617[label="localVariableDeclarationStatement\n intb; "]
718[label="localVariableDeclaration\n intb "]
819[label="integralType\n int "]
820[label="variableDeclaratorId\n b "]
621[label="expressionStatement\n b=1+10; "]
722[label="assignment\n b=1+10 "]
823[label="expressionName\n b "]
824[label="assignmentOperator\n = "]
825[label="additiveExpression\n 1+10 "]
926[label="literal\n 1 "]
927[label="literal\n 10 "]
00->11
11->22
22->33
33->44
33->45
33->46
46->57
46->58
33->49
49->510
510->611
611->712
712->813
712->814
814->915
814->916
510->617
617->718
718->819
718->820
510->621
621->722
722->823
722->824
722->825
825->926
825->927
}
```

Use http://viz-js.com/ to visualize the generated DOT file.
![](https://i.imgur.com/ZFt3Cqn.png)

You can pipe the output in a file by
```
$ gradle clean build
```
```
$ java -jar build/libs/ASTGenerator.jar > ast.dot
```

Change the content of `Blabla.java`  to generate your own AST.


## Grammar

The original grammar has been obtained from:

https://github.com/antlr/grammars-v4/tree/master/java8

It is available under the MIT License

## Help

This project was completed only after I refferd to this [repository](https://github.com/ftomassetti/python-ast) by [Federico Tomassetti](https://github.com/ftomassetti)
