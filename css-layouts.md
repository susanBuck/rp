# CSS: Page layouts

## Overview

+ Recap: 
	+ 4 position properties
	+ fixed vs. fluid layouts
	+ float
+ Practice creating page layouts with CSS.


## Useful references
Lecture notes:

+ [Chrome's Inspect Element](http://cs110.wellesley.edu/reading/chrome-inspector.html)
+ [Box model](http://cs110.wellesley.edu/~cs110/reading/box-model.html)
+ [Fonts and web fonts](http://cs110.wellesley.edu/~cs110/reading/fonts.html)
+ [CSS Page layout](http://cs110.wellesley.edu/reading/page-layout.html)


## Download lab materials
Following the same procedures you used last week, log into the cs.wellesley.edu server to download a copy of the `lab04` folder from the shared `Downloads` folder.

Download `lab04` to your Desktop.

Open the `lab04` folder in Atom.


## Plan your approach
If you open up `lab04/index.html` in your browser, you'll see this unstyled HTML page:

<img src='http://cs110.wellesley.edu/labs/lab04/images/progress-shot-start@2x.png' style='width:500px' alt='Unstyled page'>

<br><br>
Our goal in this lab is to take that HTML page, add style, and end up with this:

<img src='http://cs110.wellesley.edu/labs/lab04/images/progress-shot-end@2x.png' style='width:500px' alt='Finished page'>

<br><br>
To accomplish this task, we'll start by with the big pieces and work our way in. Don't worry yet about things like colors, background images, fonts, etc. We'll get to them at the end.

Open `lab04/index.html` in your code editor. Note the outer elements that act as containers for the smaller parts of the page.

Using a blank sheet of paper, and referring to the finished screenshot above, sketch out where you think the &ldquo;containers&rdquo; of this layout are.


## Lay out the big pieces

### Outer container:
Identify the outer most container.

Set a width of `800px` and center it on the page.

Give it a `background-color:red;`. It'll be ugly, but it's only temporary, and it will help us see the shape of the container.

<img src='http://cs110.wellesley.edu/labs/lab04/images/progress-shot-first-container@2x.png' style='width:250px' alt='First container'>


### Columns
Identify the two columns that reside in the outer most container.

Give the left column a width of `200px` and the right column a width of `600px`.

Give the left column a `background-color:yellow;` and the right column a `background-color:blue;` so you can easily see them on the page.

<img src='http://cs110.wellesley.edu/labs/lab04/images/progress-shot-columns@2x.png' style='width:250px' alt='Add columns'>

What property do you add to the left column to get it to set next to the right column?

When you add this property, the right column will fall under the left columns:

<img src='http://cs110.wellesley.edu/labs/lab04/images/progress-shot-columns-floated@2x.png' style='width:250px' alt='Add columns'>

<br>
What is one way to fix this? The end result, after the fix, should look like this:

<img src='http://cs110.wellesley.edu/labs/lab04/images/progress-shot-columns-fixed@2x.png' style='width:250px' alt='Add columns'>


## Layout the 2x2 grid of house information

Now lets focus on arranging the content in the right column.

In the final example ([screenshot](/labs/lab04/images/progress-shot-end@2x.png)), we see a 2x2 grid of Hogwart's house information. Each grid element is contained in what element?

If the total width of this column is `600px` how wide should each grid element be? Set this width. Also, give the grid elements a `background-color:green`.

<img src='http://cs110.wellesley.edu/labs/lab04/images/progress-shot-first-identify-grid@2x.png' style='width:250px' alt='Identify the grid'>

<br>
The grid elements are stacked up&mdash; what property do you add to get them to sit next to one another, like this:
<img src='http://cs110.wellesley.edu/labs/lab04/images/progress-shot-first-grid-working@2x.png' style='width:250px' alt='Grid working'>


You should now have a 2x2 grid.

Add a `margin:5px` to your grid elements, so they have a little &ldquo;breathing room&rdquo;

Woah! That broke your grid:

<img src='http://cs110.wellesley.edu/labs/lab04/images/progress-shot-broken-grid@2x.png' style='width:250px' alt='Broke the grid after adding a margin'>



What happened, and how can you fix it? The end result, so far, should look like this:

<img src='http://cs110.wellesley.edu/labs/lab04/images/progress-shot-grid-fixed@2x.png' style='width:250px' alt='Fixed the grid'>


## Fine tune
At this point, your overall layout is pretty complete and you can start &ldquo;drilling in&rdquo; to the specifics.


### Navigation column
+ Remove the bullet points from the links in navigation column on the left
+ Make the links bold, black, and remove the underline.


### Houses
+ Add `5px` of padding to your house grids. This will break your 2x2 floating grid layout, just like when you added the margin, so you'll have to fix that again.
+ Float the crest images, so that the h2s will sit next to them.
* Make the h2 text use the font `'Uncial Antiqua', cursive`
+ Make the paragraph text inside the grids use the font `'Helvetica', serif`.
+ Make the links black.
+ Set the border and font color of each house grid to match the house color
    + To find out the specific color code for the house colors, you can use our screenshot of the final product + Pixlr to do a little color detection.


### Misc
+ Center the text in the footer.
+ Set the font on the h1 to match the same font you used on the h2s.
+ Add the tiling background image (`images/old-map-texture.png`).
