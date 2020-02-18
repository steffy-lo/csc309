# HTML & CSS

Web pages

* requested by web browsers, which interpret and display their contents
* written in HTML \(HyperText Markup Languange\)
  * describes a web page's content and structure

HTML Basic Structure

```text
<!DOCTYPE html>
<html>
    <head>
        This is where page metadata and invisible content goes
    </head>
    <body>
        This is where visible page content goes
    </body>
</html>
```

Note: the title of the webpage is not considered visible content because it is not in the viewport

HTML elements

* Most elements are indicated by an opening and closing tag
* Some elements don't need a closing tag
  * &lt;br&gt; line break
  * &lt;img...&gt; image tag
* Elements can contain other elements
  * &lt;p&gt; This is &lt;strong&gt; important. &lt;/strong&gt;&lt;/p&gt;

Minimum Valid HTML Page

```text
<!DOCTYPE html>
<html lang='en'>
    <head>
        <meta charset="utf-8">
        <title>CSC309</title>
    </head>
    <body>
    </body>
</html>
```

Notice how a body is not required. We can check if HTML is valid using: https://validator.w3.org/

```text
<!DOCTYPE html>
<html lang='en'>
    <head>
        <meta charset="utf-8">
        <title>CSC309</title>
    </head>
    <body>
        <h1>Welcome to CSC309</h1>
        <a href="lectures.html">Lectures</a> <br>
        <a href="assignments.html>Assignments</a> <br> <br>
        <strong>Course Topics</strong> <br>
        Here is what we'll be learning <br>
        <em>Note: Topics might change</em>
        <ul>
            <li>What is the web?</li>
            <li>HTML</li>
            <li>CSS</li>
        </ul>
    </body>
</html>
```

Notice how we don't have to put a newline beside &lt;em&gt; element and it will still but a newline.

Semantic Tags/Elements

* HTML tags that indicate their expected use \(e.g., &lt;form&gt;, &lt;table&gt;, &lt;h1&gt;\)
* Design - meaning of page is always the same regardless of style
* Accessibility - screen readers can change voice tone on a tag
  * e.g., If word is bold, it might say it louder
* Search Engine Optimization - density of keywords is higher when more semantic tags are used

CSS \(Cascading Style Sheets\)

* A language that describes the "style" \(layout and appearance\) of web pages
  * Separation of content \(HTML\) and layout \(CSS\)
* Cascading: how we style a web page has priority rules
* CSS files are simply a set of rules to style different parts of a web page

![Cascade: the order of precedence for rules on a selector](.gitbook/assets/image%20%285%29.png)

![](.gitbook/assets/image%20%281%29.png)

Some common properties that we can change:

* Colour
* Size
* Shape
* Position
* Font
* Text Alignment

Adding CSS to our Site: Need to make a CSS file and **link** it in our .html file

```text
    ...
    <head>
        <meta charset="utf-8">
        <title>CSC309</title>
        <link rel="stylesheet" type="text/css" href="styles.css">
    </head>
    ....
```

```text
/* Course pages styles */

/* Set all h1 elements to blue */
h1 {
    colour: blue;
    background-color: yellow; /* spans the entire width of the page */
}

/* Set all em tags to red */
em {
    colour: red;
    background-color: orange; /* doesn't span the entire page */
}
```

Inline and Block Elements

* Block elements \(e.g., &lt;p&gt;, &lt;h1&gt;, &lt;ul&gt;\)
  * Forces creation of newline
  * Height and width can be specified and changed
  * By default:
    * Width is full width of parent elements
    * Height is enough to fit the content

Inline elements \(e.g., &lt;strong&gt;, &lt;a&gt;, &lt;br&gt;, &lt;em&gt;\)

* Don't have defined width/height
* Can't have block element inside it
* Inline-block elements are inline elements that can have a height and width \(e.g., images &lt;img&gt;\)

There are two non-semantic elements &lt;div&gt; and &lt;span&gt; that is generic with no specific purpose

* &lt;span&gt; is a generic inline element
* &lt;div&gt; is a generic block element
* Are used more for creating natural divisions throughout your page
  * Note: don't visually divide anything themselves
  * You have to indicate how they should appear relative to other elements

CSS classes

* Can define your own CSS selectors: classes
  * An attribute of a HTML element
* In HTML: &lt;span class="highlight"&gt;This is important&lt;/span&gt;
  * This gives this specific &lt;span&gt; tag a class attribute named "highlight
* In CSS, we can select them classes putting a dot before the class name \(e.g., .highlight { ... }\)

HTML/CSS id's

* id attribute in HTML meant to be a unique identifier
  * Only one element should have a particular id
* In CSS, ids are selected by a hash symbol \(e.g., \#navbar { ... }\)

**Combining Selectors**

* Descendant Selector
  * p strong { background-color: yellow; }
  * applies to all &lt;strong&gt; elements that are inside a &lt;p&gt;
* elements.class Selector
  * p.highlight { background-color: yellow; }
  * applies to all &lt;p&gt; elements that have class highlight
* Multiple element selector
  * p, strong, h1 { background-color: yellow; }
  * applies to all &lt;p&gt;, &lt;strong&gt;, and &lt;h1&gt; elements

Note: The more specific selector will take precedent

* Ids
* Classes
* Elements
  * Parent elements more specific that children
* How about same specificity? Rule: further down style sheet wins

CSS Inheritance: Children inherit parent styles in most cases

Size and Position: CSS Box Model

* All HTML elements are considered 'boxes' by CSS
* Element size and position determined by values of the box model

![CSS Box Model: Size](.gitbook/assets/image%20%282%29.png)

All size elements are properties in CSS

Content Size \(blue area\) specified by pixels or percentage of parent element dimensions

e.g. width: 20px, height: 50%

Recall: can only change height/width for block elements

CSS Positioning

* positioning of elements refers to a deviation from their natural flow
* Static: default position \(in the 'flow'\)
* Fixed
  * fixed position in viewport
  * doesn't move even with scrolling
* Relative
  * positioned relative to its natural location
* Absolute
  * positioned relative to _first_ **non-static** parent

