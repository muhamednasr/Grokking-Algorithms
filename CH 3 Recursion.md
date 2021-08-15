### in this chapter:

1. [Recursion](#recursion).

Pseudo code is a high-level description of the problem you're trying to solve, it's writtem like code, but it's meant to be closer to human language.
 
<a name="recusrion"/> 

## Recusrion

Suppose you are diggind through your grandma attic and you find a mysterious locked suit case and you've been told that the key to this case is in another box that contains other boxes what would be your searching algorithm to find the key? 

Here's an approach: 

![Snag_228df08](https://user-images.githubusercontent.com/56140418/128757926-3688d137-14d2-4cee-808f-f30dc3f7e182.png)


1. Make a pile of boxes to look through. 
2. grab a box and look through.
3. if you find a box add it to the pile.
4. if you find a key you are done.
5. repeat.

Here's an alternate approach.

![Snag_22a1249](https://user-images.githubusercontent.com/56140418/128758100-a9343d0a-00a1-41e5-af09-36d74e181569.png)

1. look through the box.
2. if you find a box go to number 1 again.
3. if you found a key you are done.

#### pseudo codes 

1. approach one.

```python

def look_for_key(main_box):
    pile = main_box.make_pile_to_look_through()
    
    while pile_is_not_empty:
     box = pile.grab_a_box()
     for item in box: 
       if item.is_box():
          pile.add_item(item)
       else item.is_key():
          print 'Key Found !!'
  
```
2. approach two (Recursion).


```python

def look_for_key(box):
    for item in box:
        if item.is_box():
           look_for_key(item):
        else item.is_key():
           print 'Key Found'

```

Both approachs accomplish the same thing, but the second one is clearer, recursion may not achieve a performance benifit, but it makes the solution clearer, in fact somtimes loops may be more performance efficient than recusrion, choose what is more convinient for your solution, many important algorithms use recursion so it's important to understand the term.

### Base case and recursive case

Because recursive function calls itself so it's easy to end up in na infinite loop, suppose you write down a function to print countdown from 4 to 1, you can write it recursively like that: 

```python
def count_down(number):
  print number
  count_down(number-1)
```
![Snag_23cb632](https://user-images.githubusercontent.com/56140418/128760686-f78674ea-c587-4c4a-bba0-0a18baed018f.png)

when you write a recursive function you have to tell it when to stop recursing, that's why every recursive function have to parts: the base case and the recursive case. the recursive case is when function calls it self and the base case is when function dosen't call itself so the recursing stop.

```python
def count_down(number):
  print number
  if number <= 0:
    return 0
  else:
  count_down(number-1) 
```

![Snag_240921c](https://user-images.githubusercontent.com/56140418/128761216-5d75f0a5-e4c3-431a-a81f-38b667696586.png)

### The Stack

The stack is a very important programming concept, stack is a very simple data structure, when you insert an item to the stack it's added to the top of the stack, and when you remove an item from the stack you just remove the most top item in the stack and read it just like that.
**push** (insert), **pop** (remove and read).

![Snag_265121b](https://user-images.githubusercontent.com/56140418/128765855-5d01996a-fec8-490f-b557-a4e8c3ce930c.png)

#### The call stack

computer uses stack internally called **call stack** 

```python
def greet(name):
  print 'hello' + name + ''
  greet2(name)
  print 'how are you' + name
  bye()
```
this function calls two other functions **Greet2** and **bye**, let's see what happens when you call this function.

suppose you call function **greet** the computer allocates a box of memory for the function for the call and saves all the variables in the function, then calls the **greet2** and again allocates a box of memory and save the variables of the function after pausing the **greet** function call, computer uses stack for all the boxes called **call stack** 

![Snag_2857185](https://user-images.githubusercontent.com/56140418/128769947-bfa25332-f3a9-491c-baf4-6285249979db.png)

after the **greet2** is done the function is popped of the stack and the call gets back to **greet** now it calls the **bye** function to proceed the function 

![Snag_287ce9f](https://user-images.githubusercontent.com/56140418/128770257-16c8a665-3167-4a38-803b-d2cdfadf001d.png)

and then the **bye** function is done and the call gets back to **greet** and this is the stack, it's used to call functions by sequence and save variable for each function call.

### The call stack with recursion

Call stack is also used in case of recursion calls of functions, let's take an example and see, if we have to calculate the factorial of 3 = 3 * 2 * 1.

```python
def fact(x):
   if x == 1:
      return 1
   else:
      return x * fact(x-1)
```
now we call fact(3) and see what happens to the stack,

![Snag_350e63c](https://user-images.githubusercontent.com/56140418/129464397-035af840-89a5-4326-8aea-6d689511eb66.png)

function Fact() will be called thre times due to that the condition (X == 1) will be satisfied in the third call so that will be the stack after the three fact() calls,
and all the functions calls will be half processed, now the app will start to complete processing calls by poping up the most recent function in the stack.

![Snag_353ecd5](https://user-images.githubusercontent.com/56140418/129464459-7598c69e-dcdd-4353-8432-339aed7408c8.png)

and returns the processing result.
**Hence** not any of the calls are fully processed till now. 

using stack is convenient, but there's a coast: saving all that calls can consume a lot of memory, each function call takes up some memory, at this point you have two options: 

1. you can rewrite your code to use loops.
2. you can use **tail recursion** that's and advanced recursion technique and not all languages support it.

## Reacp

1. Recusrion is when a function calls itself.
2. Every recursive function has two cases: base case and recursive case.
3. A stack has two operations: Push and Pop.
4. All functions calls go into the Call stack.
5. The call stack can get very tall which takes a lot of memory.





