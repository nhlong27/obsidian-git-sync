[#index]
[#highlevel]
[Roadmap](https://roadmap.sh/software-design-architecture)
[Roadmap2](https://roadmap.sh/computer-science)
[Roadmap3](https://roadmap.sh/system-design)


Monorepo
	Yarn Workspaces, Lerna, Turborepo



**Production environment**
**Abstraction vs Coupling**


Common mistakes
- length && (unless undefined, null, false -> 0 will be rendered)
- eventHandler accepst function: onClick = {handleClick} <-handleClick (e)
- useState [state, setState] -> state references the state, setState tells React to rerender with new object (keeps state immutable), state references new object at next rerender. setState(prev=>) prev references the actual state (meanwhile  state may only reference the old state object )

GraphQL - '*extra REST*' more complex, flexible, multiple teams
>The resolver function is responsible for returning the requested data for the corresponding field. It can retrieve data from a database, call a third-party API, or perform any other necessary operations to resolve the field. The resolver function then returns the data, which is combined with the data from other resolved fields to generate the final response. Once all the fields in the query have been resolved, the server generates a response object in JSON format and sends it back to the client. The response object contains the requested data in the `data` field, as well as any errors that may have occurred during the query execution in the `errors` field. Resolvers also act as mutation functions

```
mutation { createUser(input: {name: "John Doe", email: "john.doe@example.com"}) { id name email } }
```

tRPC - '*simpler REST*'
a single API endpoint that operates behind your api engine
>In this setup, tRPC acts as a middleware that processes requests and responses between the client and server. It provides a type-safe and efficient way to define and communicate with APIs, while also leveraging the power of TypeScript to ensure type safety and prevent common runtime errors.
```
const booksRouter = createRouter() 
.query("allBooks", { input: {}, async resolve() { const books: Book[] = await getBooksFromDatabase(); return books; }, }) 
.mutation("addBook", 
{ input: { title: z.string(), author: z.string(), year: z.number(), },
async resolve({ input }) { const newBook: Book = { id: getNextBookId(), // assume this function returns the next available book ID title: input.title, author: input.author, year: input.year, }; await addBookToDatabase(newBook); // assume this function adds the new book to the database return newBook; }, });
```
```
import { TRPCClient } from "@trpc/client"; import { httpLink } from "@trpc/client/links/httpLink"; 

const client = new TRPCClient({ links: [httpLink({ url: "/books" })], }); 

async function addNewBook() { 
const newBook = await client.mutation("addBook", { title: "The Hitchhiker's Guide to the Galaxy", author: "Douglas Adams", year: 1979, }); console.log("Added new book:", newBook); } 

addNewBook();
```

Express 
API engine as it provides a simple and flexible way to build APIs using HTTP utility methods and middleware functions.

