- mobile
	- native: objective-c/Swift, java/kotlin
	- cross: react native, flutter, xamarin
	- pwa
- desktop
	- electron framework: chromium rendering engine + node (V8 engine)
	- native Wins app: GUI libaries/frameworks WinForms + (compiled) machine code
- user agent/ browser: build & interpreting tool with a GUI (links = executable files) 
	- type
		- chrome: chromium rendering engine (blink) + V8 engine
		- firefox: gecko + spidermonkey
		- safari: Webkit + (webkit) JavascriptCore
	- api: BOM and DOM https://stackoverflow.com/questions/29991742/do-compilers-for-javascript-differ-from-web-browser-to-web-browser javascript compiled -> minified js /bytecode --> (JIT compilers- machine code or runtime interpreters/VMs)  https://stackoverflow.com/questions/62239611/why-does-javascript-get-compiled-to-machine-code, DOM is tree-like visual representational API to access the data structure constructed from parsed HTML and CSS https://qr.ae/pyEliP
	- language - javascript
		- ajax (callbacks). 3 ways: browser as terminal (php), dom manipulation (jquery), html/js abstraction with callback - promise - async/await 
	- libFra
		- react - simply a library (doesn't need node to run)
			- goal: 
				- component-based and declarative UI
					- jsx component (object, function-based syntax)
					- ![[Pasted image 20230807083837.png]]
					- ![[Pasted image 20230807085430.png]]
				- efficient DOM manipulation, performance optimization
					- DOM <- updates - VDOM reconciliation (diffing algo) + keys + batch updates
				- consistency
					- unidirectional data flow, one-way data binding (state -> ui/model->view). E.g. uncontrolled (dom state) vs controlled component (react *parent* component internal state) https://stackoverflow.com/questions/32712605/is-reacts-data-binding-really-one-way-it-seems-like-it-is-two-way
		- next
			- goal
				- react component-based architecture + spa reactivity + document era ssr (SEO)
					- build time: generate static html, code splitting, ... getStaticProps
					- run time: Link client side routing, fetch html or getServerProps
					- ![[Pasted image 20230902105909.png]] (for every page)
			- properties
				- https://www.youtube.com/watch?v=XwswPqIXYoI
				- CSR
					- Suspense (react-query-isLoading or state) + ErrorBoundary ((react-query-error or try/catch + setState or componentDidCatch) + moving up the ancestry)
				- SSR
					- cannot use Suspense & ErrorBoundary because no state 
					- moving error handling to server (try/catch)
					- keep suspense handling on client (for a whole page where ssr occurs)
					- https://daveinside.com/blog/handling-runtime-errors-when-server-side-rendering-with-nextjs
					- https://stackoverflow.com/questions/72875632/nextjs-server-side-rendering-error-handle