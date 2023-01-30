# Python & AWS Candidate Test

## Basic knowledge questions

- What is \_\_main\_\_.py used for?
## It's used for a spcial constructions the name of the top-level environment of the program, which can be checked using the __name__ == '__main__' expression; and. the __main__.py file in Python packages. Thanks to this, it is not necessary to define the main function every time you write a program.   It removes the ambiguity among end-user about the entry point of the program as Python does it automatically and helps in clean execution of the code

- How to prevent python module code from executing when the module is imported?
## To prevent code in the module from being executed when imported, but only when run directly, you can guard it with this "if"

- What's the name of method that represents a class constructor in Python?
##  the __init__() method

- What options do you have when you need to insert value of a variable into string? Name at least three.
## the string format method, f-strings in Python >= 3.6, old school % formatting

- How can you truly restrict access to a private method of a class in Python?
## There is any truly secure method to make a private class in python, but the closest thing to do it is to put __ (double underscore) before name of class

- What Python feature would you use to add some functionalities to an existing function without interfering into its code?
## One way is to use inner function just by indenting it into existing function, in this way we aren't modyfying existing code, just adding a new one.

- How is @staticmethod different from @classmethod?
## The difference between the Class method and the static method is:
A class method takes cls as the first parameter while a static method needs no specific parameters. A class method can access or modify the class state while a static method can’t access or modify it. In general, static methods know nothing about the class state. They are utility-type methods that take some parameters and work upon those parameters. On the other hand class methods must have class as a parameter. We use @classmethod decorator in python to create a class method and we use @staticmethod decorator to create a static method in python.
    
- What is the advantage of using **with** keyword when reading/writing a file in Python?
## The 'with' statement helps with clearer syntax (for example, by using that statement we don't have to worry about writing file.close() at the end of code, it is done automaticly)

## Problem solving

**problem-solving.py** script takes advantage of Person class in order to create every person defined in the "people" array and then, for each of them, run introducing method. It also prints total number of created people. Threading is used to create each person in a different thread. Unfortunately, script has some bugs preventing it from working properly. 
- Please debug, fix and explain what issues the script had.  
- Currently, number of created people is printed at the beginning. Please implement some improvements, so that number of people created is printed always at the very end (without using time.sleep).
- You are not allowed to interfere into **introduce** method code.

## Create something whilst learning something new
For this task you will need your personal account in AWS. Please create one if you don't have it yet (do not worry about costs, everything you do here will covered by AWS Free Tier).

- Create a REST API in AWS API Gateway.
- Create 2 HTTP methods in the API: GET & POST.
- Create a DynamoDB Table (keep provisioned WCU & RCU low to stay within Free Tier, 2 will be OK) and name it "users". It should consist only of a parition key (hash key) which is "user_id".
- Create a lambda function and integrate it with the API POST method. In the JSON body of HTTP POST request, user should be able to specify his first name and age. Lambda should take provided body and insert it into your DynamoDB table as a new item. Value for user_id column should be generated as a random GUID and returned to the caller in the response.
- Create second lambda function and integrate it with the API GET method. GET method should take a user_id as path parameter. Lambda should lookup the DynamoDB table (using **query** method!) and either return user or 404 status code if it doesn't exist.

Please create a new GitLab/GitHub repository, upload your lambda code in there and share link to the repo with us.
Repository should also contain a README.md with URLs to your API GET & POST methods and explanation about how to use them (exact paths, example body for POST method).
