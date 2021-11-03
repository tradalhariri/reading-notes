# Big O: Analysis of Algorithm Efficiency

* Big O notation is used to decribe the performance of algorithms.
* We are always compute Big O for the worst case of algorithm.
* we can measure Big O based on two factors: 
  * Time : number of basic operation used.
  * Space : How amount of memory needed.
* we refere to Big O by N and N represent the size of input.
* Order of Growth represent increasing in Time and Space complexity as the input size N increases.
![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/images/OrdersOfGrowth.png)

* we can classified orders of growth depend of the input size as following:
  * Constant Complexity  Growth : it means that input size has no effect on time or space.
  * Logarithmic Complexity  Growth : means that input size has a slightly effect on time and space
  * Linear Complexity  Growth : means that the time and space increases linearly with input size.
  * Linearithmic Complexity Growth : means that the time and space increases by N and Log N  with input size.
![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/images/EfficiencyNotations.png)

# Linked Lists 

### What is a Linked List
* linear list is a sequential data structure which composed of nodes. each node connects with next node (has a reference to the next node).
* there are two types of linked lists. Singly linked list and Doubly linked list.
* in Singly linked list each node holds one reference to the next one.
* in Doubly linked list each node holds two reference , one for the next node and one for the previous node.
* The head is a node and represents the first  node in linked list.
Example of Singly linked list:
![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/images/LinkedList1.PNG)

### Traversal 
* if we want to traverse through the linked list we cant use for loop. because there are no indexes . To do that the best way is to use while loop.

# What’s a Linked List, Anyway? [Parts 1+ 2]
* linked list is linear data structure, which means there is a sequence and order to traverse the linked list
* the best example of non linear data structure is tree.
![](https://miro.medium.com/max/875/1*Xokk6XOjWyIGCBujkJsCzQ.jpeg)
### Memory management
* linked list differs from array in a way that is organized in memory.
* array elements are stored in memory in contiguous  block of memory.
* linked list dose not need to be in contiguous block of memory. any node can hold a reference to another node in different location. it is not necessary for nodes references to be contiguous.
* So searching for element in array is faster than linked list because the way the memory allocate it.
![](https://miro.medium.com/max/875/1*G43FVT5xJ1n1QDKVNZUxXQ.jpeg)

## References 
[ Big O: Analysis of Algorithm Efficiency](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/big_oh.html)

[Linked Lists](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/singly_linked_list.html)

[What’s a Linked List, Anyway? [Part 1]](https://medium.com/basecs/whats-a-linked-list-anyway-part-1-d8b7e6508b9d)
[What’s a Linked List, Anyway? [Part 2]](https://medium.com/basecs/whats-a-linked-list-anyway-part-2-131d96f71996)


