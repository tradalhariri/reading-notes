# Satck 

- The Stack is a  linear data structure which contains nodes and each node has one reference to the next node in the stack.
- The stack follows `FILO` concept which means that the first item added to the stack will the last item poped out from the stack.
- The stack has the special pointer called `top` which always points to the top of the stack.
![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/stack1.PNG)
- when we add a new node we added it to the top of the stack and make sure to update the `top` to points to the new node.
- when we pop from the stack we pop the node that `top` points to it and we should update the `top` to point to the next node after it.
- push or pop a new node to the stack it always taks O(1) time because no matter how nodes exists in the stack.

# Queue

- The Queue is a  linear data structure which contains nodes and each node has one reference to the next node in the Queue.
- The Queue follows `FIFO` concept which means that the first item added to the Queue will the first item dequeued from the stack.
- The Queue has two special pointers
  - Front : points the first node added to the Queue.
  - Rear : points the last node added to the Queue.

![](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/Queue.PNG)
- when we add a new node we added it to the tail of the Queue and make sure to update the `Rear` to points to the new node.
- when we remove a node from the Queue we remove the node that `Front` points to it and we should update the `Front` to point to the next node after it.
- Enqueue or Dequeue a new node it always take O(1) time because no matter how nodes exists in the Queue.

### References

[Stack And Queue](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/stacks_and_queues.html)
