# Lab 3: CSS

## Overview
In this lab you will practice specifying the style of HTML elements using Cascading Style Sheets (CSS).

The following resources should be helpful:

+ [Lecture notes: Introduction to CSS](http://cs110.wellesley.edu/~cs110/reading/CSS1.html)
+ [W3Schools CSS reference page](http://www.w3schools.com/cssref/default.asp)


## Setup
Connect to the CS server and download the folder `lab03` from `cs110/Download` to your Desktop.

From your Desktop, open the file `/lab03/wellesley/wellesley.html` file in your browser.

This file is your starting point for this lab; you'll notice it's just a simple, unstyled HTML page:

<img src='http://cs110.wellesley.edu/labs/lab03/images/wellesley-page-unstyled@2x.png' class='' style='max-width:1097px; width:100%' alt='Unstyled Wellesley page'>


## Goal
Your task for this lab is to take the above page and add style. The end result you're aiming for will look something like the screenshot below. Note that the content on this page is the exact same as the one above, the only difference is the styling.

<img src='http://cs110.wellesley.edu/labs/lab03/images/wellesley-page-styled@2x.png' class='' style='max-width:1097px; width:100%' alt='Styled Wellesley page'>


## Attach a stylesheet
Your first step to making this page beautiful is adding an external stylesheet.

Start with a new blank file in your code editor and add this code:

```css
body {
    background-color:orange;
}
```

Save this file as `style.css` in your `/lab03/wellesley/` folder.

Then, at the top of the `wellesley.html` file, in the `<head>` of the document, connect this stylesheet:

```html
<link href='style.css' rel='stylesheet'>
```

Reload the `wellesley.html` page in the browser. Is the background orange? Excellent! You've successfully attached an external stylesheet.

You can now remove the `background-color:orange` declaration in `style.css` (it was just for testing to confirm the connection worked.)


## Get styling
With your files all set up, start adding CSS to match the styled page shown above.

[You can open the screenshot in a new tab to use as reference...](/labs/lab03/images/wellesley-page-styled.png)

We'll start at the outside and work our way in.

First, the background color is black. By default the text color is also black, so we'll want to change that to white:

```css
body {
    background-color:black;
    color:white;
}
```

Inside the body, there appears to be one &ldquo;box&rdquo; that contains everything else; this box has a red border, and a Autumn foliage image background.

If you examine the HTML, you'll notice this box is made by a `<div>` with the id `wrapper`, so that's what you'll want to style next:

```css
#wrapper {

}
```

Fill in the appropriate styles for `#wrapper`:

+ Set the background image. Tip: Use `background-size:100%` to get it to fill the wrapper.
+ Set the border, choosing the appropriate width, style and color.
    + Find the exact color using [Pixlr](https://pixlr.com/editor/), or something close via [147 Colors](http://147colors.com/).
+ Set the width to be `920px`.
+ Set the padding to `20px`.
+ Center it in the browser window. Tip: the declaration to center a *block* element is `margin:auto`.
+ The majority of the inline content in `#wrapper` is centered, so add the `text-align:center` property;

While we're looking at the big picture of the page structure, you should also style the `footer`:

+ Set the width to be `960px`.
+ Center the footer in the browser window.

For any of the above settings, remember to refer to the [CSS Reference](http://www.w3schools.com/cssref/default.asp) or lecture notes.


## Dig deeper
With your outer elements (body and `#wrapper` div) styled, you can dig deeper and start styling the other elements:

+ Links
    + The links on the page should be white, with `5px` of padding.
    + When hovered, the background color of the links should change to black.
+ h1
    + Font is `Georgia`
    + Text is larger
+ Images
    + They have a rounded edge. You don't have to use the exact pixel value we use, just get close.
    + The image and the left and right are tilted - skip this for now. We'll come back to it as a bonus.
+ Paragraph of text
    + Text is left aligned
    + Font is `Helvetica`
    + Text is left aligned
+ Unordered list of links
    + There are no bullets on the list items.


## Bonus tasks

### Rotating
If you look at the images, you'll notice Melroy has the class `tiltleft` and Clinton has the class `tiltright`. Using these classes, we can use use the CSS transform property to tilt these images:

```css
.tiltleft {
    transform:rotate(-15deg);
    -webkit-transform:rotate(-15deg); /* for safari & chrome */
}
```

### Validate
Run your CSS code through the [CSS Validator](http://jigsaw.w3.org/css-validator/) to check for any problems.


## Footnotes
[Autumn Foliage background image credit: Soe Lin on Flickr](https://flic.kr/p/dki7eu)
