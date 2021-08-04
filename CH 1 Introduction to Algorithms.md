# Chapter 1 Introduction to Algorithms

**this chapter talks about:**

1. [Binary search](#Binary) .
2. [calculate algorithm runing time using (Big O notaion)](#BigO).

- Algorithm is a set of instructions to complete a task, any piece of code could be called an algorithm.

<a name="Binary"/>

## 1. Binary Search

Binary search is an algorithm; its input is a sorted list of elements if your value is in the list it returns its *position* otherwise it returns null.

For Example: if you are looking for a number between 1 and 100 if you are using **simple search** you start guessing 1,2,3,4 ..... and so on that's not an efficient way of searching because you are eleminating only one element with each guess, a better way to guess would be to start with 50 that way you would be eleminating half the elements and the next guess would be the middle number to cut another half and so on until reaching the number. 

![Snag_4631f49](https://user-images.githubusercontent.com/56140418/128191857-f356dd0a-3a00-4abd-8cd3-9133a5f057df.png)

suppose you are looking for a word in a dictionary that has 240000 words, in the worst case how many steps would every search algorithm take?

-  simple search would take 240000 step if the word you are looking for is the last word in the dictionary.
-  binary search you are eliminating so much numbers of words in each step so binary search would take 18 step to find the word, binary search would take Log2 n steps.

implementing binary search using Python, we will be using an array, the binary_search function will take a sorted array and a number if the number is in the array it returns the position otherwise it returns null.

```python
def binary_search(list,item):

  low = 0
  high = len(list) - 1

  while low <= high:
    mid = ( low + high ) //  2
    guess = list[mid]

    if (guess == item):
      return mid 

    if (guess < item):
      low = mid + 1
    else:
      high = mid - 1
  return 'Not Found'

my_list = [1,3,5,7,10]

print(binary_search(my_list,3))
```
<a name="BigO"/>

## 2. Running time/ Big O notation

while choosing an algorithm you want to calculate its running time to choose the most efficient algoritm.

- simple search has a linear time increment.
- binary search has a logarithmic time increment.

Big O notaions is a special notation that tells you how fast an algorithm is, Big O notation tells you how running time increases as the list size increases, Big O notation is about the worst case senarion.

### - Some common Big O run times.

sorted from fastest to slowest.
-   O(log n), also known as log time. example: Binary search.
-   O(n), AKA linear time. example: Simple search.
-   O(n * log n), example: a fast sorting algorithm like quick sort.
-   O(n^2), example: a slow sorting algorithm like selection sort.
-   O(n!), example: a really slow sorting algorithm like travilling salesperson.

if you try to draw # of boxes using the algorithms above, what would be the algortims worst-case run time?

![2021-08-04_14-32-22](https://user-images.githubusercontent.com/56140418/128191587-11d9df65-f5af-436d-b277-b892b16c0380.png)

The main takeways are as follows:

-  Algorithms speed isn't measured in seconds but instead in the  growth of the number of operations.
-  instead, we talk about how quickly the run time of the algorithm increases as the size of the input increase.
-  run time of algorithm is expressed in Big O notation.
-  O(log n) is alot faster than O(n), but it gets a lot faster as the list size increases.

### - The traviling sales person

The most famous unsolved computer science problem, the sales person has to hit five cites while traviling the minimum distance
there are 120 permutations for 5 cities

![2021-08-04_15-07-29](https://user-images.githubusercontent.com/56140418/128191050-5b44e453-06bc-4d39-b8ff-3a9ca4499d63.png)

for 6 cities it will take 720 operations there are 720 permutations, in general for n number of cities there will be n! factorial number of permutations this is a terrible algorithm that still unsolved till now.

![1](https://user-images.githubusercontent.com/56140418/128191279-070ffe1b-f9a4-41a5-9a13-7658b0a18ff0.png)

## Recap

- Binary search is a lot faster than simple search.
- O(log n) is alot faster than O(n), but it gets a lot faster as the list you are searching through grows.
- Algorithm speed isn't measured in seconds.
- Algorithm times are measured in terms of growth of an algorithm.
- Algorithm times are wwritten in Big O notation.


