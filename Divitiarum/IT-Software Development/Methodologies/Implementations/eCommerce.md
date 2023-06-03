
### eCommerceApp

routing =/= ajax 
Testing
FE
	Tailwind + Headless UI
	Redux
	Next SSG, SSR, ISR
		https://www.reddit.com/r/nextjs/comments/11vh5wn/comment/jct61qw/?utm_source=share&utm_medium=web2x&context=3
- BE
	Next api as a server -> serverless functions on Vercel
		https://www.youtube.com/watch?v=2cB5Fh46Vi4&t=200s
		https://stackoverflow.com/questions/62690747/next-js-api-is-back-end
		https://stackoverflow.com/questions/74621518/how-to-get-api-call-origin-in-nextjs-api-endpoint
		![[Pasted image 20230531113618.png]]
		Other host?
			https://stackoverflow.com/questions/69469350/next-js-api-on-same-server
			https://stackoverflow.com/questions/71551510/is-it-possible-to-have-a-separate-backend-for-next-js-application
	Prisma, Mongodb, + Redis (json for redis)
	- Next Auth 
		https://stackoverflow.com/questions/73982523/nextauth-selecting-a-different-google-account-for-login
		https://stackoverflow.com/questions/74089665/next-auth-credentials-provider-authorize-type-error
		https://stackoverflow.com/questions/69234170/difference-between-usesession-and-getsession-in-next-auth
		https://github.com/nextauthjs/next-auth/issues/693
		https://www.youtube.com/watch?v=yCJH72nZ8DI&list=WL&index=4&t=446s
		https://remaster.com/blog/next-auth-jwt-session
		https://authjs.dev/guides/basics/refresh-token-rotation
		https://next-auth.js.org/getting-started/client
		https://authjs.dev/guides/basics/pages
		https://next-auth.js.org/tutorials/securing-pages-and-api-routes
		https://www.youtube.com/watch?v=VP-RCddbjrc
		https://www.oauth.com/oauth2-servers/access-tokens/access-token-response/
		
		- Deployment 
			- Providers: facebook (unknown problem), github (change later), google (unknown problem) 
			- Prisma vercel -> postgresql - adapters (to persist )?
				- https://www.prisma.io/docs/guides/deployment/deployment-guides/deploying-to-vercel
		- JWT verification: middleware vs api routes vs getServerSideProps (getServerSession, getToken) 
		- Client: sign up (credentials?, providers) + sign up as admin?  
	Microservices (grpc/http-json)
		https://softwareengineering.stackexchange.com/questions/436567/what-is-the-best-practice-about-microservice-architecture-for-consuming-many-sto
		![[Pasted image 20230531120335.png]]
		Payment services - Stripe
		Buyer service
		Seller service
API
	Zod + React Query + GraphQL 
		https://github.com/TanStack/query/discussions/3448
		GraphQL Resolver gateway
	Suspense, Error handling
		CSR
			Suspense (react-query-isLoading or state) + ErrorBoundary ((react-query-error or try/catch + setState or componentDidCatch) + moving up the ancestry)
		SSR
			cannot use Suspense & ErrorBoundary because no state 
			moving error handling to server (try/catch)
			keep suspense handling on client (for a whole page where ssr occurs)
			https://daveinside.com/blog/handling-runtime-errors-when-server-side-rendering-with-nextjs
			https://stackoverflow.com/questions/72875632/nextjs-server-side-rendering-error-handle

Static assets with ssr https://stackoverflow.com/questions/54436021/nextjs-public-folder

Data (isn't important)
	Beer
		He
	Soft Drinks
	Others
		Water

Nextjs + Web scraping?
GraphQL, Next auth, OAuth
https://www.youtube.com/watch?v=XwswPqIXYoI

### Next JS
document era && ssr + react composition + spa (2 reasons: UX & SRP)
UX - performance vs dynamic content
> Once the initial page is loaded, subsequent interactions or navigation on the client side trigger client-side rendering, where the client-side JavaScript takes over and handles subsequent rendering and data fetching. This is when `getServerSideProps` is called on subsequent requests, fetching the data from the server and updating the page dynamically without a full page reload. (returns the whole page including JS === client side rendering)

getStaticProps
-   When the data is unlikely to change frequently.
-   When you want to pre-render pages with the same data for all users.
-   When you want to optimize performance by serving cached HTML pages.
getServerSideProps
-   When the data needs to be fetched at request time and can vary per request.
-   When you require access to server-side resources or APIs.
-   When the data is frequently changing or is user-specific.

Core of ecommerce
- Core of what I want to learn
- Physical vs Logical Architecture
	- FE
		- Nextjs, Redux 
	- BE & API
		- GraphQL, OAuth
		- DB
			- SQL.., Prisma?

https://stackoverflow.com/questions/59159553/why-cant-react-project-name-contain-capital-letters
	
Wordpress, Strapi, headless CMS Strapi, Shopify
Stripe

**Methods
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
			Images + Videos
			Title + Score (*/5*) + Reviews + Solds + Report action + Favorite action
			tags
			Price 
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
		
Notes
	Tab
	AutoComplete
	Filter keywords
Architecture
	3 Tier +
		UI
			Nextjs - React - Typescript
			TailwindCSS
			React query
		Backend & API
			Nodejs
			ExpressJS + RestAPI - trpc
			Next Auth
		Database
			SQL
			FaunaDB?
		Others
			Stripe (Payment) 
			headless CMS? Strapi Contentful Deity
			FormBucket?
	Structure
		Rendering
		Routing
		State management
Development pipeline
