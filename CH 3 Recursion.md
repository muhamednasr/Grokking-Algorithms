### in this chapter:

1. Recursion![Snag_2402299](https://user-images.githubusercontent.com/56140418/128761148-84ec5a19-4d44-4668-91d9-6ff1c153b446.png)
![Snag_240921c](https://user-images.githubusercontent.com/56140418/128761216-5d75f0a5-e4c3-431a-a81f-38b667696586.png)


Pseudo code is a high-level description of the problem you're trying to solve, it's writtem like code, but it's meant to be closer to human language.
 
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







