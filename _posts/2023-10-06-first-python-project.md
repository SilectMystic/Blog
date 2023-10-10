## To Do Python Project

![Todo Project output](/assets/todo.png)

Our Python To-Do project is one of our past projects that we have done before while we were working on javascript so we were just going to do it again but this time in Python and only the simple tasks like adding and deleting and not that the user can mark it as done and filters.

### The Starter

When we started with the project the first thing that i thought of doing was making an input the would add to a list using user input for example 
```
a = ['List']
a.append(input('Input here'))
```
and then use that input to set all the todos that the user wants to have in their application.

### The Todo list / Add&Rem

After having a starter on how to get all their todos I started working on a while loop in order to make the app run endlessly unless the user actually closes the program that way we can have the program ask for input every time. After making a simple infinite while loop and adding the user input part I started working on the commands for deleting and adding more todos so I made an if statement asking for either adding an item or removing one by the provided index number.
```
a = ['List']
while 1:
    b = input('Would you like to add more or remove? (add, rem): ')
    if b == 'add':
        a.append(input('input here'))
        print(a)
```
In the code above I added both initial code and also worked on while loop and in the If statement to work on adding new items using the append statement. Now to work on how to remove an item from the list via user input so first thing I did was add an elif with an if statement to search for the input 'rem' and then remove the item via an index number, but when I finished planning on how to work on removing an item I started working on a friendly index for a common user so first I started doing a for loop at the beginning of the code by first making a variable starting from one then inside this for loop, I would be able to print both the list and the custom index.
```
a = ['List']
while 1:
    k = 1
    for items in a:
        print(str(k) + '. ' + items)
        k += 1
    b = input('Would you like to add more or remove? (add, rem): ')
    if b == 'add':
        a.append(input('input here'))
        print(a)
```
Now with the index done, I was finally able to move on with removing an item so first as mentioned before made an elif that would search for 'rem' user input, and then it would run a command to delete the given inputs. But this wasn't as easy since I didn't really use this statement before and ended up confusing the pop and remove statement and getting many errors on code but after some research, I was able to use pop with the given user integer index input.
```
    elif b == 'rem':
        m = int(input('What number you want to delete'))
        m -+ 1
        a.pop(m)
        print('Your item was removed!')
```
After writing it down I added a function that will basically subtract 1 number from the user input because the index was customized to show in normal counting so I needed to subtract one in order to get the real index order of the list in order to avoid an index error since they would either put a number higher than any on the list or delete the wrong item.

After finishing all the code for adding and removing I ended it by writing down an else statement just printing to the user to use one of the presented commands on the code or it wouldn't work since they aren't using either add or rem.
```
    else:
        print('\n(Please give a correct input)')
```

### The Finishing Touches

With all the core code finished I ended up doing some final touches. First I went back to the elif statement to remove a todo and added a try and except statement in order to avoid the code crashing on user input error because especially in this bit of code you need very specific input or the code will start to yell at you for putting an invalid option.
```
    elif b == 'rem':
        try:
            m = int(input('What number you want to delete'))
            m -= 1
            a.pop(m)
            print('Your item was removed!')
        except IndexError:
            print('(Please give an available number)')
        except ValueError:
            print('(Please give an available number)')
```
While writing the except statement I ran into some problems because Value Error under except usually would stop the code from crashing but it wouldn't stop it since part of an error code that was 100% possible here would be an index error so first I tried putting both IndexError and ValueError together like here.
```
except IndexError + ValueError:
```
But this would crash the code since you actually can't give 2 error values on one except so I had to separate them and it ended up working flawlessly by preventing the code from crashing under any user input error.

After eliminating the possibility of getting the code to crash there I added a placeholder on the list that it would delete later after the first todo input which was as simple as making an if statement inside the add if statement that would delete the placeholder if it is present in order to avoid code error of trying to delete something that's not there.
```
if 'Add a todo!' in a:
            a.remove('Add a todo!')
```

Finally, after having all the extra features done I added some extra finishing touches like '\n' in order to make new lines after every print and added a separator at the beginning to separate the code after every iteration.
```
todos = ['Add a todo!'] #The list for the todo with an item called Add a todo for the user to know.
while 1: #Start of the infinite while loop
    print('\n~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~') #Separation for iteration run 
    print('\nHere is your list\n') #Guiding user to where is the list
    k = 1 #Index
    for items in todos: #Loop for items and index
        print(str(k) + '. ' + items) #Print both k index variable and item
        k += 1 #To increase the index number
    print()
    b = input('Would you like to add more or remove? (add, rem): ') #To collect what user wants to do
    if b == 'add':
        todos.append(input('\nAdd your item: ')) #Adds the item from user input
        print('\nYour item was added!')
        if 'Add a todo!' in todos:
            todos.remove('Add a todo!') #To remove item placeholder only when its there
    elif b == 'rem':
        try: #To avoid code error on incorrect input value
            c = int(input('\nWhat number you want to delete? '))
            c -= 1 #To keep withing normal counting from 1 not 0
            todos.pop(c) #To remove item using input -1
            print('\nYour item was removed!')
        except IndexError: #To avoid input error of higher index number
            print('\n(Please give an available number)')
        except ValueError: #To avoid input error of non-integer
            print('\n(Please give an available number)')
    else: #To tell user to use available commands
        print('\n(Please give a correct input)')
```