[#leetCode]
[Roadmap](https://roadmap.sh/javascript)

##  **The basics of all languages**
- ==Data structuration (variables, types) ==
|  complex structures (functions) . procedural --> OOP  
v
- ==Data manipulations (operations, logic, control flow)==
**Paradigms**
	imperative - instruct *how* to change states
		procedural
		object-oriented
	declarative - instruct *how* to change states by predefined logic, or *what* logic to use
		logical
		functional

We manipulate data to achieve a goal/change states -> We reach that goal/change states through operations/algorithms
One of the core manipulation patterns is 
	CRUD, Index, Search, Aggregate, Join (with data persistence)
	Real-time stream processing
	Machine learning tasks?
	Graphics related
![[Pasted image 20230416085253.png]]

OOP
	Encapsulation of data + logic in a data structure/object
	Abstract
	Hierarchy
	Polymorphism


## **Javascript**


Declarators for variables + Scopes
	var, let, const - redeclared, updated 
	block scope (curly braces - if, loop, while, class, func), function scope, module scope (var, let and const can have module scope, or global scope if not inside a module, in case of var become property of global object) *temporal dead zone*
	![[Pasted image 20230503082339.png]]
	, global scope: [define a global var](https://stackoverflow.com/questions/5786851/define-a-global-variable-in-a-javascript-function)
		```
		var a = 5 (outside module, let & const don't become properties of global object, but still global scope)
		a = 5 // implicit globals [not in strict mode](http://blog.niftysnippets.org/2008/03/horror-of-implicit-globals.html)
		window.a = 5 //browsers
		globalThis.a = 5 //all Javascript environments
		```
		BOM, DOM and Window Object [source](https://200lab.io/blog/tim-hieu-them-ve-window-object-trong-javascript/)
		![[Pasted image 20230502084055.png]]
		![[Pasted image 20230427091755.png]]
		![[Pasted image 20230427092259.png]]
		Avoid global variables by using module or scoping function
		![[Pasted image 20230427092651.png]]
		
	Lexical scope -> Closure
>In JavaScript, a closure is created when a function is defined inside another function, and the inner function has access to the outer function's variables, parameters, and even other inner functions. The scope chain of a closure includes not only the immediate outer function's variables and parameters, but also the variables and parameters of any functions that are in the chain between the inner function and the outermost function.
![[Pasted image 20230502084900.png]]
![[Pasted image 20230502090058.png]]
![[Pasted image 20230502084910.png]]
Hoisting (only with declarations, else "X is not defined") --> reference before declarations inside their respective scopes
	var - undefined
	let, const - ReferenceError
	![[Pasted image 20230502085647.png]]

Data Types
	Primitives: null (typeof === object), undefined, string, symbol, bigint, number, boolean
		Immutable
		Pass by value
	Objects: built-ins (.prototypes) (root: Object.prototype), constructors for built-ins (root: Function.prototype)  --- The purpose of prototype + constructors is to imitate OOP class
		Mutable
		Pass by reference
Type coercion
	no-coercion with === , !== 
	Between primitives
		"5" + 3 -> string // "53" 
		"5" * 3 -> number  // 15
		"5" == 5 -> number // true
	Between objects with primitives
	,
	Functions
		IIFEs
		Rest parameters
		Arguments object
		Function/call stack
		Built-in Functions, or object methods

Data structures
	Indexed Collections (arrays) 
	Keyed Collections (map, set, weakmap, weakset)

Operators ... (equality comparison)
Loops, Iterations, ... Control Flow
	... Exception Handling

Modules
	<script type='module' src=''></script>
	CommonJS (.cjs)
	ESModule (.mjs)
this
[in arrow function](https://stackoverflow.com/questions/66518020/javascript-this-keyword-and-arrow-function)
![[Pasted image 20230502090739.png]]
in Node.js, this usually refers to the module.exports object (undefined if strict mode). Use 'global' (nodejs) or 'window' (web browser) or 'globalThis' (both)

Asynchornous
	XMLHttpRequest (XHR) (callback-based)
	Fetch -> Axios (promise-based)
	Blocking vs Non-blocking 


The concept of 'first-class' objects
Why we don't use global state in Javascript
Regex global modifier
Array.slice -> shallow copy
Turing machine, deterministic vs nondeterministic
P vs NP
Math concepts in programming

Buffer - area of storage in memory that holds data until the the program is ready, buffer overflow
```
const buffer = Buffer.from('Hello, world!', 'utf8');
console.log(buffer); // Output: <Buffer 48 65 6c 6c 6f 2c 20 77 6f 72 6c 64 21>
console.log(buffer.toString('hex')); // Output: 48656c6c6f2c20776f726c6421

```
- Machine code - hex and binary, Assembly code are platform-specific
- Java compiler -> bytecode (independt of platforms) with JVM
- Hardware platforms vs Operating systems
- Python interpreter -> bytecode -> Python virtual machine
- Garbage collecting
- JSON and hashmaps (JS objects)
- JS pass by reference with object  -- C pass everything by value
- Return in JS higher order function == continue
***
## Note
```
newArray = [...oldArray, ...(condition ? [newMember] : []) ] // to get empty member if condition === false, instead of null or undefined
```

```
const map = new Map([['key', 1], ['value',1]])
for (let [k, v] of map){
  console.log(k, v)
}
map.forEach((v, k)=>{})
```