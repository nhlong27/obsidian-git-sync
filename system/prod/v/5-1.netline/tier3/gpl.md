|            | paradigm | typed           | memory mgmt        | concurrency                  | implementation                                                                                   |
| ---------- | -------- | --------------- | ------------------ | ---------------------------- | ------------------------------------------------------------------------------------------------ |
| typescript | multi    | dynamic/weakly  | garbage collection | single-threaded non-blocking | js interpreter                                                                                   |
| java       | multi    | static/strongly | garbage collection | multi-threaded               | sdk (compiler + jre (libraries + jvm (intepreter - [jit](https://qr.ae/pyEXXg))))                |
| python     | multi    | dynamic/weakly  | garbage collection | multi-threaded               | [both](https://stackoverflow.com/questions/6889747/is-python-interpreted-or-compiled-or-bothis ) |
| go         | multi    | static/strongly | garbage collection | multi-threaded               | compiler                                                                                         |
| rust       | multi    | static/strongly | manual             | multi-threaded               | compiler                                                                                         |

- javascript - single threaded, garbage collection, dynamic/weakly typed, multi-paradigm
	- variables
		- (var)
			- redeclare, reassign
			- scope: function, global/module
			- hoisted: undefined
		- let, const
			- redeclare / reassign
			- scope: block (function, curly braces), global/module
			- hoisted: referenceError (temporal dead zone)
	- data types
		- primitives (immutable, pass by value) null (typeof === object) vs undefined, string, symbol, bigint, number, boolean
		- objects (mutable, pass by address) 
			- prototype (ES6 class syntax), Object.prototype --> built-ins ([Array](https://stackoverflow.com/questions/500504/why-is-using-for-in-for-array-iteration-a-bad-idea) / String / etc. / Function.prototype --> functions, Foo constructor + Foo.prototype) 
				- function
					- [apply(), call(), bind()](https://medium.com/@omergoldberg/javascript-call-apply-and-bind-e5c27301f7bb) - function methods to point *this* context to a object 
					- closure - function is defined within another function, and the inner function has access to variables or functions from the outer (enclosing) function's scope
			- this - refers to object, or global object in function ('window', 'global', 'globalThis') (note: arrow function, scope from parent)
	- + web api, event loop
		- async (callback, XMLHttpRequest - promise - async/await, fetch)
		- event (CustomEvent (name, event obj) -> dispatchEvent)
	- ts
		- type
			- primitive: boolean, string, number, null, undefined, void
			- other: unknown, any, never
			- object: index signature, interface, enum, array, tuple, function
				- [class](https://stackoverflow.com/questions/70364964/difference-in-typescript-between-types-instancetypetypeof-myclass-and-myc) (modifiers (public, protected, private), static, readonly, abstract - extends, interface - implements)
		- narrowing/creation: instanceof, typeof, keyof, type alias, union, intersection, extends, implements, [declare](https://stackoverflow.com/questions/43335962/purpose-of-declare-keyword-in-typescript)
		- generic, decorator
		- utility: partial, pick, omit, readonly, record, exclude, extract, nonnullable, parameters, returntype, instancetype, awaited
- python
	- variables & datatypes: (objects) int, float, complex, str, bool, NoneType, list, tuple, dict, set, forzenSet, binary types
- java
	- variables
		- [hoist](https://stackoverflow.com/questions/56524796/why-is-a-method-available-in-java-before-its-declaration)
	- data types
		- primitives: byte, short, int, long, float, double), char, boolean
		- [complex](https://www.javatpoint.com/non-primitive-data-types-in-java): String (literal vs object), Array, Object, Class, Interface