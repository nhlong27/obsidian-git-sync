[#patterns]

**Composition over Inheritance**

>Inheritance is a powerful mechanism for creating reusable code, but it can also lead to tightly coupled, hard-to-maintain code. This is because inherited classes are tightly bound to their parent classes and any changes made to the parent class will affect all of its child classes. This makes it hard to change or extend the code without affecting the entire class hierarchy.


**Encapsulation Principle **
- Greater control
- More flexible code
	The Facade, Proxy, Adapter patterns
> Encapsulating what varies allows for . When changes are needed, they can be made to the encapsulated parts without affecting the rest of the code.

**Abstraction Principle**
- Reduce duplication
- (Other meaning - OOP Abstraction): Simplicity from complexity

**Naming**
	Prefix Action Context (Adjectives and Nouns)

## **Best Practices**
- Javascript
	- Avoid blobal variables
		- Problems: performance issues, name collisions, harder to maintain (overwrite)
		- Solutions: IIFEs, namespacing, dependency injection, *modules*
		![[Pasted image 20230504121130.png]]
		https://stackoverflow.com/questions/24295163/nodejs-and-implicit-global-variables
- Versioning
	- https://git-scm.com/book/en/v2/Git-Basics-Tagging
	- https://www.gitkraken.com/gitkon/semantic-versioning-git-tags
	- Commits vs Tags vs Releases (or Pre-releases) with Git
	- Pre-release versions: Alpha vs Beta
	![[Pasted image 20230504141303.png]]
	![[Pasted image 20230504141915.png]]
	![[Pasted image 20230504141827.png]]
	- SemVer
		- ![[Pasted image 20230504133611.png]]
		- ![[Pasted image 20230504133633.png]]
	- CalVer
		- External factors (e.g. marketing)
	- (Web) Apps: depends SemVer or CalVer https://frontside.com/blog/2022-02-09-semver-or-calver-by-project-type/
