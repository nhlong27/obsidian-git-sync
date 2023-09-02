## Array
- collection of elements or values, each identified by an index or a key -> random access because contiguous memory locations
- fixed size, homogeneous (same type)
--> List
- dynamic size, heterogeneous

Access: O(1)
Insert, delete: O(N)
## Linked List
- Elements are stored as nodes, where each node contains the value and a reference (pointer) to the next node in the sequence, no contiguous memory
- dynamic size, heterogeneous

Access: O(N)
Insert, delete: O(1)

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
## Hash map
- Key-value pairs. Collision.

Access, insert, delete: O(1)
## Tree
- Hierarchical, non-linear. Each node holds a value (or data) and references to its child nodes. Root (topmost, starting point), Leaf (node with no children), Depth (edges from root to node), Height (maximum depth).

Traverse: O(N) - DFS, BFS vs inorder, preorder, postorder traversal (binary )

- BST (left <=) (right >)
Access, insert, delete: O(h)
- Balanced tree: AVL, Red-black tree
Access, insert, delete: O(logN)
- Heap
Access max/min: O(1)
Insert, delete: O(logN)
- Trie
Access, insert, delete: O(m length of key)

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
## Graph
- Collection of nodes (also called vertices) and the connections between these nodes (edges). Degree (in-degree, out-degree), path, cycle, connectedness.

- Adjacency matrix
Access, insert, delete edge: O(1)
O(V^2) space
- Adjacency list
Access, delete: O(degree)
Insert: O(1)
O(V+E) space



