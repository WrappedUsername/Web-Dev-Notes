# My notes from learning TypeScript 🚧 Work In Progress 🏗

## 🤖 ChatGPT reply

TypeScript is a typed superset of JavaScript that compiles to plain JavaScript. 

When you write code in TypeScript, you are essentially writing in a version of JavaScript with a few extra features that allow you to add type annotations to your code. When you compile your TypeScript code, the compiler converts your TypeScript code into plain JavaScript code that can be run in a web browser or on a server using Node.js.

The process of compiling TypeScript code involves a few steps:

The TypeScript compiler reads your TypeScript code and checks for any syntax errors or type annotations that it doesn't understand. If it finds any issues, it will report them to you.

If the TypeScript code is free of syntax errors and type annotations that the compiler doesn't understand, it will begin the process of type checking. This involves checking that all variables are used correctly and that all function calls are made with the correct number and types of arguments.

If the TypeScript code passes the type checking phase, the compiler will generate the corresponding JavaScript code. This JavaScript code will be equivalent to the TypeScript code, but without any of the type annotations or other TypeScript-specific syntax.

Finally, the compiler will output the generated JavaScript code to a file or write it to the console, depending on how you have configured the compiler.

Overall, the process of compiling TypeScript code involves checking the code for syntax and type errors, and then generating the corresponding JavaScript code. This allows you to write code with the added benefits of type checking and other features provided by TypeScript, while still being able to run your code in a web browser or on a server using Node.js.

## The OSI model and TypeScript

The OSI (Open Systems Interconnection) model is a framework for understanding how communication takes place between different computer systems. It divides the process of communication into seven layers, each of which represents a different aspect of communication and has a specific set of responsibilities. The OSI model is often used as a reference model to help understand how different protocols and technologies fit into the overall process of communication.

TypeScript, JavaScript, Node.js, and bytecode are all technologies that are used at different layers of the OSI model. Here's a brief overview of how they fit into the model:

TypeScript and JavaScript are both programming languages that are used to write code that runs in a web browser. These languages are used at the Application layer (layer 7) of the OSI model, which is the highest layer and is responsible for providing services to the user.

Node.js is a runtime environment that allows you to run JavaScript code on a server or on a command line interface. Node.js is used at the Application layer (layer 7) of the OSI model, just like TypeScript and JavaScript.

Bytecode is a low-level representation of a program that has been compiled from a high-level programming language. It is often used as an intermediate representation of a program that can be run on different types of hardware or in different environments. Bytecode is typically used at the Presentation layer (layer 6) of the OSI model, which is responsible for translating data between different systems and ensuring that it is properly formatted.

Overall, TypeScript, JavaScript, and Node.js are used at the highest layer of the OSI model, while bytecode is used at a slightly lower layer. These technologies are all used to facilitate communication and enable different systems to work together and exchange data.
