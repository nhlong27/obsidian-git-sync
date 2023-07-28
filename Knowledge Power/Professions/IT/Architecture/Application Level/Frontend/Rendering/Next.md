
https://www.youtube.com/watch?v=XwswPqIXYoI
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
