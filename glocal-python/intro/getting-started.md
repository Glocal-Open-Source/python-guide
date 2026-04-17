# Getting Started with Python

## Python Fundamentals

Python is an open-source, interpreted language that combines clear, readable syntax with a **“batteries-included”** standard library—everything from HTTP clients to JSON parsers is ready to go out of the box. It supports multiple paradigms (procedural, object-oriented, functional), automatic memory management, and an enormous ecosystem of third-party packages. That makes Python both easy to learn and incredibly powerful for tasks like web scraping, data analysis, automation, and more.

## Installing Python & Getting Started

### Download & Install

**Windows / macOS**:
Grab the latest installer from [python.org/downloads/](https://python.org/downloads/) and follow the prompts. 

```{warning}
**Critical Step for Windows:** Make sure to check the box for **"Add to PATH"** when the option comes up during installation!
```

**Linux**:
```bash
# Debian/Ubuntu
sudo apt update && sudo apt install python3 python3-venv python3-pip

# Fedora
sudo dnf install python3 python3-venv python3-pip
```

### Open a Terminal

- **Windows**: Press `Win+R`, type `cmd` or `powershell`, hit Enter.
- **macOS**: Use Spotlight Search (`⌘+Space`) → type “Terminal” → hit Enter.
- **Linux**: Press `Ctrl+Alt+T` or find “Terminal” in your applications menu.

### Verify Installation
In your open terminal, run the following command:
```bash
python3 --version    # should print something like "Python 3.x.y"
```
*(On Windows, you might just need to run `python --version`)*

---

## Pythonic Principles

Python is special because it's a verbose and human-centric language. It was designed with the philosophy that code is read more often than it's written, and it's humans, not machines, who will be reading, writing, and maintaining it.

So, while computers ultimately understand only binary (1s and 0s), Python embraces readability and simplicity, making it closer to natural language than most programming languages.

### What Does It Mean to Write Pythonic Code?
Writing "Pythonic" code means writing code that adheres to the idioms, principles, and style guidelines embraced by the Python community. It's not just about getting the job done, it's about doing it the *Python way*.

**Characteristics of Pythonic Code:**

| Trait | Description |
| :--- | :--- |
| **Readable** | Prioritizes clarity and easy understanding over cleverness or brevity |
| **Concise** | Avoids unnecessary repetition or verbosity |
| **Explicit** | Prefers clear behavior to implicit tricks or surprises |
| **Simple > Complex** | Strives to solve problems in the simplest reasonable way |
| **Elegant** | Uses built-in features and idioms instead of over-engineering solutions |
| **Consistent** | Follows the conventions of PEP 8 |
| **Leverages Library** | Uses "batteries included" modules rather than reinventing the wheel |

### Pythonic vs Unpythonic Loops

```python
# Unpythonic: verbose and manual
squares = []
for i in range(10):
    squares.append(i * i)

# Pythonic: concise and readable (List Comprehension)
squares = [i * i for i in range(10)]
```

```python
names = ["Alice", "Bob", "Charlie"]

# Unpythonic: using index unnecessarily
for i in range(len(names)):
    print(names[i])

# Pythonic: iterate directly
for name in names:
    print(name)
```

### Key Tools That Help You Write Pythonically
- **Comprehensions**: List/Dict/Set comprehensions
- **Context managers**: Example `with open(...) as f:`
- **Unpacking**: Assigning multiple variables `a, b = b, a`
- **Enumerate and zip**: Better alternatives to `range(len(...))`
- **Built-in functions**: `map()`, `filter()`, `sorted()`, `any()`, `all()`, `sum()`

```{tip}
**The Zen of Python (by Tim Peters)**
You can read the core philosophy of Python directly in the Python interpreter by typing:
`>>> import this`
```

---

## Text Editors

Now that you have had some time to play with Python in the command line, it’s worth investing a little time in a dedicated text editor. A good editor gives you syntax highlighting, bracket matching, code snippets, and an integrated terminal or debugger—all of which save you from hunting through lines of plain text to spot errors. Instead of juggling multiple windows and copy-pasting, you can write, test, and refactor your code in one place, making your workflow smoother and less error-prone.

```{note}
**Recommendation for Beginners:** 
I recommend using **Visual Studio Code**. It is slightly bulkier software than simple text editors, but it is simple and intuitive to use. It’s also very easy to install extensions and themes!
```

### Popular Editor Options

| Editor | Key Strengths | Link |
| :--- | :--- | :--- |
| **Visual Studio Code*** | • Integrated terminal & debugger<br>• Rich extension ecosystem<br>• Built-in Git support<br>• Best for beginners | [code.visualstudio.com](https://code.visualstudio.com) |
| **Sublime Text** | • Ultra-lightweight & blazing fast<br>• “Goto Anything” fuzzy finder<br>• Powerful multi-selection editing<br>• Package Control | [sublimetext.com](https://www.sublimetext.com) |
| **Atom** | • Highly hackable (built on Electron)<br>• GitHub integration<br>• Teletype for real-time collaboration | [atom.io](https://atom.io) |
| **Vim** | • Modal, keyboard-driven editing<br>• Very low resource usage<br>• Ubiquitous on Unix systems<br>• Steep learning curve but massive speed gains | [vim.org](https://www.vim.org) |
| **Emacs** | • Infinitely extensible via Emacs Lisp<br>• Integrated shell, mail, calendar<br>• Org-mode for notes/tasks | [gnu.org/software/emacs/](https://www.gnu.org/software/emacs/) |

---

## Additional Resources

- [Official Python Tutorial](https://docs.python.org/3/tutorial/)
- [Real Python: Python Basics](https://realpython.com/)
- [PEP 8 – Style Guide for Python Code](https://peps.python.org/pep-0008/)

```{note}
**Log Your Training Hours!**
Don't forget that reviewing this documentation and familiarizing yourself with Python fundamentals directly supports our civic initiatives! Be sure to head over to [volunteer.youcount.ca](https://volunteer.youcount.ca) and log your reading and review time. Every hour counts!
```
