Java Compiler Front-End (JavaCC & JJTree)A robust Compiler Front-End for the Java programming language built using JavaCC and JJTree. This project implements the full pipeline: Lexical Analysis, Syntax Parsing, Abstract Syntax Tree (AST) Construction, and Semantic Analysis.🚀 Features1. Phase 1: Lexical AnalysisTokenization: Breaks down source code into Tokens (Keywords, Identifiers, Operators, Literals).Symbol Table: Generates a detailed list of all tokens found in the source code.Cleaning: Automatically ignores comments (//, /* */) and whitespace.2. Phase 2: Syntax Analysis (Parser)Grammar Validation: Validates code against Java grammar rules.Structure Support: Handles Class declarations, Main method, Blocks, and Statements.Control Flow: Supports if-else, while, and for loops.Error Reporting: Detects syntax errors and reports the exact line and column.3. Phase 3: AST Construction (JJTree)Tree Building: Uses JJTree to automatically build the Abstract Syntax Tree.Pretty Printing: Features a Custom Tree Visitor that visualizes the AST in a hierarchical, easy-to-read format (e.g., └── TypeDeclaration).4. Semantic Analysis (Bonus) ✨Scope Resolution: Tracks variables across different scopes (Global vs Local).Undeclared Variables: Detects usage of variables that haven't been declared.Unused Variables: Warns about variables that are declared but never used.Duplicate Declaration: Prevents declaring the same variable twice in the same scope.🛠️ PrerequisitesJava JDK (Version 8 or higher).javacc.jar (Included in the project root).🏃‍♂️ How to Run (Step-by-Step)Since this project uses JJTree for AST generation, the build process involves an extra step.Windows (CMD / PowerShell)Clean old files (Important to avoid conflicts):del *.java *.class JavaCompiler.jj
Generate the Tree (JJTree):java -cp javacc.jar jjtree JavaCompiler.jjt
Generate the Parser (JavaCC):java -cp javacc.jar javacc JavaCompiler.jj
Compile Java Files:javac *.java
Run the Compiler:java JavaCompiler input.txt
Linux / Mac Terminalrm *.java *.class JavaCompiler.jj      # Clean
java -cp javacc.jar jjtree JavaCompiler.jjt # Build Tree
java -cp javacc.jar javacc JavaCompiler.jj  # Build Parser
javac *.java                           # Compile
java JavaCompiler input.txt            # Run
📂 Project StructureJavaCompiler.jjt: The main source file containing Grammar, Tokens, and AST logic.input.txt: Test file containing Java code to be compiled.javacc.jar: The tool used to generate the compiler.README.md: This documentation.📝 Example OutputInput Code:int x = 10;
if (x > 5) { ... }
Console Output:--- Symbol Table (Tokens) ---
Keyword (int)
Identifier (x)
Operator (=)
Numeric Constant (10)
...

--- Syntax & AST Check ---
✅ Syntax Validation Successful.

--- Abstract Syntax Tree (AST) ---
└── CompilationUnit 
    └── TypeDeclaration (name: TestCompiler, modifier: public)
        └── MethodDeclaration (name: main)
            └── Block 
                ├── VariableDeclarationStatement (type: int, name: x)
                ├── IfStatement
                │   ├── InfixExpression (operator: >)
                │   └── Block
                └── ReturnStatement
👥 Contributors[Your Name]: Lexical Analysis & Parser Grammar.[Teammate Name]: AST Construction & Logic.[Teammate Name]: Semantic Analysis & Testing.