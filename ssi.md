# Server Side Includes (SSI)

In addition to `index.html` we want to complete 4 other pages, one for each house in Hogwarts.

In the `lab04` Download contents, you'll see we included a `gryffindor.html` file.

If you look at this file in your code editor and browser, you'll notice it's very similar to `index.html` in that it shares the same navigational content.

Rather than having this information &ldquo;hardcoded&rdquo; in two (and ultimately six) different files, it makes sense to extract the navigation to its own file that can than be included in each page that needs to display the navigation.

We'll accomplish this using Server Side Includes.


## Build the part file
In your code editor create a new, blank file.

From `index.html` cut the code that makes up the inner content of the nav element (i.e. what's *inside* `<nav>` and `</nav>`).

Paste this code in your new file and save it as `nav.part`.

<div class='tip'>
Notes: This new file is only a partial HTML file&mdash; it does not have an `.html` extension, it does not contain all the tags needed for a complete webpage, and it cannot be validated by itself.
</div>


## Connect the part file
Back in `index.html`, use the following line to connect in the navigation code you just removed:

```html
<!--#include virtual="nav.part" -->
```

Likewise, for `gryffindor.html`, remove the navigation code and replace it with the include line.


## Upload your work to test it out
After you save all your changes, if you try to view your work in the browser, the navigation include won't work because the browser is unable to process the SSI code. Only servers can process the SSI code.

Given this, in order to test your work you need to upload it to the cs.wellesley.edu server.

SFTP into your account and upload the `lab04` folder you've been working in today into your `public_html` folder.

Change the permissions of `index.html` and `gryffindor.html` to **Execute**. In CyberDuck, you can do this by right clicking the file and choosing *Info*. In the window that pops up select the *Execute* option for the *Owner* of the file.

<img src='http://cs110.wellesley.edu/labs/lab04/images/cyberduck-set-permissions@2x.png' style='max-width:863px; width:100%;'>

Finally, test your work in the browser.

Your URL should look something like this: `http://cs.wellesley.edu/~yourUsername/lab04/index.html`.


## Pages for the remaining three houses.

* index.html &#x2713;
* gryffindor.html &#x2713;
* hufflepuff.html *Todo*
* ravenclaw.html *Todo*
* slytherin.html *Todo*

Time permitting, build three more pages for the remaining three houses of Hogwarts.

Use `gryffindor.html` as your starting template.

You can get the blurb of text for each house page by searching for the house name at <http://harrypotter.wikia.com/wiki>.
