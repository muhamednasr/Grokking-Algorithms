# CH 2 Selection Sort

in this chapter:

1. [Arrays and Linked lists](#arrays).
2. Selection sort algorithm.

### - How memory works
Imagine you go to a show and you need to check you things, A chest of drawers is available, each drawers ca hold one thing, you want to store two things, so you ask for drawers.

![Snag_37c3323](https://user-images.githubusercontent.com/56140418/128434769-0272a090-ab74-4251-a945-3a007b617afd.png)

you store your two things and now you are ready for the show, this is basically how the computer memory works, computer memory is a giant set of drawers and each drawer has an address.

![Snag_37ec046](https://user-images.githubusercontent.com/56140418/128434935-1c6eba5b-dcf3-4861-8162-ab71cc4018aa.png)

fe0ffeeb can be a slot address.

<a name="arrays"/>

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













