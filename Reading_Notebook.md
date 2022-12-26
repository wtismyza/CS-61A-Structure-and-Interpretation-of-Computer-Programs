**Interactive Sessions**

Interactive controls. Each session keeps a history of what you have typed. To access that history, press <Control>-P (previous) and <Control>-N (next). <Control>-D exits a session, which discards this history. Up and down arrows also cycle through history on some systems.
  
Statements & Expressions. Python code consists of expressions and statements. Broadly, computer programs consist of instructions to either

Compute some value
Carry out some action
  
Functions. Functions encapsulate logic that manipulates data.
  
Objects. An object seamlessly bundles together data and the logic that manipulates that data, in a way that manages the complexity of both. 

Interpreters. Evaluating compound expressions requires a precise procedure that interprets code in a predictable way. A program that implements such a procedure, evaluating compound expressions, is called an interpreter. 

Learning to interpret errors and diagnose the cause of unexpected errors is called debugging. Some guiding principles of debugging are:

Test incrementally: Every well-written program is composed of small, modular components that can be tested individually. Try out everything you write as soon as possible to identify problems early and gain confidence in your components.
Isolate errors: An error in the output of a statement can typically be attributed to a particular modular component. When trying to diagnose a problem, trace the error to the smallest fragment of code you can before trying to correct it.
Check your assumptions: Interpreters do carry out your instructions to the letter — no more and no less. Their output is unexpected when the behavior of some code does not match what the programmer believes (or assumes) that behavior to be. Know your assumptions, then focus your debugging effort on verifying that your assumptions actually hold.
Consult others: You are not alone! If you don't understand an error message, ask a friend, instructor, or search engine. If you have isolated an error, but can't figure out how to correct it, ask someone else to take a look. A lot of valuable programming knowledge is shared in the process of group problem solving.
Incremental testing, modular design, precise assumptions, and teamwork are themes that persist throughout this text. Hopefully, they will also persist throughout your computer science career.
  
When we describe a language, we should pay particular attention to the means that the language provides for combining simple ideas to form more complex ideas. Every powerful language has three such mechanisms:

primitive expressions and statements, which represent the simplest building blocks that the language provides,
means of combination, by which compound elements are built from simpler ones, and
means of abstraction, by which compound elements can be named and manipulated as units.
  
Expressions, Call Expressions, Importing Library Functions, Names and the Environment, 
  
  
Function notation has three principal advantages over the mathematical convention of infix notation. 
  
First, functions may take an arbitrary number of arguments:
Second, function notation extends in a straightforward way to nested expressions, where the elements are themselves compound expressions. In nested call expressions, unlike compound infix expressions, the structure of the nesting is entirely explicit in the parentheses.
Third, mathematical notation has a great variety of forms: multiplication appears between terms, exponents appear as superscripts, division as a horizontal bar, and a square root as a roof with slanted siding. Some of this notation is very hard to type! However, all of this complexity can be unified via the notation of call expressions. While Python supports common mathematical operators using infix notation (like + and -), any operator can be expressed as a function with a name.
  

