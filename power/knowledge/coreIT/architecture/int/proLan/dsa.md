[#leetCode]
[Roadmap](https://roadmap.sh/computer-science)
[Data structures we use everyday](https://www.youtube.com/watch?v=ouipSd_5ivQ)

we manipulate data to achieve a goal/change states -> We reach that goal/change states through operations/algorithms


- algo - efficiently achieve a goal
	- dynamic programming: tabulation + iterative / bottom-up, memoization + recursive / top-down
	- sort 
	- ![[Pasted image 20230627175950.png]]



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


	![[Pasted image 20230504083953.png]]

 ```
function ListNode (val, next) {
  this.val = val ? val : 0;
  this.next = next ? next : null;
}

function LinkedList () {
  this.head = null;
  this.size = 0;
  
  this.insertAt = (idx, val) => {
    if (this.size-1<idx) return;
    const newNode = new ListNode(val)
    if (!this.head){
      this.head = newNode
      this.size++
    } else {
      let curr = this.head;
      while (idx > 0){
        curr=curr.next
        idx--;
      }
      newNode.next = curr.next;
      curr.next = newNode
      this.size++;
    }
  }
  
  this.traverse = () => {
    let curr = this.head;
    const arr = []
    while (curr){
      arr.push(curr.val)
      curr = curr.next
    }
    return arr
  }
  
  this.removeElements = function(head, val) {
    if (!head) return head;
    
    let curr = head, temp = head
    while (curr !== null){
        if (curr.val === val){
            if (head.val === val){
                head = head.next
                curr = head
                temp = head
            } else {
                temp.next = curr.next
                curr.next = null
                curr = temp.next
            }
        } else {
            temp = curr
            curr = curr.next
        }
    }
    return head
};
}

```

```

function TreeNode (val, left, right) {
  this.val = val ? val : 0;
  this.left = left ? left: null;
  this.right = right ? right: null;
}

function Tree () {
  this.root = null;
  
  this.BFS = () => {
    if (this.root === null) return;

    const queue = []; // Use an array as a queue
    queue.push(this.root);

    while (queue.length > 0) {
      const node = queue.shift();
      console.log(node.val);

      if (node.left !== null) queue.push(node.left);
      if (node.right !== null) queue.push(node.right);
    }
  }
  
  this.DFS=()=> {
    if (this.root === null) return;

    const stack = []; // Use an array as a stack
    stack.push(this.root);

    while (stack.length > 0) {
      const node = stack.pop();
      console.log(node.val);

      // Push right child first to process left child first (LIFO order)
      if (node.right !== null) stack.push(node.right);
      if (node.left !== null) stack.push(node.left);
    }
  }
  
}
```



