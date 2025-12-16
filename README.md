How to run
```Bash
del *.java *.class JavaCompiler.jj
java -cp javacc.jar jjtree JavaCompiler.jjt
java -cp javacc.jar javacc JavaCompiler.jj
javac *.java
java JavaCompiler input.txt
```
