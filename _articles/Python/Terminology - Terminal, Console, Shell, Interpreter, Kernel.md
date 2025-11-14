---
title: "Terminology: Terminal, Console, Shell, Interpreter, Kernel"
layout: article
date: 2025-11-13
---

This terminology confuses me each time I think about it. So let's talk about it now. And because these terms have a lot of people talking about them online - on Reddit, StackOverflow, Wikipedia, computer science formus, blogs etc. - mostly with different claims about them, I'm using ChatGPT to try to get some general definitions. I feel OK with that, because this is exactly what LLMs should be doing well.

(Disclaimer: This post is mostly based on GPT-5 responses. All sentences in citation marks are either direct citations or paraphrases of ChatGPT, unless other source is mentioned.)

# Terminal / Console

"The two terms overlap historically and conceptually." There are some subtle differences, but I'm not sure ChatGPT explains them correctly. The distinctions I was able to get:
1) Historically, "console was local to the system, for the operator" and "terminal was remote, for users connecting over communication lines".
2) Today, "Console = low-level text I/O interface provided by the system itself", "Terminal = user-space application that simulates a console or terminal device."
3) "Terminal is a tool, while a console is the interface to the OS/system."

"Historically, 'terminal' meant a physical device — a keyboard and screen connected to a mainframe.
Today it's software (an emulator) that lets you type and see command-line output." "It is a general-purpose text interface to your operating system."

"Examples: Windows Command Prompt, Linux GNOME Terminal, macOS Terminal.app."

"Developers often call the output area of an IDE (like the Python console in PyCharm) a 'console' — it's a program-specific interface for running code."

**Summary**: So I think it is safe to ignore those (mostly historical) differences and treat them as basically the same thing. But if I had to make a distinction, it would be this: If you are talking about interacting with an OS, the convention is to call it a "terminal". But if you are interacting with anything else, like Python, or IPython, the convention is to call it a "console".

# Shell
"A shell is the program that actually interprets the text commands you type into the terminal."

"Examples: bash, zsh, cmd.exe or PowerShell."

**Summary**: I think of a shell as a program that actually runs inside a terminal or a console.

# Python Console / Python Shell
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

"This is the interactive mode of Python that you get when you type python in your terminal. Lets you execute Python commands line by line."

"Also called "Interactive interpreter", "REPL" (Read-Eval-Print Loop)."

"It runs inside the terminal, but once launched, you're no longer giving OS commands — you're interacting directly with the Python interpreter."

**Summary**: So again, I think it is safe for me to treat them as basically the same thing. But if anything, I guess it should be analogous to the relationship between "console" (or terminal) and "shell". Meaning "Python console" is any console that runs a "Python shell", and "Python shell" is the program that actually connects my prompts to the Python interpreter.

# IPython Console
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
"IPython (Interactive Python) is a command shell for interactive computing in multiple programming languages, originally developed for the Python programming language, that offers introspection, rich media, shell syntax, tab completion, and history."

**Summary**: I would again say that the actual thing is the shell, and a console is any window that presents that shell. And IPython shell differs from the standard Python shell in features like magic commands.

Note: I think that the terms "Python console" or "IPython console" are actually nonsensical in a way. They are just a console. Whatever shell is run in it is not the console's business. So I think it is clearer when we say "a console that runs an IPython shell" instead of "an IPython console".

# Python Interpreter
"The core engine (usually python.exe, python3, or similar) that actually executes Python code."

- "Reads your code (from file or input)
- Compiles it to bytecode
- Executes that bytecode on the Python Virtual Machine (PVM)"

From GeeksForGeeks:

"A Python Interpreter is the program that reads and executes Python code. It translates your Python instructions into machine-readable form line by line, so the computer can understand and run them.

When you run a Python program, code passes through Python Interpreter, which is responsible for:
- Checking your code for errors.
- Converting it into an intermediate form called bytecode.
- Sending it to the Python Virtual Machine (PVM) for execution."

**Summary**: This is the most obvious term to me. It is simply the program that actually executes python commands.

# Kernel
"A separate process that runs and executes code sent from an interface like Jupyter Notebook or Spyder."

"The 'IPython kernel' is the engine behind Jupyter Notebooks — it's essentially IPython running in the background, communicating via messages (using ZeroMQ)."

From https://docs.jupyter.org/en/latest/projects/kernels.html:

- "Kernels are programming language specific processes that run independently and interact with the Jupyter Applications and their user interfaces. ipykernel is the reference Jupyter kernel built on top of IPython, providing a powerful environment for interactive computing in Python.
- ipykernel is the wrapper around IPython which enables using IPython as a kernel."

**Summary**: So I'd say that first, a kernel is a term used in Jupyter Notebooks. And second, it is a process that runs an independent (and Jupyter-adjusted) copy of an IPython shell.
