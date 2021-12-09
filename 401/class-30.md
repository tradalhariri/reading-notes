# Hash Tables 

## What is a Hashtable? 

* Hash : a hash is the result of some algorithm taking an incoming string and converting it into a value that could be used for either security or some other purpose. In the case of a hashtable, it is used to determine the index of the array.

* Buckets : a bucket is what is contained in each index of the array of the hashtable. Each index is a bucket. An index could potentially contain multiple key/value pairs if a collision occurs.

* Collisions : a collision is what happens when more than one key gets hashed to the same index.

## Why use Hashtables?

1. Hold unique values
2. Dictionary
3. Library

## What Are they
* Hashtables are a data structure that utilize key value pairs. This means every Node or Bucket has both a key, and a value.
* if we want to search for a value in array then we need to iterate n times to get the value.
* but if we know which index is the value then we get complexity of O(1).
* The hash table is based on array fast access.
## How it is Working
* each key passed to hash function.
* the hash function will return index where we should store the key and value pair.
* if we want to get the value of specific key then we pass that key to hash function and get the index then access that index in O(1).
* The collision occurs when more than one key hashed to the same index.
* Then we need to append each key,value pair to linked list in that index.


> To achieve a good hashing mechanism, It is important to have a good hash function with the following basic requirements:

1. Easy to compute: It should be easy to compute and must not become an algorithm in itself.
2. Uniform distribution: It should provide a uniform distribution across the hash table and should not result in clustering.
3. Less collisions: Collisions occur when pairs of elements are mapped to the same hash value. These should be avoided.

![Hash function](https://he-s3.s3.amazonaws.com/media/uploads/dda3e36.jpg) 



### References:
[Intro to Hash Tables](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-30/resources/Hashtables.html)
<br>
[what is a hash table?](https://www.youtube.com/watch?v=MfhjkfocRR0)
<br>
[basics of hash tables](https://www.hackerearth.com/practice/data-structures/hash-tables/basics-of-hash-tables/tutorial/)

