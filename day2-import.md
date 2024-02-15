# Day 2 - Python `import` 

### Python `http` request sender

This is a simple Python script that makes it easy to submit HTTP requests. You can use command-line arguments to set parameters, and verbose output is one of the options. This script is a useful addition to any toolkit, especially it helped me to understand a how `http` requests work in python, and how to leverage `requests` module to create an `http request`

```python
import requests

def perform_request(url):
    try:
        response = requests.get(url)
        if response.status_code == 200:
            print("Request successful!")
            print("Response content:")
            print(response.text)
        else:
            print(f"Error: Status code {response.status_code}")
    except requests.exceptions.RequestException as e:
        print(f"Error: {e}")

if __name__ == "__main__":
    url = input("Enter the URL to perform the HTTP GET request: ")
    perform_request(url)

```

### Explaination 

A popular Python idiom that determines if the current script is being executed by the Python interpreter as the main program directly, as opposed to being imported as a module into another script, is if __name__ == "__main__":.

This is what it implies:

__name__: Python has a unique built-in variable called this. "__main__" is the script that is being run directly, and __name__ is set to it. __name__ is set to the module name when a script is imported as a module into another script.

"__main__" is a string that in Python denotes the name of the main module. Direct execution of a Python script causes Python to set __name__ to "__main__".

### Let's understand the code line by line

import requests: This line imports the requests module, which provides functions for making HTTP requests in Python.

def perform_request(url): This line defines a function named perform_request that takes a single argument url. This function will be used to perform an HTTP GET request to the specified URL.

try:: This line starts a try block, indicating that the code inside it will be executed, and any exceptions that occur will be caught by the corresponding except block.

response = requests.get(url): This line sends an HTTP GET request to the URL specified by the url argument using the requests.get() function. The response object returned by this function is assigned to the variable response.

if response.status_code == 200:: This line checks if the status code of the response is 200, which indicates a successful HTTP request.

print("Request successful!"): If the status code is 200, this line prints a success message indicating that the request was successful.

print("Response content:"): This line prints a message indicating that the content of the response will be printed next.

print(response.text): This line prints the content of the response using response.text, which contains the response body.

else:: If the status code is not 200, this line indicates the start of the else block, which executes when the condition in the if statement is not met.

print(f"Error: Status code {response.status_code}"): This line prints an error message indicating the status code returned by the server.

except requests.exceptions.RequestException as e:: This line starts an except block, which catches any exceptions of type RequestException that occur within the try block.

print(f"Error: {e}"): If an exception occurs, this line prints an error message indicating the specific exception that occurred.

if name == "main":: This line checks if the script is being run directly (as opposed to being imported as a module).

url = input("Enter the URL to perform the HTTP GET request: "): If the script is being run directly, this line prompts the user to enter the URL to which they want to perform the HTTP GET request, and it stores the inputted URL in the variable url.

perform_request(url): This line calls the perform_request function, passing the URL entered by the user as an argument. This initiates the process of sending an HTTP GET request to the specified URL

### Further reading -

1. https://developer.vonage.com/en/blog/3-ways-to-make-http-calls-with-python-requests-beginner-to-advanced
2. https://www.digitalocean.com/community/tutorials/python-http-client-request-get-post
