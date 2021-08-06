# CH 2 Selection Sort

in this chapter:

1. [Arrays and Linked lists](#arrlin).
2. [Selection sort algorithm](#Selectionsort).

### - How memory works
Imagine you go to a show and you need to check you things, A chest of drawers is available, each drawers ca hold one thing, you want to store two things, so you ask for drawers.

![Snag_37c3323](https://user-images.githubusercontent.com/56140418/128434769-0272a090-ab74-4251-a945-3a007b617afd.png)

you store your two things and now you are ready for the show, this is basically how the computer memory works, computer memory is a giant set of drawers and each drawer has an address.

![Snag_37ec046](https://user-images.githubusercontent.com/56140418/128434935-1c6eba5b-dcf3-4861-8162-ab71cc4018aa.png)

fe0ffeeb can be a slot address.

<a name="arrlin"/>

## 1- Arrays and Linked lists
sometimes you need to store a list in the memory, suppose you need to write an app to manage your todos, you will need to stor the todos as a list in the memory, you can use an array or a linked list.
First: we would use an array which would mean your todos will be stored right next to each other.

![Snag_3a85897](https://user-images.githubusercontent.com/56140418/128437892-55cd1323-ab54-4ab8-b5d9-672531849873.png)

now if you want to add a fourth element to the todos list, that would be hard because the memeory slots beside those three are occupied by other tasks, now you have to move the entire list to another place to add the fourth element and so on if you want to add additional element you have to move the entire array once again, this would be really slow, 
to solve this you should ask the computer for fixed number of slots from the begining , this is a good work around but you should be aware of : 
- you may not need the extra slots reserved, that's a waste of memory because you won't use it and no boy else can use it.
- you may exceed the number of slots reserved by the computer and thus you have to move the entire array again.

so it's a good work around but it's not the best so the linked lists came to the picture to solve this issue. 

### Linked lists

with linked lists you can store items in any place in the memeory each item will have an address of the next element in the linked list.

![Snag_3b2aa5f](https://user-images.githubusercontent.com/56140418/128438606-458d4656-874f-4b3f-8804-045d069c63ae.png)

it's easy to add an item in the linked list add it and add it's address to the previous element of the linned list, if you want to find 10,000 slots in the memory. your memory might have 10,000 slots but it dosen't have 10,000 slots together, here comes the linked list. 
so linked lists are much better at inserts, what are arrays good for?

### Arrays

Linked list has a problem suppose you want to read the last element in the list, you can't just read it because you don't know what is it's address, you have to go to item #1 and find address to item #2 and then address to item #3 and so on till the last item.
arrays are different you know the address for every element in the array, suppose your array contains five elements and you know your first element is at position 00, element five would be at position 04 ? right ? 

![Snag_53b62d](https://user-images.githubusercontent.com/56140418/128517586-210cd11f-d1e0-45ad-8560-3f298868d81a.png)

### Terminology

- elements in the array are numbered, this numbering starts from 0 not 1.
- the position of an element is called index.
- here are some run times for common opperations on arrays and linked lists.

![Snag_56084a](https://user-images.githubusercontent.com/56140418/128517943-ca749896-2563-452e-a177-a269d8b3883c.png)

### Inserting into the middle of a list

Suppose you want to add an item in the middle of a list, for a linked list it would be easy, you have to change the address that the previous element points to, but for the arrays you have to shift the rest of the elements down. 

![Snag_8754e5](https://user-images.githubusercontent.com/56140418/128525171-339524cf-fa54-477f-a5c0-7147c0b6e410.png)

![Snag_876282](https://user-images.githubusercontent.com/56140418/128525182-a074af2d-6e40-499b-a093-298d6e0f0bc4.png)

and if there's no place to sift elements you will have to move all the array to a new place in the memory.

### Deletions

What if we want to delete and element? for linked list it would be easy you have to change where the previous element points to, for arrays it would be easier than adding element in the middle of an array it will always work as you will be shifting things up not down, so you can always delete an element.

what about deletion run time? 

![Snag_8de810](https://user-images.githubusercontent.com/56140418/128526265-380c0662-0f6a-4d3b-90d4-c909e243f32e.png)

Which are used more? arrays or linked lists? it dependes on the use case, but arrays see a lot of use because they allow random access,there are two types of access, random access and sequential access. sequential access means you have can access elements one by one, Random access means you can jump directly to the element you want, so arrays are a lot faster at reads.

#### - Arrays and linked lists are bulding blocks to more complex data structures.

<a name='Selectionsort'/>

## 2- Selection sort

Suppose you have a bunch of music on your phone and for each artist you have a play count, you want to sort this list from most to least played, so that you rank your favourite artist. 

one way is to search the whole list for the most-played artist and add it to another list, do it again to find the next most-played artist, keep doing it and you will end up with a sorted list.

To find the highest played artist you have to check each item in the list this means **O(n)** and you have to do it **n** times this means O(n x n) or  O(n^2). 

![Snag_d35cd3](https://user-images.githubusercontent.com/56140418/128537135-fdc39b70-d856-46f2-adee-60787be2a0d6.png)

- Sorting algorithms are so important you can use it to sort : 

1. names in a phone book.
2. travel dates.
3. Emails (newest to oldest).

```python

def find_smallest:
  smallest = arr[0]
  smallest_index = 0
  
  for i in range(1,len(arr))
     if arr[i] < smallest:
        smallest = arr[i]
        smallest_index = i
        
  return smallest_index 

def selection_sort(arr):
    newArr = []
    
    for i in range(len(arr)):
        smallest = find_smallest(arr)
        newArr.append(arr.pop(smallest))
    return newArr
    
 print selection_sort([5,7,3,4,6])
        
```














