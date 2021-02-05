# whitefuck
[![PyPi](https://img.shields.io/pypi/v/whitefuck.svg?style=flat-square)](https://pypi.org/project/whitefuck/)

(Whitespace + Brainfuck) / 2 = Whitefuck
  
***
  
  
Installation
====
Run this:
```bash
pip install whitefuck
```

***
  
Syntax
====

In this doc,  
  "s" means "Space",
  "t" means "Tab",
  "b" means "Breakline".

| In whitefuck | In brainfuck | How does it work |
| ------------ | ------------ | ---------------- | 
| ssb | + | increment (increase by one) the byte at the data pointer. |
| stb | - | decrement (decrease by one) the byte at the data pointer. |
| tsb | > | increment the data pointer (to point to the next cell to the right). |
| ttb | < | decrement the data pointer (to point to the next cell to the left). |
| sssb | . | output the byte at the data pointer. |
| sstb | , |accept one byte of input, storing its value in the byte at the data pointer. |
| stsb | [ | if the byte at the data pointer is zero, then instead of moving the instruction pointer forward to the next command, jump it forward to the command after the matching ] command. |
| sttb | ] | if the byte at the data pointer is nonzero, then instead of moving the instruction pointer forward to the next command, jump it back to the command after the matching [ command. |

***

Usage
====

```
usage: whitefuck [-h] [-m {run,convert}] [-i INPUT] [-c COUNTER] [-o OUTPUT] file

positional arguments:
  file                  File to run

optional arguments:
  -h, --help            show this help message and exit
  -m {run,convert}, --mode {run,convert}
                        Mode. Default: run

Run:
  -i INPUT, --input INPUT
                        A input.
  -c COUNTER, --counter COUNTER
                        Number of counters to make.

Convert:
  -o OUTPUT, --output OUTPUT
                        Path to export result.
```

***

Use on script
====

```python
>>> import whitefuck as wf
>>> with open("./example/helloworld.wf") as f:
...   s = f.read()
...
>>> wf.run(s)
Hello World!
>>> f = wf.make_function(s)
functools.partial(<function run at 0x00000203123669D0>, '  \n  \n  \n  \n  \n  \n  \n  \n  \n \t \n\t \n  \n  \n  \n  \n  \n  \n  \n  \n\t \n  \n  \n  \n  \n  \n  \n  \n  \n  \n  \n  \n\t \n  \n  \n  \n\t \n  \n\t\t\n\t\t\n\t\t\n\t\t\n \t\n \t\t\n\t \n   \n\t \n  \n  \n   \n  \n  \n  \n  \n  \n  \n  \n   \n   \n  \n  \n  \n   \n\t \n  \n  \n  \n  \n  \n   \n\t\t\n\t\t\n  \n  \n  \n  \n  \n  \n  \n  \n  \n  \n  \n  \n  \n  \n  \n   \n\t \n   \n  \n  \n  \n   \n \t\n \t\n \t\n \t\n \t\n \t\n   \n \t\n \t\n \t\n \t\n \t\n \t\n \t\n \t\n   \n\t \n  \n   \n\t \n  \n   \n', '', 1024)
>>> f()
Hello World!
```

***

Prerequisites
====
* **Python 3.8 (Please make GitHub issue if you can use this lib on different python version)**  
***
  
License
====
Please see [LICENSE](https://github.com/sevenc-nanashi/whitefuck/blob/main/LICENSE).
