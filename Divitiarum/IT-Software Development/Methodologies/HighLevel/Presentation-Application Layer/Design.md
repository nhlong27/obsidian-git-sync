[#design]
[Roadmap](https://roadmap.sh/design-system)


## $$Layout-Design$$
### Common
- Shells
	Horizontal, Vertical, Multi-column
- Layout
	Containers, Panels, Divider, Media Object
- Navigation
	Navbar/Tab (vertical, horizontal), Pagination, Breadcrumbs, Steps, Command Palettes, Flyout Menus
- Headings
	Page, Card, Section Headings
- Overlays
	Modals, Slide-overs, Notifications
- Elements
	Avatars, Dropdowns, Badges, Buttons
	
*Marketing*
|            | Landing Pages                               | Pricing Pages | Contact Pages |
| ---------- | ------------------------------------------- | ------------- | --------------- |
| Navigation | Banner                                      |               |                 |
|            | Flyout Menu                                 |               |                 |
| Sections   | Hero                                        | Header        | Header          |
|            | Why (Feature [partial + image, grid]/Blogs) | Pricing       | Contact/Team    |
|            | Who (Logo Clouds/Stats/ Testimonials)       |               |                 |
|            | Where (CTA/ Newsletter/FAQs)                |               |                 |
| Footer     |                                             |               |                 |
*Ecommerce*
|            | Storefront Pages          | Category/Search Pages | Product Pages     | Shopping Cart Pages | Order Detail Pages | Order History Pages |
| ---------- | ------------------------- | --------------------- | ----------------- | ------------------- | ------------------ | ------------------- |
| Navigation | Banner                    |                       |                   |                     |                    |                     |
|            | Search                    |                       |                   |                     |                    |                     |
|            | Flyout Menu               |                       |                   |                     |                    |                     |
| Sections   | Promo                     | Category Filter       | Product Overviews | Shopping Cart       | Order Summary      | Order History       |
|            | Incentives/Category       | Product List          | Reviews           | Checkout Form       |                    |                     |
|            | Previews/Product features |                       | Category Previews |                     |                    |                     |
| Footer     |                           |                       |                   |                     |                    |                     |

## **Refactoring UI**

- **Design Stage**
	- Features -> Data & Manipulations
	- Personalities
		- font family
			- by: popularity, font weight number, copying
			- headlines vs normal, or use letter-spacing
		- color scheme
		- form (border radius)
		- images
		- language
- **Implementation Stage**
	- Step 0 : Skeleton
		Raw Layout + Spacing  (data + manipulations)
		State management, API handling, Business Logic
	- Step 1: Flesh
		Flesh Layout + Spacing + Text + Colorscheme (neutral)
		Visual Hierachy
	- Step 2:  Skin
		Color + Images/Icons	

Sequences 
- media queries: mobile -> 
- routes 

### Visual Hierarchy
- Layout - Spacing 
	- Outer: max, min
	- Inner: ++ white space -> --, avoid ambiguous spacing, maybe baseline
	- Overlapping for layers

- Text: Primary, secondary, tertiary
	- font family (personality), beware all-caps
	- size - line height (style system)
	- weight

- Color Scheme 
	- Neutral: greys
	- Primary
	- Accent
	- Relationships
		- ![[Pasted image 20230512153436.png]]
		- Text: contrast ratio 3:1, 5:1
		- Depth: lighter -- darker

- Images/Icons
	- Text: Add overlay | Lower Contrast | Text shadow
	- Icons: no scaling (designed for sizes)
	- user-image: innerbox

### Style System
[consistent, organized, fast]
font-weight, line-height, color, margin, padding, width, height, box-shadows, border-radius, border-width, opacity
