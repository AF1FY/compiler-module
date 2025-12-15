Java Compiler Front-End (JavaCC)

A simple Compiler Front-End for the Java programming language built using JavaCC. This project implements the Lexical Analysis and Syntax Analysis (Parsing) phases.

🚀 Features

Lexical Analysis:

Tokenizes Java source code.

Identifies Keywords, Identifiers, Operators, and Literals.

Generates a categorized Symbol Table.

Ignores comments (// and /* */) and whitespace.

Syntax Analysis (Parsing):

Validates the code structure against Java Grammar rules.

Supports: Class Declarations, Main Method, Control Structures (if/else, while), Variable Declarations, and Complex Expressions.

Reports syntax errors with line and column numbers.

🛠️ Prerequisites

Java JDK (version 8 or higher).

JavaCC (included as javacc.jar in the root directory).

🏃‍♂️ How to Run

Follow these commands in your terminal to build and run the compiler:

1. Generate the Parser (Phase 1 & 2)

Use JavaCC to generate the Java source files from the grammar file (.jj).

java -cp javacc.jar javacc JavaCompiler.jj


2. Compile the Java Files

Compile the generated Java files and the main program.

javac *.java


3. Run the Compiler

Run the compiler by providing a text file containing Java code (e.g., input.txt).

java JavaCompiler input.txt


📂 Project Structure

JavaCompiler.jj: The main grammar file containing Token definitions and BNF rules.

input.txt: Sample Java code to test the compiler.

javacc.jar: The JavaCC tool used to generate the parser.

📝 Example Output

Input (input.txt):

class Test {
    public static void main(String[] args) {
        int x = 10;
        if (x > 5) {
            x = x + 1;
        }
    }
}


Console Output:

--- Symbol Table ---
Keyword              (class)
Identifier           (Test)
Special Character    ({)
...
--------------------

--- Syntax Validation ---
✅ Syntax validation successful. Code is valid Java.


🤝 Team Tasks (Next Steps)

Current Status: Phase 1 (Lexer) and Phase 2 (Parser Grammar) are completed.

Next Phase: Phase 3 (AST Construction).

Create AST Node classes.

Inject Java code into JavaCompiler.jj to build the tree nodes.

Implement a Visitor pattern or print method to visualize the tree.