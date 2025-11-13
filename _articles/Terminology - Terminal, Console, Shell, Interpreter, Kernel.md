---
title: "Terminology: Terminal, Console, Shell, Interpreter, Kernel"
layout: article
---

This terminology confuses me each time I think about it. So let's talk about it. And because these terms have a lot of people talking about them online - on Reddit, StackOverflow, Wikipedia, computer science formus and blogs etc. - mostly with different claims about them, I'm using ChatGPT to try to get some general definitions. I feel OK with that, because this is exactly what it should be doing well.

(Disclaimer: This post is mostly based on GPT-5 responses. All sentences in citation marks are either direct citations or paraphrasions of ChatGPT.)

## Terminal / Console

"The two terms overlap historically and conceptually." There are some subtle differences, but I'm not sure ChatGPT explains them correctly. The distinctions I was able to get:
1) Historically, "console was local to the system, for the operator" and "terminal was remote, for users connecting over communication lines".
2) Today, "Console = low-level text I/O interface provided by the system itself", "Terminal = user-space application that simulates a console or terminal device."
3) "Terminal is a tool, while a console is the interface to the OS/system."

I think it is safe to ignore those differences and treat them as the same thing. But after writing this post, I'm thinking that todays convention is this: If you are talking about interacting with OS, you call it a "terminal". But if you are interacting with anything else, like Python, or IPython, you call it a "console".

"Historically, 'terminal' meant a physical device — a keyboard and screen connected to a mainframe.
Today it's software (an emulator) that lets you type and see command-line output." "It is a general-purpose text interface to your operating system."

"Examples: Windows Command Prompt, Linux GNOME Terminal, macOS Terminal.app."

"Developers often call the output area of an IDE (like the Python console in PyCharm) a 'console' — it's a program-specific interface for running code."

## Shell
"A shell is the program that actually interprets the text commands you type into the terminal."

"Examples: bash, zsh, cmd.exe or PowerShell."

## Python Console / Python Shell
"In most contexts, Python console ≈ Python shell"

```
(bash)
$ python
Python 3.12.1 (main, ...) 
>>> print("hi")
hi
>>>
```

"That environment (the >>> prompt) is both:
- called the Python shell in the Python documentation, and
- often called a Python console by IDEs or textbooks."

"In normal usage: Python console = Python shell.
In technical terms:
- The shell is the interactive REPL interface to the Python interpreter.
- The console is any program or UI that hosts or presents that shell to you."

So, again, I think it is safe for me to treat them as the same thing. But I guess if anything, it should be analogous to the relationship between "console" (terminal) and "shell".

"This is the interactive mode of Python that you get when you type python in your terminal. Lets you execute Python commands line by line."

"Also called "Interactive interpreter", "REPL" (Read-Eval-Print Loop)."

"It runs inside the terminal, but once launched, you're no longer giving OS commands — you're interacting directly with the Python interpreter."

## IPython Console
```
In [1]: 
```
"A smarter interactive shell built on top of the Python interpreter."

"Enhancements over the basic Python shell:

- Syntax highlighting
- Auto-completion
- Magic commands (%time, %run, etc.)
- Better tracebacks and object inspection"
- Inline plots (especially in Jupyter)
- Shell-like commands (!ls, !git status)

"It uses the same underlying Python interpreter, but provides a richer user interface and features for interactive use (especially in data science)."

Wikipedia:

IPython (Interactive Python) is a command shell for interactive computing in multiple programming languages, originally developed for the Python programming language, that offers introspection, rich media, shell syntax, tab completion, and history.

(Again, I would say that the actual thing is the shell, and a console is any window that presents that shell.)

Note: I think it is safe to say than "Python console" is any console that runs a Python shell. Similary, an IPython console is any console running an IPython shell. Actually, the terms "Python console" or "IPython console" are nonsensical in a way. They are just a console. Whatever shell is run in it is not the console's business. So I think it is clearer when we say "a console that runs an IPython shell" instead of "an IPython console".

## Python Interpreter
"The core engine (usually python.exe, python3, or similar) that actually executes Python code."

- "Reads your code (from file or input)
- Compiles it to bytecode
- Executes that bytecode on the Python Virtual Machine (PVM)"

From GeeksForGeeks:

A Python Interpreter is the program that reads and executes Python code. It translates your Python instructions into machine-readable form line by line, so the computer can understand and run them.

When you run a Python program, code passes through Python Interpreter, which is responsible for:
- Checking your code for errors.
- Converting it into an intermediate form called bytecode.
- Sending it to the Python Virtual Machine (PVM) for execution.

## Kernel
"A separate process that runs and executes code sent from an interface like Jupyter Notebook or Spyder."

"The 'IPython kernel' is the engine behind Jupyter Notebooks — it's essentially IPython running in the background, communicating via messages (using ZeroMQ)."

From https://docs.jupyter.org/en/latest/projects/kernels.html:

- Kernels are programming language specific processes that run independently and interact with the Jupyter Applications and their user interfaces. ipykernel is the reference Jupyter kernel built on top of IPython, providing a powerful environment for interactive computing in Python.
- ipykernel is the wrapper around IPython which enables using IPython as a kernel.

So I'd say that kernel is a process that runs an independent (and Jupyter-adjusted) copy of an IPython shell.