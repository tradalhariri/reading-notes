# A beginner's guide to Big O Notation

![Big O](https://assets.digitalocean.com/articles/alligator/js/big-o-notation/o-complexity.png)

## Big O notation 
* Big O notation is a concept used in computer science to describe how the algorithm performance will decrease if the input size increases. Big O describes the worst case situation.
  ----------------------------------------------------------------
* O(1) 
  The Big O(1) means that the algorithm will take the same time or space regardless of the input size.

  The example for that is setting the first item in the list with specific value.

* O(N) 
  The Big O(N) means that the algorithm performance will decrease linearly with increasing of the input size.

  Ex. searching for a value in the list.


* O(N²) 
  The Big O(N²) means that the algorithm performance will decrease linearly (but more than O(N) )  with increasing of the input size.

  Ex. searching for a value in the nested list.


* O(2^N)
  This the worst Big O . and it means whenver we increase the input by one the algorithm performance will decrease twice.

  Ex . Fibonacci numbers


## Logarithms
* if we can reach O(1) that is the best performance.
* The Big O(log N) is the opposite of O(2^N).
* for example the Big O for binary search algorithm  is O(log N) because it try to find a value in the list starting from the middle of the list. Due to the list should be sorted before we apply the binary search algorithm on it if we could not find a value in the middle of the list , we have two choices now, if the value in the  greater than the value we search for it we then choose the middle to be between the previous middle and beginning of the list and so on . this algorithm decrease the input each time to be half of the original one. we reach Big O(log N) as a result.
  
  





## References 
[Beginners Guide to Big O](https://rob-bell.net/2009/06/a-beginners-guide-to-big-o-notation)
