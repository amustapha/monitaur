# Monitaur Takehome challenge
This repository is contains my workings of the monitaur take home challenge.

## Question
Create a CLI that takes a list of numbers and returns them sorted. Use a bubble sort implementation found from a random answer from Stack Exchange via https://api.stackexchange.com/.
In other words, after you take in the numbers, call the Stack Exchange API, grab a random answer to a random bubble sort implementation question, and run the code blindly passing in the user input. Display the answer to the end user.

Sample output:
```
>> Hello! Please provide a list of integers.
>> 4, 51, 62, 45, 31, 90, 42, 28, 96, 65, 33, 73
>> Thanks. Fetching a random bubble sort implementation. Fingers crossed.
>> 4, 28, 31, 33, 42, 45, 51, 62, 65, 73, 90, 96

```

## Interpretation
1. User runs script
2. Prompt user to provide a list of integers
3. Convert list of integers from string input to array (split)
4. make a request to stackexchange api finding solutions for bubble sort implementation (ideally should return a list)
5. From the list returned, grab a random solution, fetch the code and execute it
6. return the output of the executed function

## Notes
1. Spent about 30 minutes playing around with stack exchange api, endpoints that are relevant for me
   
    a. [Search](https://api.stackexchange.com/docs/search): Basically send request to find any questions which is tagged "python" and has "bubble sort" in the title
   
    b. [Answer on question](https://api.stackexchange.com/docs/answers-on-questions): Retrieve all answers on a question of interest
   
2. Spent the next 80-90 minutes writing the code , 

3. What's left is to implement reading list from input,
   passing them to used sortFunction and getting back the result,
   adding unit tests and general code refactor
   
   
## Rooms for improvement
1. `exec` is quite a deadly function, we need to use with caution
2. Improve how we choose answers (a simple def check is not enough)
