[#leetCode]
[Roadmap](https://roadmap.sh/computer-science)
[Data structures we use everyday](https://www.youtube.com/watch?v=ouipSd_5ivQ)
## ***Data structures***
Container of data - for efficient access and modification of data
				
	Primitive
		String
> The spread operator is a feature introduced in ES6 that allows an iterable (such as an array or a string) to be expanded into individual elements. In this case, the spread operator is used to create a new array `arr` from the characters of the string 
> 	Numeral Systems 
> 		Base 2/10/16/64
> 		Floating point

	Non-primitive
		Indexed Collections: 
		Array (homogeneous)
			dynamically O(1) append
> Thus, arrays can be very useful when dealing with a large collection of homogeneous data types. Since Python does not have to remember the data type details of each element individually; for some uses, arrays may be faster and uses less memory when compared to lists.

		List (heterogeneous)
			Linear
				Linked list
			Non-linear ?
		Meta data structures
			*Stack* 
			*Queue*
			Graph
				Tree - Binary Tree. (Focus on the data)
					BST
						retrieve, insert, delete. Red black tree maintains O(H = logN). Create O(NlogN)
					Heap/Priority Queue
						insert, delete O(logN), retrieve O(N) unless highest priority O(1). Create O(NlogN) -> O(N)
				Other graph (Focus on the relationships)
		Keyed Collections:
		Hash map (hash function + array)
			retrieve, insert, delete O(1). Memory-intensive
 Container of behaviors
	Class


> 1.  When order matters: Hash maps do not maintain any specific order of elements, and iterating over them in order can be inefficient. In such cases, a linked list, a queue, or a priority queue may be a better choice.
	2.  When there are duplicates: Hash maps do not allow duplicates. If you need to store multiple copies of an element, you would need to use a different data structure such as a list or a set. 
	3.  When memory is a concern: Hash maps can be memory-intensive due to the need for additional memory to store hash codes and pointers. In cases where memory is limited, a compact data structure such as a bitset or a bitmap may be a better choice.
	4.  When the keys are not hashable: Hash maps require that keys are hashable, which means that they must have a unique hash code that can be used to index into the hash table. If your keys are not hashable, you may need to use a different data structure such as a tree or a linked list.
	5.  When the size of the data is small: For small amounts of data, the overhead of setting up a hash table may outweigh the benefits of using a hash map. In such cases, a simple array or a list may be sufficient and more efficient.


## **Algorithms**
How to efficiently achieve a goal

**BigO**
1, logN, N, NlogN, N^2, 2^N, N!, ...
logN -> Sorting algorithms: cap NlogN (except Radix and Counting Sorts)

**Discrete** Math
Boolean Algebra
Set Theory
Combinatorics
	Graph Theory

## **Sorting** 
Insertion Sort (better for smaller data sets)
	swap & comparison
	n*(n-1)/2 --> O(n2)
	```
	for i:1 to length(A)-1
		j=i
		while j>0 and A[j-1] > A[j]
			swap A[j-1] and A[j]
			j=j-1
	```

## **Real World Javascript**
![[Pasted image 20230502163611.png]]

**Map** for caching (fast data retrieval based on unique identifier ) (messages with name)
	new Map([ [...] ]), has(), set(), get(), delete(), size, forEach(), for n of keys(), values(), self 
	keys: primitive, object, function
	ordered, iterable
**Set** for filtering selected options, or checking if exists (forms, checkboxes) (only shallow checks)
	new Set([...]), add(), has(), clear(), delete(), size, forEach(), for n of .values(), keys(), self   
	ordered, iterable
**Stack** for undo, redo actions (history stack)
	[...], push(), pop() or concat(), slice(0, -1), length (for immutable React, note that slice only shallow copies)
**Queue** for queued actions (messages, notifications)
	[...], push(), shift() or concat(), slice(1), length
**Tree** for nested menu items, comments
	nested object { ..., children: [...] }, or flat array [ { id: ,...,, children: [ ids ], isRoot? } ]
	
**Linked list** vs array
	- insert, delete: better than dynamic array (since create new array)
	append, prepend, insert 
	- retrieve (->update) 
		by index (array better) 
		by value: same
	- length
**Class**
	- constructor (1 only) - class fields
	- public vs private # (not in prototype inheritance)
	- static - fixed configs
	- extends, super
	- this (can't work with static properties, cause no instance)
	![[Pasted image 20230504083953.png]]