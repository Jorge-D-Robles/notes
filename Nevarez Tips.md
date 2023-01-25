# Nevarez Tips

## Python 

```
pip install //whatever
```

To install different homebrew apps 

```brew install //whatever ```

To work on:
Prompt user to give you inputs on what you want problems to be

```python
while True: 
    try:
    	tries = int(input("How many problems do you want?: "))
    	if(ok(tries)): #create a function or condition that makes sure that your input is 			valid
        break
    else:
		continue
    except ValueError:
        print("Invalid input. Try again.")
        continue
```

After prompting user, use sympy to create problems. 

Store them in a list.

```python
problems_list = [] #empty list
#sympy logic codes goes here
# problem = stuff

for i in range(tries): 
    problem = sympylogic() #you are assigning whatever sympy gives you into a temporary problem variable called problem
	problems_list.append(problem)

#afterwards, problems_list will look like this:

problems_list = [symp(x^2 - 5x + 3), symp(x^3 - x^2 + 3x - 6)]

#to export it,
for problem in problems:
    print(problem)
    #add this problem as well to your pdf
  
with open ("pset2x2", "w") as file:
    for problem in problems:
        #add to pdf
```

