# Mar 14 2023

## Topics to cover

### HTML

Tags:

- `<h1>` - `<h6>` = headings

  - `<h1></h1>` = the largest and the main topic of the page
  - `<h6></h6>` = the smallest and the most sub topic

<h1>the largest</h1>
<h2>next largest</h2>
<h3>sort of large</h3>
<h4>a little smaller</h4>
<h5>not the smallest</h5>
<h6>the smallest</h6>

- `<body>` = the main context of the document
- `<header>`/`<footer>` = consistent across different pages and navigational in nature
  - `<nav>` = section that hold navigational things
  - `<a>` = anchor - points to a different page or location in the browser
- `<main>` = the main content/topic of the body
- `<section>` = contatins info specific to a single topic
- `<article>` = Examples include: a forum post, a magazine or newspaper article, or a blog entry, a product card.
- `<aside>` = a collection of info that doesn't quite fit the context of the page
- `<p>` = paragraph - holds the text content of a paragraph
- `<img>` = image - take a src and alt attribute. src is url(more later)
- lists
  - `<ul>` = unordered list (bulletpoint lists)
    - `<li>` - list item with a bulletpoint
  - `<ol>` = ordered list (numbered lists)
    - `<li>` - list item with a number
- `<br>` - put a break in the document or new line
- `<hr>` - horizontal rule = line across the document
- `<address>` = element indicates that the enclosed HTML provides contact information for a person or people, or for an organization

Generic elements:

- `<div>` = divider - is a generic container (attempt not to use because it's generic)
- `<span>` = generic inline container for phrasing content, which does not inherently represent anything (attempt not to use because it's generic)

Other things to know:

- `href` - hypertext reference = points to new location inside opening a tag.

#### text-based HTML tags

- `<b>` - bolds text
- `<em>` - italicizes text

#### Element

![html element](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Getting_started/grumpy-cat-small.png)

### CSS

There are 3 types of CSS styling:

- In-line styling - Where we're able to write a rule directly on a tag
- Internal styling - We're able to write our CSS in the head of document inside of style tag
- External styling - style outside of our file.
  ![Writing Rules](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics/css-declaration-small.png)

Writing CSS rules

1. You need to choose a selector
1. tag type -> ie. p, section, main, article, nav ...
1. class -> a group of similar items
1. id -> usually a unique identifier
1. You type curly braces
1. Inside you add `property: value` pair

#### Some different CSS rules:

- font-family = changing the font or the type for a given bit of text
  - Make sure you have a fallback font-family category (i.e. serif or sans-serif) as the last value in your font-family rule
  - Any font with 2 or more words must be wrapped in quotes
- font-size = changing the size of the font
- padding = distance between your HTML content and the border of its HTML container element
- margin = distance between your HTML container's BORDER and the border of the browser window
- text-decoration = allows you to stylize text
- display = Changing the display orientation of a given HTML element
  - Table
  - inline
  - Block
  - inline-block
- text-align = Where do you want your text to be oriented to
- width
- height
- border = What kind of border do you want to give to your HTML elements
- border-radius = the amount of curve you give to the border
- position = What position do you want your element to be relative to everything else
- color = generally refers to text
- background-color = color of the background
- background-image = `url("someurlhere.com")
- opacity = change the transparency of an image or background or other stuff.

#### Selectors:

- Parent-child relationship
  - A quirky game to help with understanding selectors!
    [CSS Dinner](http://css-dinner.fullstackacademy.com/)

Specificity:

- [Specifics on CSS Specificity](https://css-tricks.com/specifics-on-css-specificity/)

- Tagname least specific
- Class next
- ID most specific
- Inline style most specific (in these examples)

Box Model:

- Everything is a box. Use \*{border: 2px solid red} at the top of your style sheet to see a visual representation of this.

- Also visible in the browser dev-tools.

- Think of the box model like a item hanging in a gallery:

  - content: the painting/photograph
  - padding: matte surrounding the art
  - border: the physical frame itself
  - margin: space on the wall between items

- Use box-sizing to determine how the width and height properties interact with these properties.

- Suggestion: use box-sizing: border-box everywhere.

- Under border-box, the width of the content area is: width - borderWidth - paddingWidth

- By default, width of the element is width + borderWidth + paddingWidth

(The same is true of height.)

Display | Block & Inline:

- Block:

  - Owns the entire line
  - Width is generally 100% of the contain it's in
  - Width and height can be difined
  - Examples: (h1, p, header, main, section, footer)

- Inline:
  - The element generates one or more inline element boxes that do not generate line breaks before or after themselves. In normal flow, the next element will be on the same line if there is space.
  - Examples: (span, a, em, label)
  - Can be explicitly coerced into a block element by using display: block;

#### **General Resources and Links**

- [MDN CSS Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)
- [W3Schools CSS Reference](https://www.w3schools.com/css/css_colors_rgb.asp)
- [CSS-Tricks Guides](https://css-tricks.com/guides/)
- [Video: Kyle's Web Dev Simplified YouTube Channel](https://www.youtube.com/playlist?list=PLZlA0Gpn_vH9xx-RRVNG187ETT2ekWFsq)

@import url('https://fonts.googleapis.com/css2?family=Poor+Story&family=Rubik+Bubbles&display=swap');

Values/Units

- Examples (px, em, rem, in, vw, vh)
  - More on [CSS Units](https://www.w3schools.com/cssref/css_units.asp)

Pseudo-classes

- Can't be used inline.
- :hover
- Allows you to change styling based on hovering over an element. Frequently used on images and anchor tags.
- Tons more [Pseudo-Classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)

Importing Fonts

- [Google Web Fonts](https://fonts.google.com/)
- Use this syntax -> @import url(https://fonts.googleapis.com/somefont-family-here) that is generated at the top of your style sheet. Then, include the font-family as usual in your style rules.
- If using internal styling, and I suggest you don't, you'll need to include a link tag in the head with the href that points to the font url. Then, include the font-family as usual in your style rules.

Float

- More on [Floats](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Floats)
- Removed from normal flow.
- float: left
- Element floats to the left of it's container.
- float: right
- Element floats to the right of it's container.

Position

- More on [Position](https://www.w3schools.com/cssref/pr_class_position.asp)

- static: Static position corresponds to the normal flow.
  Other positions place the element according to the left, top, right, and bottom css properties.

- relative: Relative elements are offset in their screen position relative to where they would be rendered in the normal flow. Relative positioning does NOT effect the position of other elements in the normal flow.

- absolute: Absolute elements are taken out of normal flow. Their position is relative to their layout parent. The layout parent of an absolute element is the nearest non-static element. This can be an relative or absolute element. If all the parents of an absolute element are position: static, it is positioned relative to the document body.

- fixed: Fixed elements are positioned relative to the browser screen.
