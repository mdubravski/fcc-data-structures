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
|       Name       |     O()    |
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
>`Example 0`

>`O(n + c) = O(n)`

>`O(cn) = O(n), c > 0`

Let f be a function that describes the running time of a particular algorithm for an input of size `n`.
>`Example 1`

>`f(n) = 7log(n)^3 + 15n^2 + 2n^3`

>`O(f(n)) = O(n^3)`

>`Example 2`

>`The following run in constant time: O(1)`

>`a = 1`
>`b = 2`
>`c = a + 5*b`

>`i = 0`
>`while(i < 11){i = i + 1}`

>`Example 3`

>`The following run in constant time: O(n)`

>`i = 0 while(i < n){i = i + 1;} (f(n) = n)`

>```
    i = 0;
    while(i < 11){
        i = i + 3
    } (f(n) = n/3)
 ```

## Authors

Micahel Dubravski

## Acknowledgments

[Free Code Camp Data Structure Course](https://www.youtube.com/watch?v=RBSGKlAvoiM&t=3309s)