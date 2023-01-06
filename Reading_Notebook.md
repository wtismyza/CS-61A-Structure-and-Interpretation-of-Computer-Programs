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
  
Practical Guidance. When indenting a suite, all lines must be indented the same amount and in the same way (use spaces, not tabs). Any variation in indentation will cause an error.
  
Python includes several false values, including 0, None, and the boolean value False. All other numbers are true values.
  
A while statement that does not terminate is called an infinite loop. Press <Control>-C to force Python to stop looping.
  
When writing Python in files, all doctests in a file can be run by starting Python with the doctest command line option:

python3 -m doctest <python_source_file>
  
The key to effective testing is to write (and run) tests immediately after implementing new functions. It is even good practice to write some tests before you implement, in order to have some example inputs and outputs in your mind. A test that applies a single function is called a unit test. Exhaustive unit testing is a hallmark of good program design.

two key advantages of lexical scoping in Python.

The names of a local function do not interfere with names external to the function in which it is defined, because the local function name will be bound in the current local environment in which it was defined, rather than the global environment.
A local function can access the environment of the enclosing function, because the body of the local function is evaluated in an environment that extends the evaluation environment in which it was defined.

  **Partition trees** Recursive Construction
  **count_leaves(tree):**
  **nonlocal statement**


  
Python also has an unusual restriction regarding the lookup of names: within the body of a function, all instances of a name must refer to the same frame. As a result, Python cannot look up the value of a name in a non-local frame, then bind that same name in the local frame, because the same name would be accessed in two different frames in the same function. This restriction allows Python to pre-compute which frame contains each name before executing the body of a function. When this restriction is violated, a confusing error message results. To demonstrate, the make_withdraw example is repeated below with the nonlocal statement removed.
  
This UnboundLocalError appears because balance is assigned locally in line 5, and so Python assumes that all references to balance must appear in the local frame as well. This error occurs before line 5 is ever executed, implying that Python has considered line 5 in some way before executing line 3. As we study interpreter design, we will see that pre-computing facts about a function body before executing it is quite common. In this case, Python's pre-processing restricted the frame in which balance could appear, and thus prevented the name from being found. Adding a nonlocal statement corrects this error. The nonlocal statement did not exist in Python 2.

  **Propagating Constraints**

Naming Conventions. Class names are conventionally written using the CapWords convention (also called CamelCase because the capital letters in the middle of a name look like humps). Method names follow the standard convention of naming functions using lowercased words separated by underscores.

In some cases, there are instance variables and methods that are related to the maintenance and consistency of an object that we don't want users of the object to see or use. They are not part of the abstraction defined by a class, but instead part of the implementation. Python's convention dictates that if an attribute name starts with an underscore, it should only be accessed within methods of the class itself, rather than by users of the class.
  
Python has a simple feature for computing attributes on the fly from zero-argument functions. The @property decorator allows functions to be called without call expression syntax (parentheses following an expression). The ComplexRI class stores real and imag attributes and computes magnitude and angle on demand.
  
```
        def __repr__(self):
            return 'ComplexMA({0:g}, {1:g} * pi)'.format(self.magnitude, self.angle/pi)
```
  
**Memoization**
Q: How do you prevent the ok autograder from interpreting print statements as output?
Choose the number of the correct choice:
0) You don't need to do anything, ok only looks at returned values, not printed values
1) Print with # at the front of the outputted line
2) Print with 'DEBUG:' at the front of the outputted line  
  
lab01:
  python3 ok -q debugging-quiz -u
  
(lambda: 3)()
 
 ```
 def cycle(f1, f2, f3):
    """Returns a function that is itself a higher-order function.
    >>> def add1(x):
    ...     return x + 1
    >>> def times2(x):
    ...     return x * 2
    >>> def add3(x):
    ...     return x + 3
    >>> my_cycle = cycle(add1, times2, add3)
    >>> identity = my_cycle(0)
    >>> identity(5)
    5
    >>> add_one_then_double = my_cycle(2)
    >>> add_one_then_double(1)
    4
    >>> do_all_functions = my_cycle(3)
    >>> do_all_functions(2)
    9
    >>> do_more_than_a_cycle = my_cycle(4)
    >>> do_more_than_a_cycle(2)
    10
    >>> do_two_cycles = my_cycle(6)
    >>> do_two_cycles(1)
    19
    """
    def cycle_through(n):
        funs = [f1, f2, f3]

        def final_cycle(x):
            count = 0

            while count < n:
                x = funs[count % 3](x)
                count += 1

            return x

        return final_cycle
    
    return cycle_through
```  
```
def make_repeater(f, n):
    """Return the function that computes the nth application of f.
    >>> add_three = make_repeater(increment, 3)
    >>> add_three(5)
    8
    >>> make_repeater(triple, 5)(1) # 3 * 3 * 3 * 3 * 3 * 1
    243
    >>> make_repeater(square, 2)(5) # square(square(5))
    625
    >>> make_repeater(square, 4)(5) # square(square(square(square(5))))
    152587890625
    >>> make_repeater(square, 0)(5)
    5
    """
    "*** YOUR CODE HERE ***"
    return accumulate(compose1, lambda x: x, n, lambda x: f)

# Alternatives

    def calculator(x):
        if n == 0:
            return x
        else:
            return f(make_repeater(f, n - 1)(x))
    return calculator





def compose1(f, g):
    """Return a function h, such that h(x) = f(g(x))."""
    def h(x):
        return f(g(x))
    return h                            
```
```
Solution
def div_by_primes_under(n):
    """
    >>> div_by_primes_under(10)(11)
    False
    >>> div_by_primes_under(10)(121)
    False
    >>> div_by_primes_under(10)(12)
    True
    >>> div_by_primes_under(5)(1)
    False
    """
    checker = lambda x: False
    i = 2
    while i <= n:
        if not checker(i):
            checker = (lambda f, i: lambda x: x % i == 0 or f(x))(checker, i)
        i = i + 1
    return checker

def div_by_primes_under_no_lambda(n):
    """
    >>> div_by_primes_under_no_lambda(10)(11)
    False
    >>> div_by_primes_under_no_lambda(10)(121)
    False
    >>> div_by_primes_under_no_lambda(10)(12)
    True
    >>> div_by_primes_under_no_lambda(5)(1)
    False
    """
    def checker(x):
        return False
    i = 2
    while i <= n:
        if not checker(i):
            def outer(f, i):
                def inner(x):
                    return x % i == 0 or f(x)
                return inner
            checker = outer(checker, i)
        i = i + 1
    return checker                           
```                           
                            
                            
                            
