# An overview of CSS
## 1. Introduction
Cascading Style Sheets (CSS) is a stylesheet language used to describe the presentation of a document written in HTML or XML. CSS describes how elements should be rendered on screen, on paper, in speech, or on other media.
## 2. BOX Model
Every element in the CSS is a box. Like every box in real life contains some width, height and many more things CSS box also contains width, height, paddig and margin. In css sometime a box may contains a outline which is similier to the margine border. Every box contains some containts.
Padding is appiled arround the content. Border is applied arround the padding. Margin is applied arround the border. We can say padding is the distance between border and contant and margin is the distance between the two adjecent boxes.
![](https://static.javatpoint.com/csspages/images/css-box-model.png)
## 3. Inline verses Block Elements
### 3.1 Inline Elements
An inline element takes space which is required for the content. An inline element does not start from a newline. It starts from the position where it find space for it.An inline element only takes up as much width as necessary. Here are some examples of inline elements.
``` 
<a> <abbr> <acronym> <b> <bdo> <big> <br> <button> <cite> <code> <dfn> <em> <i> <img> <input> <kbd> <label> <map> <object> <output> <q> <samp><script> <select> <small> <span> <strong> <sub> <sup> <textarea> <time> <tt> <var>
```
### 3.2 Block Element
A block-level element always starts on a new line, and the browsers automatically add some space (a margin) before and after the element.A block-level element always takes up the full width available (stretches out to the left and right as far as it can). Here is the some example of block level element
```
<address><article><aside><blockquote><canvas><dd><div><dl><dt><fieldset><figcaption><figure><footer><form><h1>-<h6><header><hr><li><main><nav><noscript><ol><p><pre><section><table><tfoot><ul><video>
```
## 4. Positioning in CSS
There are basically five types of positioning in css.__Static__ HTML elements are positioned static by default. Static positioned elements are not affected by the top, bottom, left, and right properties. __Relative__ An element with position: relative; is positioned relative to its normal position. Setting the top, right, bottom, and left properties of a relatively-positioned element will cause it to be adjusted away from its normal position. Other content will not be adjusted to fit into any gap left by the element. __Fixed__ An element with position: fixed; is positioned relative to the viewport, which means it always stays in the same place even if the page is scrolled. The top, right, bottom, and left properties are used to position the element. A fixed element does not leave a gap in the page where it would normally have been located. __Absolute__ An element with position: absolute; is positioned relative to the nearest positioned ancestor (instead of positioned relative to the viewport, like fixed).However; if an absolute positioned element has no positioned ancestors, it uses the document body, and moves along with page scrolling. Note: Absolute positioned elements are removed from the normal flow, and can overlap elements.
__Sticky__ An element with position: sticky; is positioned based on the user's scroll position.A sticky element toggles between relative and fixed, depending on the scroll position. It is positioned relative until a given offset position is met in the viewport - then it "sticks" in place (like position:fixed).

## 5. Common CSS structural and styling classes
In general to style a website we use two type of CSS files. First one is for define the structure of the websute and second one is for style the website. In these files we have some elements who have common style for these types of element we make a common class so that we can style all the element by writing code of one class. By using common class we can reduce a lot of work in styling.
## 6. CSS Specificity
If there are two or more CSS rules that point to the same element, the selector with the highest specificity value will "win", and its style declaration will be applied to that HTML element.Every CSS selector has its place in the specificity hierarchy.There are four categories which define the specificity level of a selector:Inline styles, IDs, Classe, pseudo-classes, attribute selectors elements and pseudo-elements.There are some points to remember in css specificity. Here I am talking a example with numbers.
* universal selector has zero spacificity.
* Classes selector has 10 specificity value.
* Ids selector has 100 specificity value.
* Inline selector has spacificity value 1000.
* if we combine more than one selector then we have to add specificity value of all the items then which has highest value has highest spacificity. 

## 7. CSS Responsive Queries
The @media rule is used in media queries to apply different styles for different media types/devices.Media queries can be used to check many things, such as:

* width and height of the viewport
* width and height of the device
* orientation (is the tablet/phone in landscape or portrait mode?)
* resolution

Using media queries are a popular technique for delivering a tailored style sheet (responsive web design) to desktops, laptops, tablets, and mobile phones.
CSS Syntax:
```
@media not|only mediatype and (mediafeature and|or|not mediafeature) {
  CSS-Code;
}
```
```
meaning of the not, only and and keywords:

not: The not keyword inverts the meaning of an entire media query.

only: The only keyword prevents older browsers that do not support media queries with media features from applying the specified styles. It has no effect on modern browsers.

and: The and keyword combines a media feature with a media type or other media features.

They are all optional. However, if you use not or only, you must also specify a media type.
```
Example 
```
/* On screens that are 992px wide or less, go from four columns to two columns */
@media screen and (max-width: 992px) {
  .column {
    width: 50%;
  }
}

/* On screens that are 600px wide or less, make the columns stack on top of each other instead of next to each other */
@media screen and (max-width: 600px) {
  .column {
    width: 100%;
  }
}
```
## 8. Flexbox/Grid
### Grid Layout
The CSS Grid Layout Module offers a grid-based layout system, with rows and columns, making it easier to design web pages without having to use floats and positioning.A grid layout consists of a parent element, with one or more child elements.An HTML element becomes a grid container when its display property is set to grid or inline-grid.All direct children of the grid container automatically become grid items.The horizontal lines of grid items are called rows.The gap property is a shorthand property for the row-gap and the column-gap properties.The grid-template-columns property defines the number of columns in your grid layout, and it can define the width of each column.
Example:
```HTML

<!DOCTYPE html>
<html>
<head>
<style>
.grid-container {
  display: grid;
  grid-template-columns: auto auto auto auto;<!--making 4 columnd in the grid -->
  gap: 10px; <!-- Giving gap between rows and columns-->
  background-color: #2196F3; <!-- Giving background color to the grid -->
  padding: 10px; <!-- giving padding to the grid -->
}

.grid-container > div {
  background-color: rgba(255, 255, 255, 0.8); <!--  giving background color to each cell-->
  text-align: center; <!-- making taxt centerd inside the cell-->
  padding: 20px 0;
  font-size: 30px;
}
</style>
</head>
<body>

<h1>The grid-template-columns Property</h1>

<p>You can use the <em>grid-template-columns</em> property to specify the number of columns in your grid layout.</p>

<div class="grid-container">
  <div>A</div> <!-- making child grid-->
  <div>B</div>
  <div>C</div>  
  <div>D</div>
  <div>E</div>
  <div>F</div>  
  <div>G</div>
  <div>H</div>
</div>

</body>
</html>
```
Output will be displayed like this
![](https://media.geeksforgeeks.org/wp-content/uploads/gridtemplate1.png)


## 9. Common header meta tags
The <meta> tag defines metadata about an HTML document. Metadata is data (information) about data.

<meta> tags always go inside the <head> element, and are typically used to specify character set, page description, keywords, author of the document, and viewport settings.Metadata will not be displayed on the page, but is machine parsable. Some important attributes of the metatag is given bellow:
  
  ### 9.1 meta tag
   It gives the information about the meta data. Here is the example of meta tag
  ```
 <meta name="viewport" content="width=device-width, initial-scale=1.0">
  ```
 The viewport is the user's visible area of a web page. It varies with the device - it will be smaller on a mobile phone than on a computer screen.The width=device-width part sets the width of the page to follow the screen-width of the device (which will vary depending on the device).

The initial-scale=1.0 part sets the initial zoom level when the page is first loaded by the browser.
  ### 9.2 title tag
  The <title> element defines the title of the document. The title must be text-only, and it is shown in the browser's title bar or in the page's tab.The contents of a page title is very important for search engine optimization (SEO)! The page title is used by search engine algorithms to decide the order when listing pages in search results.
  The <title> element:

*  defines a title in the browser toolbar
*  provides a title for the page when it is added to favorites
*  displays a title for the page in search engine-results
  For example
  ```
  <title>My first project</title>
  ```
  This will give the 
  ### 9.3 Open Graph Data 
  It is a metadata protocol that Facebook invented to provide richer metadata for websites. 
  ```
  <meta property="og:image" content="https://developer.mozilla.org/static/img/opengraph-logo.png">
<meta property="og:description" content="The Mozilla Developer Network (MDN) provides
information about Open Web technologies including HTML, CSS, and APIs for both Web sites
and HTML5 Apps. It also documents Mozilla products, like Firefox OS.">
<meta property="og:title" content="Mozilla Developer Network">
  ```
  ### 9.4  Twitter Cards
  Twitter also has its own similar proprietary metadata called Twitter Cards, which has a similar effect when the site's URL is displayed on twitter.com.
  ```
  <meta name="twitter:title" content="Mozilla Developer Network">
  ```
  ### 9.5 Different Styling tags 
  In HTML we use diffrent type of styling tags to style html such as link tag to link css and favicon and script tag to link  java script.
  ```
  <link rel="icon" href="favicon.ico" type="image/x-icon">
  <link rel="stylesheet" href="my-css-file.css">
 <script src="my-js-file.js" defer></script>
  ```
## 10. Conclusion
  The CSS is an important part of every website that is developed or devolopment is going on. Thus, a web page you see in a browser is a combination of the document’s data sources, with the CSS formatting rules applied. In the other tutorials in this section you will learn more about CSS, why it is important, and how to use it effectively.
## 11. References
  
1. https://www.w3schools.com/css/default.asp
2. https://developer.mozilla.org/en-US/docs/Web/CSS#cookbook
3. https://www.geeksforgeeks.org/css-grid-property/
