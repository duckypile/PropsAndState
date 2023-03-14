# Mar 14 2023

## Topics to cover

### HTML

Tags:

- h1 - h6 = headings
  - h1 = the largest and the main topic of the page
  - h6 = the smallest and the most sub topic
- body = the main context of the document
- headers/footer = consistent across different pages and navigational in nature
  - nav = section that hold navigational things
  - a = anchor - points to a different page or location in the browser
- main = the main content/topic of the body
- section = contatins info specific to a single topic
- aside = a collection of info that doesn't quite fit the context of the page
- p = paragraph - holds the text content of a paragraph
- img = image - take a src and alt attribute. src is url(more later)
- lists
  - ul = unordered list (bulletpoint lists)
    - li - list item with a bulletpoint
  - ol = ordered list (numbered lists)
    -li - list item with a number
- br - put a break in the document or new line
- hr - horizontal rule = line across the document
- address = element indicates that the enclosed HTML provides contact information for a person or people, or for an organization

Generic elements:

- div = divider - is a generic container (attempt not to use because it's generic)
- span = generic inline container for phrasing content, which does not inherently represent anything (attempt not to use because it's generic)

Other things to know:

- href - hypertext reference = points to new location inside opening <a> tag.

#### text-based HTML tags

- b - bolds text
- em - italicizes text

### CSS

There are 3 types of CSS styling:

- In-line styling - Where we're able to write a rule directly on a tag
- Internal styling - We're able to write our CSS in the head of document inside of style tag
- External styling - style outside of our file.

Writing CSS rules

1. You need to choose a selector
1. tag type -> ie. p, section, main, article, nav ...
1. class -> a group of similar items
1. id -> usually a unique identifier
1. You type curly braces
1. Inside you add `property: value` pair

#### Some different CSS rules:

- font-family = changing the font or type for a given bit of text
  - you'll want a fall back font-family
  - if there's a space it needs to be wrapped in quotes
- font-size = changes the size of the font
- color = changes the color of font
- padding = distance between the content and the border of the element
- border = outside of the padding
- margin = space outside of the border and between other elements
