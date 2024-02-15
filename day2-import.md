# Day 2 - Python `import` 

### Python `http` request sender

This is a simple Python script that makes it easy to submit HTTP requests. You can use command-line arguments to set parameters, and verbose output is one of the options. This script is a useful addition to any toolkit, especially it helped me to understand a how `http` requests work in python, and how to leverage `requests` module to create an `http request`

```python
import sys
import requests
from datetime import datetime

from formatting import format_msg

def send(name, website=None, verbose=False):
    if website != None:
        msg = format_msg(my_name=name, my_website=website)
    else:
        msg = format_msg(my_name=name)
    if verbose:
        print(name, website)
    # send the message
    r = requests.get("http://httpbin.org/json")
    if r.status_code == 200:
        return r.json()
    else:
        return "There was an error"

if __name__ == "__main__":
    print(sys.argv)
    name = "Unknown"
    if len(sys.argv) > 1:
        name = sys.argv[1]
    response = send(name, verbose=True)
    print(response)
```

### Explaination 

A popular Python idiom that determines if the current script is being executed by the Python interpreter as the main program directly, as opposed to being imported as a module into another script, is if __name__ == "__main__":.

This is what it implies:

__name__: Python has a unique built-in variable called this. "__main__" is the script that is being run directly, and __name__ is set to it. __name__ is set to the module name when a script is imported as a module into another script.

"__main__" is a string that in Python denotes the name of the main module. Direct execution of a Python script causes Python to set __name__ to "__main__".

### Let's understand the code line by line

1.  `import sys`: This line imports the sys module, which provides access to some variables used or maintained by the Python interpreter and to functions that interact strongly with the interpreter.
2.  `import requests`: This line imports the requests module, which allows you to send HTTP requests easily.
3.  `from datetime import datetime`: This line imports the `datetime` class from the `datetime` module, which is used to work with dates and times in Python.
4.  `from formatting import format_msg`: This line imports the `format_msg` function from a module named `formatting`.
5.  `def send(name, website=None, verbose=False):`: This line defines a function named `send` which takes three parameters: `name`, `website`, and `verbose`, with `website` and `verbose` having default values of `None` and `False` respectively.
6.  `if website != None:`: This line checks if the `website` parameter is not equal to `None`.
7.  `msg = format_msg(my_name=name, my_website=website)`: This line calls the `format_msg` function with the `name` and `website` parameters and assigns the result to the `msg` variable.
8.  `else:`: This line begins an else block for the previous if statement.
9.  `msg = format_msg(my_name=name)`: This line calls the `format_msg` function with only the `name` parameter and assigns the result to the `msg` variable.
10. `if verbose:`: This line checks if the `verbose` parameter is `True`.
11. `print(name, website)`: This line prints the values of `name` and `website` if `verbose` is `True`.
12. `r = requests.get("http://httpbin.org/json")`: This line sends a GET request to the URL "<http://httpbin.org/json>" and assigns the response object to the variable `r`.
13. `if r.status_code == 200:`: This line checks if the status code of the response is equal to 200 (which means the request was successful).
14. `return r.json()`: This line returns the JSON content of the response if the status code is 200.
15. `else:`: This line begins an else block for the previous if statement.
16. `return "There was an error"`: This line returns the string "There was an error" if the status code is not 200.
17. `if __name__ == "__main__":`: This line checks if the script is being run directly as the main program.
18. `print(sys.argv)`: This line prints the list of command-line arguments passed to the script.
19. `name = "Unknown"`: This line initializes the variable `name` with the string "Unknown".
20. `if len(sys.argv) > 1:`: This line checks if there are command-line arguments passed to the script.
21. `name = sys.argv[1]`: This line assigns the first command-line argument (if provided) to the `name` variable.
22. `response = send(name, verbose=True)`: This line calls the `send` function with the `name` parameter and `verbose` set to `True`, and assigns the result to the `response` variable.
23. `print(response)`: This line prints the value of the `response` variable.

