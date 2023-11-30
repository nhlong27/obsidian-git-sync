[#leetCode]
[Roadmap](https://roadmap.sh/computer-science)
[Data structures we use everyday](https://www.youtube.com/watch?v=ouipSd_5ivQ)


- algo - bigO breakpoints
	- dynamic programming: tabulation + iterative / bottom-up, memoization + recursive / top-down
	- sort 
- datStr: container of data - for efficient access and modification of data - https://stackoverflow.com/questions/75734006/are-all-data-structures-implemented-with-arrays-and-linked-structures array -> linked list -> graph, tree -> stack, queue -> hash table -> OOP -> advanced 
	- array  -> list: fixed, constant access (matrix, weather app, image processing)
		- collection of elements or values, each identified by an index or a key -> random access because contiguous memory locations
		- fixed size, homogeneous (same type)
		- access: O(1) - insert, delete: O(N)
	- linked list: frequent insert, delete (social media feeds, task management, shopping carts)
		- elements are stored as nodes, where each node contains the value and a reference (pointer) to the next node in the sequence, no contiguous memory
		- dynamic size, heterogeneous
		- access: O(N) - insert, delete: O(1)
	- stack, queue: undo, redo (text editor, browser history) (chat app, queue job)
		- stack - push(), pop() or concat(), slice(0, -1), length (for immutable React, note that slice only shallow copies)
		- queue - push(), shift() or concat(), slice(1), length
	- hash map (search engine, caching system, interpreter/compiler) - hash map load factor
		- key-value pairs. collision.
		- access, insert, delete: O(1)
	- tree: hierarchy (comments)
		- hierarchical, non-linear. Each node holds a value (or data) and references to its child nodes. Root (topmost, starting point), Leaf (node with no children), Depth (edges from root to node), Height (maximum depth).
		- traverse: O(N) - DFS, BFS vs inorder, preorder, postorder traversal (binary ) 
		- types
			- BST (left <=) (right >)  - access, insert, delete: O(h) |
			- balanced tree: AVL, Red-black tree - access, insert, delete: O(logN)
			- heap: (task scheduling, memory management) - access max/min: O(1) - insert, delete: O(logN)
			- trie - access, insert, delete: O(m length of key)
			- r tree: nearest neighbor (mapping/geolocation)
			- B, B+ tree: (database index)
			- suffix tree: (text editor)
	- graph: relationship (social network, recommendation engine, path finding algo)
		- collection of nodes (also called vertices) and the connections between these nodes (edges). Degree (in-degree, out-degree), path, cycle, connectedness.
		- implementations
			- adjacency matrix - access, insert, delete edge: O(1), space O(V^2) 
			- adjacency list - access, delete: O(degree) - insert: O(1), space O(V+E)
	- class: oop - reusability + maintainability (in developing context, not performance context)
		- constructor (1 only) - class fields
		- public vs private # (not in prototype inheritance)
		- static - fixed configs
		- extends, super
		- this (can't work with static properties, cause no instance)

