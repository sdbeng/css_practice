A browser will render the elements of an HTML document that has no CSS from left to right, top to bottom, in the same order as they exist in the document. This is called the flow of elements in HTML.

In addition to the properties that it provides to style HTML elements, CSS includes properties that change how a browser positions elements. These properties specify where an element is located on a page, if the element can share lines with other elements, and other related attributes.

In this lesson, you will learn three properties for adjusting the position of HTML elements in the browser:

* position
* display
* z-index

Each of these properties will allow us to position and view elements on a web page. They can be used in conjunction with any other styling properties you may know.
Instructions
Let's look at what we'll be building throughout the lesson! Compare the version that only utilizes default positioning for all elements to the version in which we've specified positioning to improve the appearance and usability of the site. You can see the differences between the styling if you look at style.css (the initial styles) and style1.css (the complete styles). When you feel ready to begin learning these properties, click "Next!"

<!-- Inline Display -->
Every HTML element has a default display value that dictates if it can share horizontal space with other elements. Some elements fill the entire browser from left to right regardless of the size of their content. Other elements only take up as much horizontal space as their content requires and can be directly next to other elements.

In this lesson, we’ll cover three values for the display property: inline, block, and inline-block.

The default display for some tags, such as <em>, <strong>, and <a>, is called inline. Inline elements have a box that wraps tightly around their content, only taking up the amount of space necessary to display their content and not requiring a new line after each element. The height and width of these elements cannot be specified in the CSS document. For example, the text of an anchor tag will, by default, be displayed on the same line as the text inside of an emphasize element. Each of these will only be as wide as necessary to contain their content.

To learn more about <em>inline</em> elements, click <a href="#">here</a>.
In the example above, the <em> element is inline, because it displays its content on the same line as the content surrounding it, including the anchor tag. This example will display:

To learn more about inline elements, click here.

The CSS display property provides the ability to make any element an inline element. This includes elements that are not inline by default such as paragraphs, divs, and headings.

h1 {
  display: inline;
}
The CSS in the example above will change the display of all <h1> elements to inline. The browser will render <h1> elements on the same line as other inline elements immediately before or after them (if there are any).

<!-- Block Display -->
Some elements are not displayed in the same line as the content around them. These are called block-level elements. These elements fill the entire width of the page and, unless specified, are the height necessary to accommodate the content inside.

Elements that are block-level by default include all levels of heading elements (<h1> through <h6>), <p>, <div> and <footer>. For a complete list of block level elements, click here.

strong {
  display: block;
}
In the example above, all <strong> elements will be displayed on their own line, with no content directly on either side of them even though their contents may not fill the width of most computer screens.

In the previous exercise we changed the display of all header elements to be inline. However, for this webpage we prefer the headers to each be on their own line. Below, you will revert the headers to block styling and change the display of <img>s to block to see how they behave.

<!-- Inline-Block Display -->
The third value for the display property is inline-block. Inline-block display combines features of both inline and block elements. Inline-block elements can appear next to each other and we can specify their dimensions using the width and height properties. Images are the best example of default inline-block elements.

For example, divs in the CSS below will be displayed on the same line and with the specified dimensions:

<div class="rectangle">
  <p>I’m a rectangle!</p>
</div>
<div class="rectangle">
  <p>So am I!</p>
</div>
<div class="rectangle">
  <p>Me three!</p>
</div>
.rectangle {
  display: inline-block;
  width: 200px;
  height: 300px;
}
In the example above, there are three rectangular divs that each contain a paragraph of text. The .rectangle divs will all appear inline (provided there is enough space from left to right) with a width of 200 pixels and height of 300 pixels, even though the text inside of them may not require 200 pixels by 300 pixels of space.

<!-- Positioning -->
The previous three exercises described three values for the display property, which we used to alter an element’s box and specify whether multiple elements can appear on the same line. Another property that we can use to specify how elements appear on a web page is the position property.

The position property specifies where an element is placed in relation to other elements and whether the element moves when the user scrolls. Just as all elements have a default display value, they also have a default position value. We can change the default position of an element by setting its position property. The position property can take one of four values:

static — an element will be positioned where it naturally occurs in the flow of the document from left to right, top to bottom (the default value).
absolute — an element will be positioned exactly where it is specified in relation to the nearest non-statically positioned element; it is removed from the flow of the web page.
relative — an element will be positioned in relation to where it would have occurred in the flow of the document; it is NOT removed from the flow and space is reserved for it.
fixed — an element will be positioned in the same place in the viewport of the browser (the part of the browser that contains the website being viewed) at all times, even if the user scrolls; it is removed from the flow of the web page.
In the next three exercises, you'll learn about the values in items 2, 3, and 4 above. If you prefer the default position of an HTML element, you don't need to set its position property because setting position: static should not change the position of any elements.

Set the footer element to have a position value of relative (which we’ll cover in a later exercise). The logo should now move to the footer because its parent element (the footer) has a position value that is not static.

<!-- Absolute -->
In the previous exercise, you learned that an element with position: absolute will be located in relation to the nearest element that has a position value other than static. Now, we are going to cover how to specify where the absolutely positioned element should go.

<div class="container">
  <img src="#" />
</div>
.container {
  position: relative;
}
img {
  position: absolute;
  top: 50px;
  left: 40px;
}
In the example above, the image will be located 50 pixels from the top and 40 pixels from the left of the .container element.

There are 4 values for offsetting position:

top — specifies how far from the top of the non-static parent container the element should be.
left — specifies how far from the left of the non-static parent container the element should be.
right — specifies how far from the right of the non-static parent container the element should be.
bottom — specifies how far from the bottom of the non-static parent container the element should be.
Note: It is generally not effective to specify all four values; a small element likely cannot be both 30 pixels from the left and 40 pixels from the right of the containing element because the container is probably much wider than that.

Absolute positioning has fallen out of practice with the advent of mobile development. Absolute positioning determines exactly where an element will appear on a screen and removes an element from the flow of the document. While an element might appear perfectly positioned on the screen you use for development, on a small screen it may overlap other elements or appear in an unexpected location.

<!-- Fixed -->
A third value for position is fixed. Fixed positioning causes an element to remain visible to the user at all times; even when scrolling, a fixed element will not move. Subsequently, the element is removed from the flow of the HTML document. This means that space will not be saved for it.

Once the element is removed from the flow of the document, all other elements after it in the flow of the document will shift upward and/or to the left as though the element never existed.

nav {
  position: fixed;
  top: 50px;
}
In the example above, the nav element will be positioned 50 pixels from the top of the viewport (the part of the web browser that contains the web page being viewed). Offsets work the same way for fixed positioning as they do for absolute positioning; however, the element is positioned in relation to the viewport rather than the web page itself.

Scroll up and down on the web site you’ve been editing. Now, click here and scroll up and down again. Notice that in the finished website, the header and nav always remain at the top of the page, even as the rest of the content seems to "disappear" underneath it. Below, we’ll add this type of styling to our project.

<!-- Relative -->
The final value for the position property that we’re going to cover in this lesson is relative. Unlike absolute and fixed positioning, relative positioning does not remove an element from the flow of an HTML document. This means that space is reserved for that element. relative positioning allows us to move an element relative to where it would have been positioned in the flow of the document.

As with fixed and absolute, you can use offset properties to relatively position an element.

<nav>
  <a href="#">About</a> <a href="#">Locations</a>
</nav>
<div class="container">
  <p>This container is 30 pixels down!</p>
</div>
.container {
  position: relative;
  top: 30px;
  left: 30px;
}
In the example above, the container element will be positioned 30 pixels below the nav and 30 pixels to the right of where it would have been if it was statically positioned.

<!-- z-index -->
When multiple elements on a web page use different position attributes, they (and therefore, their content) can overlap each other, making the content difficult to read or even hidden.

.navigation {
  background-color: olive;
  width: 100%;
  height: 100px;
  position: fixed;
}
.description {
  background-color: blue;
  width: 50px;
  height: 50px;
  position: relative;
  top: 200px;
}
In the example above, the description div would overlap the navigation div as the user scrolls.

The z-index property controls how far "back" or how far "forward" a non-static element should appear on the web page. The z-index property accepts integer values. These values instruct the browser in which order to display the elements on the web page.

.navigation {
  background-color: olive;
  width: 100%;
  height: 100px;
  position: fixed;
  z-index: 5;
}
.description {
  background-color: #1D09AF;
  width: 50px;
  height: 50px;
  position: relative;
  top: 200px;
}
In the example above, the z-index of the .navigation div has been set to 5, which instructs the browser to move this div forward and stack it "on top" of the other elements when the user scrolls.

The default value of z-index is auto. In practice, the browser will search for the z-index of the parent elements until it finds one. If none of the parent elements have a z-index declared, the z-index of the element will default to 0. Therefore, it is not necessary to set the z-index of .description to 0, as .description does not have a parent element with a z-index other than 0. Negative z-index values are not accepted. Setting the z-index of .navigation to a number greater than 0 is sufficient to prevent overlapping content.

z-index values are somewhat arbitrary — they don't need to start at 1. Any element that you wish to display in front of another item simply needs a z-index greater than the element beneath it. It is also unnecessary to create extremely large z-index values; incrementing z-indices by 5 or 10 is considered standard practice to allow for changes later on. Consider the example below:

.container {
  position: relative;
  top: 20px;
  left: 20px;
  z-index: 5;
}

footer {
  position: relative;
  top: 40px;
  left: 60px;
  z-index: 10;
}
In the example above, in the case of any overlap, the footer will be visible and .container elements will be hidden or overlapped.

Note: z-index cannot be used to style statically positioned elements.
Instructions
1.
When scrolling down the page, the nav disappears. In the nav rule in style.css, add the z-index property and assign it a value of 5. Scroll to see what's changed.
2.
Repeat Step 1 for the header rule. Scroll again.
3.
In the .date-square rule, set a z-index of 5. Scroll again. Now when you scroll all the way up, you should see that divs with the dates inside of them appear over the nav. We'll fix that in the next exercise.

At the end of the previous exercise, the nav, header, and date-square elements all had a z-index of 5. This resulted in the date-square elements overlapping the nav and header as the user scrolled. Let's explore why below.

<nav>
  <ul>
    <li>Home</li>
    <li>About</li>
  </ul>
</nav>
<div class="description">
  <p>A description of the purpose of the webpage</p>
</div>
nav {
  background-color: olive;
  width: 100%;
  height: 100px;
  position: fixed;
  z-index: 5;
}
.description {
  background-color: blue;
  width: 50px;
  height: 50px;
  position: relative;
  top: 200px;
  z-index: 5;
}
In the example above, the nav is fixed and there is a div containing a paragraph of text below it. The p element is below the nav element in the HTML file, so the p element will scroll over the nav as the user explores the web page. This is because if two elements with the same z-index overlap, the element that is lower in the HTML document will be rendered on top of the element that is earlier in the HTML document.

Let's fix this issue in our webpage below!
1.
In the nav rule in style.css, change the z-index property to the value of 10. Scroll to see what's changed.
2.
Repeat Step 1 for the header rule. Scroll again.

<!-- Review -->
Compare the website you started with to the one you have now! You have learned several useful tools to lay out your document.

The default positioning of elements is based on the flow of the HTML file.
Inline elements appear next to each other on the same line.
You can position elements to be displayed on their own line using block display.
Inline-block elements are on the same line as each other and their size can be set.
The default positioning for any element is static which means it will appear exactly as it does in the flow of the HTML document.
Elements with absolute positioning are removed from the flow of the document and positioned in relation to the parent element. This positioning will override display properties. An element with absolute positioning will scroll.
Elements with fixed positioning will not scroll as the page scrolls. This removes the element from the flow of the document.
Elements with relative positioning specify the element's distance from where it would have been positioned in the flow of the HTML document.
Non-static elements can be displayed in front or behind another element using the z-index property.
