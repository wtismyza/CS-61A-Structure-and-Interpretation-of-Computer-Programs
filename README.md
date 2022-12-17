# CS-61A-Structure-and-Interpretation-of-Computer-Programs

Some Python example:

```

# Numeric expressions
2022
2000 + 22
1 + 2 + 3 + 4 * ((5 // 6) + 7 * 8 * 9)

# Functions
abs(-2)

# Values
"Go Bears"

# Objects
# Note: Download from http://composingprograms.com/shakespeare.txt
shakes = open('shakespeare.txt')
text = shakes.read().split()
len(text)
text[:25]
text.count('the')
text.count('thou')
text.count('you')
text.count('forsooth')
text.count(',')

# Sets
words = set(text)
len(words)

# Combinations 
'draw'
'draw'[0]
{w[0] for w in words}

# Data
'draw'[::-1]
{w for w in words if w == w[::-1] and len(w)>4}
{w for w in words if w[::-1] in words and len(w) == 4}
{w for w in words if w[::-1] in words and len(w) > 6}

```

The lines in the triple-quotes `"""` are called a docstring, which is a description of what the function is supposed to do. 

The lines that begin with `>>>` are called doctests. Recall that when using the Python interpreter, you write Python expressions next to `>>>` and the output is printed below that line. Doctests explain what the function does by showing actual Python code. It answers the question: "If we input this Python code, what should the expected output be?"

**Appendix: Useful Python command line options**
When running a Python file, you can use options on the command line to inspect your code further. Here are a few that will come in handy. If you want to learn more about other Python command-line options, take a look at the documentation.

Using no command-line options will run the code in the file you provide and return you to the command line. For example, if we want to run lab00.py this way, we would write in the terminal:

`python3 lab00.py`
`-i`: The `-i` option runs your Python script, then opens an interactive session. In an interactive session, you run Python code line by line and get immediate feedback instead of running an entire file all at once. To exit, type `exit()` into the interpreter prompt. You can also use the keyboard shortcut `Ctrl-D` on Linux/Mac machines or `Ctrl-Z` Enter on Windows.

If you edit the Python file while running it interactively, you will need to exit and restart the interpreter in order for those changes to take effect.

Here's how we can run lab00.py interactively:

`python3 -i lab00.py`
`-m doctest`: Runs doctests in a particular file. Doctests are surrounded by triple quotes (`"""`) within functions.

Each test in the file consists of `>>>` followed by some Python code and the expected output (though the `>>>` are not seen in the output of the doctest command).

To run doctests for `lab00.py`, we can run:

 `python3 -m doctest lab00.py`
