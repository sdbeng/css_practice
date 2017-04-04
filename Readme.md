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

<!--  -->
