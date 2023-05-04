
Media Queries term
Xs 500
Sm 640
Md 768
Lg 1024
Xl 1280
4k 2560

| Fix                                        | Feat                                 |
| ------------------------------------------ | ------------------------------------ |
| [x] make dropdown menu sticky              | [ ] add dark theme                   |
| [x] export default prop drilling           | [ ] add code splitting               |
| [x] make play media send 'watching' status | [ ] add UI handling                  |
| [x] allow fullscreen (media page)          | [x] migrate to infinite query        |
| [x] make media list responsive             | [ ] add skeletons                    |
| [x] refactor the media card                | [x] add media pages (responsive)     |
| [x] refactor home page responsiveness      | [x] finish home page (responsive)    |
|                                            | [x] finish profile page (responsive) |
|                                            | [x] finish auth page (responsive)    |

profilePage 2h
	[x] auth paths - scuffed
	[x] default Avatar
	[x] showcontainer + date Updated
	[x] search title
	[x] better looking option list
	[x] mobile responsive - toggle userInfo
	[x] continue watching list in home page
authPage
	[x] basic form
	page
		modal card reflective
		video background 
errorPage

infiniteQuery
	loader
	skeleton

react query
	inactive vs stale
	[react query w/ react error boundary](https://github.com/TanStack/query/discussions/3393)
	[removeQueries vs invalidateQueries](https://github.com/TanStack/query/discussions/3169)
- the problem: react router (outside of Outlet) doesn't work with react error boundary (+ react query) (even with forced rerender, works inside Outlet for unknown reason)
 the solution: hard refresh
	navigate(0)
	Route + key
```
<Route path={YOURPATH} render={(props) => <YourComp {...props} keyProp={someValue} key={randomGen()}/>} />
```
- the problem: protected routes of auth and profile (url guard =/= link guard)
the solution: make Auth page a fallback of Profile page with Wrapper (Error Boundary)

Why refs { playRef} and funcs { func} work but ref and func don't?

Resources
https://api.quotable.io/random

https://www.facebook.com/groups/hoidesignlearn1/permalink/1966461747019828/

https://www.facebook.com/plugins/post.php?href=https%3A%2F%2Fwww.facebook.com%2Fd3design1%2Fposts%2Fpfbid0VkZG1sDdNqZ3mfZQbQTqUefdCVScv6jjsr6MxP72pBsKtpeYW7yRAq9Ev5gq6hynl&show_text=true&width=500

https://www.facebook.com/groups/2065849506971669/permalink/3447107652179174/

https://www.facebook.com/rgb.vn/posts/pfbid02LYC2UzQDS4jaMUCcKExnL7sUZdYcg2PSzQkorPPMHju4JwQAq2CstaSrDQV7vPUUl

signupform https://www.youtube.com/watch?v=jMVhxBB3l0w
glitch https://www.youtube.com/watch?v=FHsYlL88HrI&list=PL72krCXbZJcIkEEh1OG4bSp0auQbDVOKf&index=30

### **Other projects**

Plant Encyclopedia
Diet Guide

https://www.reddit.com/r/learnprogramming/comments/xvp7dz/comment/ir299f9/?utm_source=share&utm_medium=web2x&context=3

https://www.reddit.com/r/nhentai/comments/x0u31u/comment/ima4vl1/?utm_source=share&utm_medium=web2x&context=3

https://www.reddit.com/r/nhentai/comments/119ibvp/comment/j9pv7a7/?utm_source=share&utm_medium=web2x&context=3





```
toast.success(

`${

!isBookmarked

? "This film is now bookmarked"

: "This film is removed from your bookmarks"

}`,

{

position: "top-right",

autoClose: 2000,

hideProgressBar: false,

closeOnClick: true,

pauseOnHover: true,

draggable: true,

progress: undefined,

}

);

};
```