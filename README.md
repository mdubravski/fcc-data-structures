# Free Code Camp - Data Structure Course

Implements of data structures and their respective functions from Free Code Camp's Data Structures course.

## Notes

### Data Structure
A data strucute is a way of organizing data so that it can be used effectively.

* essential ingredients in creating fast and powerful algorithms
* they help to mange and organize data
* they make code cleaner and easier to understand

### Abstract Data Type
A Abstract Data Type (ADT) is an abstraction of a data structure which provides only the interface to which a data structure must adhere to.

The interface does not give any spicific details about how something should be implemented or in what programming language.
* essential ingredients in creating fast and powerful algorithms
* they help to mange and organize data
* they make code cleaner and easier to understand

### ADT VS DS
|Abstraction (ADT) | Implementation (DS) |
|------------------|---------------------|
| List             | Dynamic Array, LinkedList|
| Queue            | LinkedList based Queue, Array based Queue, Stack based Queue|
| Map              | Tree Map, Hash Map/Hash Table|
| Vehicle          | Glof Cart, Bicycle, Car|


### Computational Complexity Analysis
How much time does this algorithm need to finish? How much space does this algorithm need to finish?

#### Big O Notation
Big O notation gives an upper bound of the complexity in the worst case, helping to quantify performance as the input size becomes arbitrarily large.

#### Complexities ordered in from smallest to largest (n = size of the input)
|       Name       |     O(n)    |
|------------------|------------|
| Constant Time    | O(1)|
| Logarithmic Time | O(log(n))|
| Linear Time      | O(n)|
| Log-Linear Time  | O(nlog(n))|
| Quadratic Time   | O(n^2)|
| Cubic Time       | O(n^3)|
| Exponential Time | O(b^n)|
| Factorial Time   | O(!n)|

#### Big O Properties
We drop constant terms that wont effect growth as input become arbitrarily large.
We also drop slower growing terms.
##### Example 0
>`O(n + c) = O(n)`

>`O(cn) = O(n), c > 0`

##### Example 1
Let f be a function that describes the running time of a particular algorithm for an input of size `n`.

>`f(n) = 7log(n)^3 + 15n^2 + 2n^3`

>`O(f(n)) = O(n^3)`

##### Example 2

>The following run in constant time: `O(1)`

```
    a = 1
    b = 2
    c = a + 5* b
```
```
    while(i < 11){
        i = i + 1
    }
```

##### Example 3

>The following run in linear time: `O(n)`

```
    // fn(n) = n
    i = 0
    while(i < n){
        i = i + 1
    }
```
```
    // f(n) = n/3
    i = 0;
    while(i < 11){
        i = i + 3
    } 
```

##### Example 4

>The following run in quadratic time: `O(n^2)`

```
    // fn(n) = n*n = n^2
    for(i = 0; i < n; i++){
        for(j = 0; j < n; j++){
            // do something
        }
    }
```
```
    // fn(n) = n(n+1)/2 = n^2/2 + n/2
    for(i = 0; i < n; i++){
        for(j = i; j < n; j++){
            // do something
        }
    }
```

##### Example 5

>Suppose we have a sorted array and we want to find the index of a particualr value in the array, if it exists.
>What is the time complexity of the following alogrithm?

```
    // fn(n) = log2(n) = log(n)
    function(value){
        low = 0
        high= n-1
        while(low <= high){
            mid = (low+high) / 2
            if(array[mid] == value){
                return mid
            }else if(array[mid] < value){
                low = mid + 1
            }else if(array[mid] > value){
                high = mid - 1
            }
        }
        return -1 // value not found
    }
```
> O(f(n)) = O(log(n))

##### Example 6

```
    // f(n) = n * (3n + 2n) = 5n^2
    i = 0
    while(i < n){
        j = 0
        while(j < 3*n){
            j++
        }
        j = 0;
        while(j < 2*n){
            j++
        }
        i++
    }
```
> O(f(n)) = O(n^2)

##### Example 7

```
    // f(n) = 3n * (40 + (n^3)/2) = 3n/40 + (3n^4)/2
    i = 0
    while(i < 3*n){
        j = 10
        while(j < 50){
            j++;
        }
        j = 0;
        while(j < n*n*n){
            j = j + 2
        }
        i++
    }
```
> O(f(n)) = O(n^4)

##### Example 8
>Finding all subsets of a set = `O(2^n)`

>Finding all permutations of a string = `O(n!)`

>Sorting using mergesort = `O(nlog(n))`

>Iterating over all the cells in a matrix of size n by m = `O(nm)`

### Static and Dynamic Arrays

#### Static Arrays
A static array is a fixed length container ocntaining n elements indexable from the range [0, n-1].
Static arrays are given as contigious chunks of memory (all address adjecent). 

Used in:
* Storing and accessing sequential data
* Temporarily storing objects
* Used by IO routines as buffers
* Lookup tables and inverse lookup tables
* Can be used to return multiple values from a function
* Used in dynamic programming to cache answersw to subproblems

#### Dynamic Arrays
A dynamic array can grow and shrink in size.

A dynamic array can be implemented using a static array:
1. Create a static array with an inital capacity
2. Add elements to the underlying static array, keeping tack of the number of elements.
3. If adding another element will exceed the capacity, then create an new static array with twice the capacity and copy the original elements into it.

#### Complexity - Static Array vs Dynamic Array

|Function|Static Array|Dynamic Array|
|--------|------------|-------------|
|Access|O(1)|O(1)|
|Search|O(n)|O(n)|
|Insertion|N/A|O(n)|
|Appending|N/A|O(1)|
|Deletion|N/A|O(n)|

### Singly and Doubly Linked Lists
A linked list is a sequential list of nodes that hold data which point to other nodes also containing data. The head is the first node in a liked list. The tail is the last node in a linked list. A pointer is a reference to antoher node. A node is an object containing data and pointer(s).

Used in:
* Used in many List, Queue & Stack implementations
* Great for creating circular lists
* Can easily model real world objects such as trains
* Used in separate chaining, which is present in certain Hastable implementations to deal with hashing collisions
* Often used in the implementation of adjacency lists for graphs

#### Singly Linked List
A singly linked list only holds a reference to the next node. In the implementation you always maitian a referece to the head to the linked list and a reference to the tail node for quick additions/removals.


#### Doubly Linked List
With a doubly linked list each node holds a reference to a next and previous node. In the implementation you alwayts amintain a refenrece to the head and the tail of the doubly linked list to do quick additions/removals from both ends of your list.

#### Singly & Doubly Linked List Pros and Cons

|Type|Pros|Cons|
|--------|------------|-------------|
|Singly Linked List|Uses less memory, Simpler implemenation|Cannot easily access previous element|
|Doubly Linked List|Can be traversed bakcwards|Takes 2x memory|

#### Complexity - Singly Linked List vs Doubly Linked List

|Function|Singly Linked|Doubly Linked|
|--------|------------|-------------|
|Search|O(n)|O(n)|
|Insertion at head|O(1)|O(1)|
|Insertion at tail|O(1)|O(1)|
|Remove at head|O(1)|O(1)|
|Remove at tail|O(n)|O(1)|
|Remove in middle|O(n)|O(n)|





## Authors

Micahel Dubravski

## Acknowledgments

[Free Code Camp Data Structure Course](https://www.youtube.com/watch?v=RBSGKlAvoiM&t=3309s)
