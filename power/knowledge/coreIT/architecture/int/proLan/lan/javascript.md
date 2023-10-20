[#leetCode]
[Roadmap](https://roadmap.sh/javascript)

- purpose
	- DOM manipulation, event handling
	- Async: callback -> promise -> async/await
- properties
	- type
		- data
			- primitives (immutable, pass by value) null (typeof === object) vs undefined, string, symbol, bigint, number, boolean
			- objects (mutable, pass by reference) 
				- prototype vs ES6 class, built-ins (.prototypes) (root: Object.prototype), constructors for built-ins (root: Function.prototype)  --- The purpose of prototype + constructors is to imitate OOP class
				- this - refers to object, or global object in function ('window', 'global', 'globalThis') (note: arrow function, scope from parent)
					- ![[Pasted image 20230927162124.png]]
				- 
				- function
					- IIFEs
					- Rest parameters
					- Arguments object
					- Function/call stack
					- Built-in Functions, or object methods
					- Generator function* + yield, [...] ~ for ... of function()
				- array -> higher-order function (return using continue)
		- declarators
			- (var)
				- redeclare, reassign
				- scope: function, global/module
				- hoisted: undefined
			- let, const
				- redeclare / reassign
				- scope: block (function, curly braces), global/module
				- hoisted: referenceError (temporal dead zone)
			- function
				- closure: "In JavaScript, a closure is created when a function is defined inside another function, and the inner function has access to the outer function's variables, parameters, and even other inner functions. The scope chain of a closure includes not only the immediate outer function's variables and parameters, but also the variables and parameters of any functions that are in the chain between the inner function and the outermost function"
				- hoisted: output (only proper declarations) -> development speed, don't care order
			![[Pasted image 20230502085647.png]]

- features
	- async (callback, XMLHttpRequest - promise - async/await, fetch)
	- concurrency and parallelism
		- single-threaded
		- ![[Pasted image 20230628090157.png]]
		- multi-threaded - web workers
	- memory management
