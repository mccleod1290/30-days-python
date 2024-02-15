# Day 2 - Python `import` 

### Python `http` request sender

This is a simple Python script that makes it easy to submit HTTP requests. You can use command-line arguments to set parameters, and verbose output is one of the options. This script is a useful addition to any toolkit, especially it helped me to understand a how `http` requests work in python, and how to leverage `requests` module to create an `http request`

```python
import sys
import requests

def send(name):
    response = requests.get("http://httpbin.org/json")
    return response.json() if response.status_code == 200 else "There was an error"

if __name__ == "__main__":
    name = sys.argv[1] if len(sys.argv) > 1 else "Unknown"
    print(send(name))

```

### Explaination 

A popular Python idiom that determines if the current script is being executed by the Python interpreter as the main program directly, as opposed to being imported as a module into another script, is if __name__ == "__main__":.

This is what it implies:

__name__: Python has a unique built-in variable called this. "__main__" is the script that is being run directly, and __name__ is set to it. __name__ is set to the module name when a script is imported as a module into another script.

"__main__" is a string that in Python denotes the name of the main module. Direct execution of a Python script causes Python to set __name__ to "__main__".

### Let's understand the code line by line

import sys: This imports the sys module, which provides access to some variables used or maintained by the Python interpreter and to functions that interact with the interpreter. We'll use it to access command-line arguments.

import requests: This imports the requests module, which allows us to send HTTP requests easily.

def send(name):: This defines a function named send that takes one argument, name.

response = requests.get("http://httpbin.org/json"): This line sends an HTTP GET request to the URL "http://httpbin.org/json" using the requests library and assigns the response object to the variable response.

return response.json() if response.status_code == 200 else "There was an error": This line checks if the status code of the response is 200 (which indicates a successful request). If it is, it returns the JSON content of the response using the .json() method. Otherwise, it returns the string "There was an error".

if __name__ == "__main__":: This is a Python idiom that checks if the script is being run directly by the Python interpreter (as opposed to being imported into another script). If it is being run directly, the code block below is executed.

name = sys.argv[1] if len(sys.argv) > 1 else "Unknown": This line gets the first command-line argument provided when running the script (sys.argv[0] is the script name itself). If there are command-line arguments (len(sys.argv) > 1), it assigns the first argument to the variable name; otherwise, it defaults to "Unknown".

print(send(name)): This line calls the send function with the name as an argument and prints the result
