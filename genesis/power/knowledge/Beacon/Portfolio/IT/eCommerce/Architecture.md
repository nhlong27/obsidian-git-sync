[#ecommerce, #portfolio]

![[portfolio_IT.excalidraw]]

![[Pasted image 20230629122412.png]]


- services: service discovery, inter-service communication, data persistence, error handling, and security
	- Order service --> message queue (vs promise: asynchronous operations - a/synchronous processing)
		- product, quantity, customer info
		- inventory, catalog, order, user, payment 
	- Payment Service -> Webhook (persistence callback) vs polling -> PSP
		- Event: Payment status + Payment details
		- <-> Wallet
		- <-> Ledger -> reconciliate financial transactions with bank statements 
	- Payment Service Provider (PSP) 
		- *provided*: Checkout: Order summary, Shipping/Billing info, Payment method, Payment details, 
		- Payment Gateway -> PCI, DSS - Risk check/ Fraud prevention
		- Payment Processor <-> Acquiring Bank <--> Card Schemes <--> Issuing Bank
		- ![[Pasted image 20230708134057.png]]
	- Catalog service
		- elastic stack
- fe
	- rendering - routing: next, tailwind
	- state management
		- redux, jotai, react-query*
- be
	- api
		- engine/server: apollo (graphql)
		- auth: next-auth
	- dbs
		- cache: redis
		- postgresql (prisma)
		- mongodb (mongoose)
		- storage options
- dependencies
	- style
		- class-variance-authority, react-wrap-balancer, clsx, tailwind-merge
	- event
		- nodemailer

### Design
Home
	Nav - **Links**
		SearchBar - search by keyword/ tags [1]
		Home 
		Products -> Categories [1]
		Cart [2]
		Profile [4] -> Seller Profile [4.1] Dropdown (Account, Cart, Seller Profile/Buyer Profile, Sign Out) / Sign in/Sign up [2]  
	Body
		Trending - Swiper
		Categories
		Products Preview + 3
			Slideshow [...Products]
				Backdrop
				Small cards [3]
					Images + Title + Description
					Price
					Solds
					Location
		Recommended
			[...Products]
	Footer 
		About
		Payment method
		Follow
			Links to Facebook, Instagram, LinkedIn
			Address, Phone
		Copyrighted
[...Products]
	Card 
		Tabbed category (Note: in the product data itself)
		Sku + Title + Categories + Price + Instock +  pkg Size + case Quantity + Images + Score (*/5*) + Reviews 
		Report action + Favorite action
		Transport/Delivery 
			Address
			Delivery fee (function)
		Amount (available products)
		Add to cart
	Store Display
		Image + Name
		Visit + Favorite action
		Reviews + Products + Joined Date + Followers
	Details
		Tabbed category
		--Others
	Description
		description prompt
		product includes
		how to use
		warranty
		note
		tags		
	Reviews (Paginated)
		Score + All, 5(number), 4, 3, 2, 1(number) 
	Similar products (See more)
		Lists
		Link to Explore page
Explore [1] /explore/:category#tags
	Filters
		Categories
		Locations 2
		*Delivery Type*
		Price range
		Reviews range
		Following shops
		Reset action
	Product List (Paginated)
		Tabbed category
		Filtered by popular, new, most sales
		Small cards [3]
Auth page [2] ./auth
	Backdrop
	Sign in/Multi-step Sign up form + OAuth
	(Multi-step Sign up to be Seller)
		Store information - Name, Address, Email, Phone
		Delivery type
		Add a product
Buyer Profile [4] /user
	Sidebar
		Profile info /profile - Edit action* Username (random), Name, Email, Phone number, Gender, Birthday, Avatar (default)
		Seller Profile [4.1]
		Cart /cart - All, Delivering, Canceled, Completed, Refund ..?
	Main content
		Cart* Search bar for products	
Seller Profile [4.1] /user/seller
	Sidebar
		Store info /store - Edit action* Name, Address, Email, Phone, Delivery type , Avatar (default), 
		Buyer Profile [4]
		Product list - In Store
		Order
	Main content
		In Store* Search bar for products, Categories
		Order	


### In-depth
- FE
	- State mgmt
		- Redux
			- https://www.youtube.com/watch?v=8tZtm-znc9A
	- Routing-Rendering
		- Tailwind + Headless UI
		- Next SSG, SSR, ISR
			- https://www.reddit.com/r/nextjs/comments/11vh5wn/comment/jct61qw/?utm_source=share&utm_medium=web2x&context=3
	- Async Handling
		- React-query SSR
		- Suspense, Error checking
			- CSR
				- Suspense (react-query-isLoading or state) + ErrorBoundary ((react-query-error or try/catch + setState or componentDidCatch) + moving up the ancestry)
			- SSR
				- cannot use Suspense & ErrorBoundary because no state 
				- moving error handling to server (try/catch)
				- keep suspense handling on client (for a whole page where ssr occurs)
				- https://daveinside.com/blog/handling-runtime-errors-when-server-side-rendering-with-nextjs
				- https://stackoverflow.com/questions/72875632/nextjs-server-side-rendering-error-handle
- BE
	- API
		- Next api as a server -> serverless functions on Vercel
			- https://www.youtube.com/watch?v=2cB5Fh46Vi4&t=200s
			- https://stackoverflow.com/questions/62690747/next-js-api-is-back-end
			- https://stackoverflow.com/questions/74621518/how-to-get-api-call-origin-in-nextjs-api-endpoint
			 - ![[Pasted image 20230531113618.png]]
			 - ![[Pasted image 20230531120335.png]]
			- Other host?
				- https://stackoverflow.com/questions/69469350/next-js-api-on-same-server
				- https://stackoverflow.com/questions/71551510/is-it-possible-to-have-a-separate-backend-for-next-js-application
		- GraphQL : Apollo resovler gateway
			- https://github.com/TanStack/query/discussions/3448
			- https://stackoverflow.com/questions/74063463/how-do-i-wait-for-next-auth-session-before-using-usequery
			- https://www.reddit.com/r/reactjs/comments/oqx5me/apollo_client_vs_reactquery_help_me_choose_do_i/ - apollo client has normalized caching
			- another option https://www.youtube.com/watch?v=wRRO9915Lbc
			- mutation error https://stackoverflow.com/questions/74064124/react-query-usemutation-no-overload-matches-this-call
			- thunder client https://www.katk.dev/thunder-client
			- runtime typechecking? --> "Yolo"
	- Runtime Env
		- Prisma
		- Mongoose
	- Databases
		- PostgreSQL
		- Mongodb 
			- https://stackoverflow.com/questions/62440264/mongoose-nextjs-model-is-not-defined-cannot-overwrite-model-once-compiled  --> https://devdojo.com/amp/usmanwrites/how-to-use-mongoose-with-nextjs-for-mongodb
			- Tier
				- 1: load straight from csv
				- 2: load from kafka - zookeper https://www.youtube.com/watch?v=heR3I3Wxgro
		- Redis
			-  https://stackoverflow.com/questions/71538821/typescript-type-error-while-using-redis-type
			- remove upon mutation
	 - Services
		- Next Auth 
			- JWT verification: middleware vs api routes vs getServerSideProps (getServerSession, getToken) 
			- https://stackoverflow.com/questions/73982523/nextauth-selecting-a-different-google-account-for-login
			- https://stackoverflow.com/questions/74089665/next-auth-credentials-provider-authorize-type-error
			- https://stackoverflow.com/questions/69234170/difference-between-usesession-and-getsession-in-next-auth
			- https://github.com/nextauthjs/next-auth/issues/693
			- https://www.youtube.com/watch?v=yCJH72nZ8DI&list=WL&index=4&t=446s
			- https://remaster.com/blog/next-auth-jwt-session
			- https://authjs.dev/guides/basics/refresh-token-rotation
			- https://next-auth.js.org/getting-started/client
			- https://authjs.dev/guides/basics/pages
			- https://next-auth.js.org/tutorials/securing-pages-and-api-routes
			- https://www.youtube.com/watch?v=VP-RCddbjrc
			- https://www.oauth.com/oauth2-servers/access-tokens/access-token-response/
			- https://www.youtube.com/watch?v=RJpevpbC4YY
		