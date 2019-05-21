# [_HTML & CSS_](http://htmlandcssbook.com/)- Notes
Book author: Jon Duckett

## Introduction

### How People Access The Web
1. You connect to the Web via an Internet Service Provider (ISP). You type the domain name or web address into your browser to visit a site.
2. Your computer contacts a network server called Domain Name System (DNS) servers. These tell your computer the IP address associated with the requested domain name.
3. The unique number that the DNS server returns to your computer allows your browser to contact the web server that hosts the website you requested.
4. The web server sends the page you requested back to your web browser.

#### Web Servers
- When you ask your browser for a webpage, your request is sent accross the Internet to a **web server** which hosts the website.
- **Web hosting** companies charge a fee to host your site.

## 1. Structure
- Web documents are structured as written documents, using headers, sub-headers, paragraphs, etc..
- HTML describes the structure of pages.
- HTML code is made up of **elements**.
- Elements are usually made up of two **tags**, the opening and closing tags, and the **content** between them. Elements act like containers for the content.
- Each HTML element tells the browser something about the information that sits between its opening and closing tags.
- The `<html>` tag indicates that everything between `<html>` and `</html>` is HTML code.
- The `<body>` tag indicates that everything between its opening and closing tag should be shown inside the main browser window.
- The `<h1>` tags indicate a main heading.
- The `<h2>`,`<h3>`,... tags indicate a sub-heading.
- The `<p>` tags indicate a paragraph of text.
- **Attributes** tell us more about elements.
- Attributes appear on the opening tag of the element and are made up of a **name** and a **value**. E.g. `<p lang="en-us">Paragraph in English.</p>`.
- The `<head>` element is usually found before the `<body>`.
- The `<head>` element contains information *about* the page. You can usually find the `<title>` element inside the `<head>` element.
- The `<title>` element are shown in the window bar, or the tab bar of the web page.

## 2. Text

### Structural Markup

#### Headings
- HTML has six "levels" of headings: `<h1>`,`<h2>`,...
- Paragraphs (`<p>`). By default, browsers will show each paragraph on a new line and with some spacing between paragraphs.
- Bold & Italic. `<b>` and `<i>`.
- Superscript & Subscript. `<sup>` and `<sub>`.
- Whitespace. Two or more spaces are displayed as one space. A line break is also treated as one space. This is known as **white space collapsing**.
- Line breaks & Horizontal rules. `<br />` will add a line break. `<hr />` will add a horizontal rule (a horizontal line). Because these elements have only one tag, and don't contain any text, they are called **empty elements**. 

### Semantic Markup
- Strong & Emphasis. `<strong>` indicates that the content is of strong importance (by default, this text will be boldened). `<em>` indicates emphasis that subtly changes the meaning of a sentence (by default italicised).
- Quotations. `<blockquote>` element is used for longer quotes that take up an entire paragraph. `<q>` is used for shorter quotes. Both elements may use the `cite` attribute to indicate where the quote is from (URL). E.g. `<q cite="https://example.com/source">Quoted text</q> from a source.`
- Abbreviations & Acronyms. `<abbr>` tag with a `title` attribute specifying the full term. E.g. `<abbr title=Deoxyribonucleic acid>DNA<abbr>`.
- Citations & Definitions. `<cite>` is used to reference works (books, papers, etc.). `<dfn>` should be used the first time a specific term is defined.
- Author details. `<address>` contains specific details about the author of the page.
- Changes to content. `<ins>` for insertions, `<del>` for deletions. `<s>` shows that something is no longer accurate or relevant (but that should not be deleted).

## 3. Lists

### Ordered Lists
- `<ol>` ordered list
- `<li>` list item

### Unordered Lists
- `<ul>` unordered list
- `<li>` list item

### Definition Lists
- `<dl>` definition list
- `<dt>` defined term. A definition can define many terms.
- `<dd>` definition. A defined term can have many definitions.

### Nested Lists
- List elements can nest other list elements.

## 4. Links
- Links are creating using an `<a>` element with an `href` attribute.

### Linking to Other Sites
- When linking to other websites, the `href` attribute should be an **absolute** URL.

#### Absolute URLs
- An absolute URL starts with the domain name and can be followed by the path to a specific page.

### Linking to Other Pages on the Same Site
- When linking to pages on the same site, the `href` attribute _can_ be a **relative** URL

#### Relative URLs
- Shorthand version of absolute URLs because you do not need to specify the domain name.
- Relative link types:
  - Same folder: `<a href="reviews.html">Reviews</a>`
  - Child folder: `<a href="music/reviews.html">Reviews</a>`
  - Grandchildren folder: `<a href="movies/dvd/reviews.html>Reviews</a>`
  - Parent folder: `<a href="../index.html">Home</a>`
  - Grandparent folder: `<a href="../../index.html">Home</a>`
- A forward slash will return the home page for that site.

### Email Links
- The `mailto:` attribute will start the user's email program and address an email to the specified email address.
- E.g. `<a href="mailto:me@domain.com">Email me</a>`.

### Open Links in a New Window
- The `target="_blank"` attribute opens the link in a new window.
- It is nice to let the user know the link will open in a new window.
- E.g. `<a href="https://github.com/cristiean" target="_blank">My GitHub page</a>(opens in a new window)`

### Linking to a Specific Part of the Same Page
- Any HTML element can have an `id` attribute. Each element must have a unique `id` attribute for that page.
- To link to specific elements on the page associate `id` attributes to the elements you want to link to, and link to them using the `href` attribute with the value as the `#` key followed by the element's `id`.
- E.g. `<a href="#top">Go to the top</a>`

### Linking to a Specific Part of Another Page
- The same as above. You just need to append the `#id_of_element` to the absolute URL.
- E.g. `<a href="html.com/tutorial/#bottom">



### Directory Structure
- On larger websites it's a good idea to organise the pages in folders.
- Each section of the website should be its own folder (also referred to as _directory_).
- Folders can have parents, children, grandparents or grandchildren of other folders.

## 5. Images

### Storing images on your site
- Keep images organised as your website grows by storing them in a directory tree.

### Adding Images
- Use the **empty element** `<img>` with attributes:
  - `src` for the source of the image. This is usually a relative URL.
  - `alt` provides a text description of the image for those who cannot see it. Often referred to as **alt text**.
  - `title` provides additional information about the image. Most browsers will display this information as a tooltip when the user hovers the pointer over the image.

### Where to Place Images in Your Code
1. Before a paragraph
2. Inside the start of a paragraph
3. In the middle of a paragraph
- **Block elements always appear on a new line**. Examples include `<h1>` and `<p\>` elements.
- **Inline elements sit within a block level element and do not start on a new line**. Examples include `<em>`, `<img>` and `<b>`.

### Image Formats
- _JPEG_. Use for images with many colours.
- _GIF_ or _PNG_. Use for images with few colours or large areas of the same colour, like logos, illustrations or diagrams.
- _SVG_ (Scalable Vector Graphic) is a new way of displaying vector images directly on the web.
- _Animated GIFs_ show several frames of an image in sequence.
- Transparency:
  - _Transparent GIFs_ only works for images that have straight edges and full transparency.
  - _PNGs_ work with images that have semi-opaque areas, round corners, diagonal lines or drop-shadows.
  
### HTML5: Figure and Figure Caption
- The `<figure>` element may include many `<img>` elements and only one `<figcaption>` element.
- The `<figcaption>` element allows the web page authors to add a caption to an image or a set of images.

## 6. Tables
- The `<table>` element is used to add tables to a web page.
- Tables are drawn row by row. Each row is created with the `<tr>` element (for _table row_).
- Inside each row there are a number of cells represented by the `<td>` element (_table data_) or `<th>` (_table heading_).
- You can make cells of a table span accross more than one row or column by using the `rowspan` and `colspan` attributes.
- For long tables you can split the table into a `<thead>`, `<tbody>` and `<tfoot>`.

## 7. Forms
- You can collect data from users using a form, which sits inside a `<form>` element.
- Information from a form is sent in **name, value** pairs.
- Each _form control_ is given a name, and the text the user types in or the values of the options they select are sent to the server.
- HTML5 introduces new form elements which make it easier for visitors to fill in forms.

### Form Structure
- Forms live inside `<form>` tags.
- Every `<form>` element requires an `action` attribute. This is the URL of the page on the server that will recieve the submitted data.
- By default, the forms will be submitted with the GET method. If you want to change this, use the `method` attribute. There are two methods of sending a form:
  - `get`- usually used for short forms, or when you are just retrieving data from the web server.
  - `post`- sends data through an HTTP header. Use the POST method if your form:
    - is very long
    - allows users to upload a file
    - contains sensitive data (e.g. passwords)
    - adds information to, or deletes information from, a database
- The form can have an `id` attribute.

### Input
- The `<input>` element is used to create different _form controls_.
- The `type` attribute specifies the type of the _form control_.
- Each _form control_ requires a `name` attribute, so the server knows which form control each piece of data was entered into.
- Some form controls require a `value` attribute. This indicates the option or options that the user may have selected.

### Text Input
- In the `<input>` element, use the `type="text"` attribute to create a single-line text input.
- The `maxlength` attribute limits the number of characters a user may enter into text fields.

### Password Input
- Use the `type="password"` attribute to create a single-line text box that acts exactly like a single-line text input, except that the characters are blocked out.

### Text Area
- The `<textarea>` element creates a multi-line text input.
- Unlike other input elements, it is **not an empty element**.
- Any text between the opening and closing `<textarea>` tags will apear in the text box when the page loads. If the user does not delete this text, it will be submitted.

### Radio Button
- Use if the users need to see all available options at a glance.
- Use the `type="radio"` attribute ti allow users to pick just one of a number of options.
- All options must have the same `name` attribute.
- Each option must have a `value` attribute.
- The `checked="checked"` attribute can be used to indicate which value (if any) should already be selected when the page is loaded.

### Checkbox
- `type="checkbox"` allow users to select and deselect multiple options.
- All options must have the same `name` attribute.
- Each option must have a `value` attribute.
- The `checked` attribute can be used.

### Select box (drop down list box)
- Use if there is a long list of options.
- The `<select>` element contains two or more `<option>` elements.
- The `<select>` element must have a `name` attribute. It indicates the name of the form control being sent to the server, along with the value the user selected.
- `<option>`:
  - The text between the opening and closing `<option>` tags will be displayed in the select box.
  - The `<option>` element uses the `value` attribute to indicate the value sent to the server along with the name of the control if this option is selected.
  - The `selected="selected"` can be used to indicate the option that should be selected when the page loads. If this option is not used, the first element in the select box will be selected when the page loads.

### Multiple select box
- You can allow users to select multiple options by using the `multiple="multiple"` attribute in a `<select>` element.
- You can also specify the number of visible options with the `size` attribute.

### File Input Box
- If you want to allow users to upload a file (image, video, PDF, mp3) you will need to use a file input box.
- Use the `type="file"` attribute within the `<input>` element.
- When you are allowing users to upload files, the `method` attribute on the `<form>` element must have the value `post`. (You cannot send files using the HTTP GET method).

### Submit Button
- `type="submit"`
- It can use a `name` attribute but it does not need to have one.
- The `value` attribute controls what text the button should display.

### Image Button
- `<input>` with `type="image"`
- The `src`, `width`, `height` and `alt` attributes work just like they fo when used with an `<img>` element.

### Button & Hidden Controls
- The `<button>` element gives you more control over how you display buttons.
- You can combine text and images between the `<button>` opening and closing tag.
- You can also have _hidden_ form controls. (For example, on the press of a button you want to send information to the server to bookmark the current page). To do this, use the `type="hidden"` attribute in your `<input>` element.

### Labelling Form Controls
- Each form control should have a `<label>` element
- The `<label>` element can:
  1. Wrap around both the text description and the form input (e.g. `<label>Age: <input type="text" name="age" /></label>`).
  2. Be kept separate from the form control and use the `for` attribute (e.g. `<input id="female" type="radio" name="gender" value="f"> <label for="female">Female</label>`).
- The `for` attribute states which form control the label belongs to. Its value should be the `id` attribute of the labelled form control.
- When a label is used with a radio button or a checkbox, the user can also press on the labels to select/deselect them.
- As a rule of thumb, place the labels:
  - Above or to the left of:
    - Text inputs
    - Text areas
    - Select boxes
    - File uploads
  - To the right of:
    - Individual radio buttons
    - Individual checkboxes

### Grouping Form Elements:
- Group related form controls using the `<fieldset>` element.
- The `<legend>` element can be placed after the opening `<fieldset>` tag. The text between the opening and closing `<label>` tags is a cption that describes the group of form controls.

### HTML5: Date Validation
- An example of HTML5 form validation is the `required="required"` attribute, which can be used with any form element that the user is expected to fill in.

### HTML5: Date, Email, URL and Search Inputs.
- `<input type="date">`
- `<input type="email">`
- `<input type="url">`
- `<input type="search">`. This can also have a `placeholder` attribute that will display text until the user clicks in the area.

## 8. Extra Markup

### Doctypes
- Because there have been several versions of HTML, each webpage should begin with a DOCTYPE declaration to tell the browser which version of HTML the page is using.
- `<!DOCTYPE html>` for HTML5

### Comments
- Enclose coments within `<!--` and `-->`.

### The `id` Attribute
- Every HTML element can carry an `id` attribute to uniquely identify it from other elements on the page.
- Giving elements unique attributes will allow you to style them using CSS.
- `id` attributes alwo allow JavaScript to work with particular elements.
- The `id` attribute is known as a **global attribute** because it can be used on any element.

### The `class` Attribute
- Every HTML attribute can also carry a `class` attribute to identify a set of elements as being part of the same group.
- An element can belong to many classes. Separate the classes with a whitespace e.g. `class="announcement important"`.

### Block Elements vs Inline Elements
- **Block elements** appear to start on a newline (examples are `<h1>`, `<p>`, `<ul>` and `<li>`).
- **Inline elements** will always appear to continue on the same line as their neighbouring elements (examples are `<a>`, `<b>`, `<em>` and `<img>`).

### Grouping Text & Elements in a Block
- The `<div>` element allows you to group a set of elements together in one block-level box.
- The `<div>` block will start on a new line.
- `id` and `class` attributes can be added to the `<div>` elements to add CSS styling rules.

### Grouping Text & Elements Inline
- The `<span>` element allows you to enclose:
  1. A section of text
  2. A number of inline elements
- `id` and `class` attributes can be added to the `<span>` elements to add CSS styling rules.

### IFrames
- The term iframe is an abbreviation of inline frame.
- `<iframe>` is a window on your page that shows another web page.
- It needs the `src` attribute with the value being a URL.
- `height` and `width` attributes specify the size of the iframe in pixels.
- The `seamless` attribute can be applied to an iframe where scrollbars are not desired.

### Information About Your Page
- The `<meta>` element lives inside the `<head>` element and contains information about the web page.
- It is not visible to the users, but provides useful information to search engines.
- `<meta>` elements can have any `name` attribute. However, there are some defined values that are commonly used:
  - `name="description"` contains a description of the webpage. Usually used by search engines. Should be less than 155 characters.
  - `name="keywords"` contains a list of comma-separated words that a user might search on to find the page.
  - `name="robots"` indicates whether the search engines should add this page to their search results or not.
- `<meta>` elements can also have `http-equiv` attributes:
  - `http-equiv="author"` defines the author of the webpage.
  - `http-equiv="pragma"` prevents the browser from caching the webpage.
  - `http-equiv="expires"` sets an expiration date for the page (after which the page should not be cached).

### Escape Characters
- Take the form of `&amp;` or `&#38;`. 

## 9. Flash, Video & Audio

### Flash
_I did not bother writing notes for this section, as it is not that relevant to me_

### HTML5 Video: `<video>`
- Add using the `<video>` element.
- The `<video>` element can have attributes:
  - `src`
  - `poster` the image displayed while the video is loading, or not playing
  - `width` and `height` 
  - `controls` indicates that the browser should supply its own controls for playback
  - `autoplay`
  - `loop`
  - `preload`, which can have the values `none`, `auto` or `metadata`
- To allow multiple browsers and devices to play your video, you can use multiple video sources with the `<source>` elements.
- The `<source>` element has attributes `src`, `type`, and `codecs`.

### HTML5 Audio: `<audio>`
- Similar to the video.

## 10. Introducing CSS
- CSS associates style rules with HTML elements.
- CSS treats HTML elements as boxes, and controls how these boxes and their content are presented.
- A CSS styling rule follows the pattern `selector { property: value; }`. This is a CSS styling rule: `p { font-family: Arial; }`.
  - `p` is the **selector**. It indicates which element the rule applies to. There can be more than one selectors separated by comma.
  - `font-family: Arial;` is the **declaration**. This indicates how the referred elements should be styled. There can be more tan one declarations, separated by a colon.Declarations sit inside curly brackets and each is made up of two parts:
    - `font-family` is the **property**
    - `Arial` is the **value**

### Comments
_This section is not in the book. I have added it myself._
- `/* comment here */`

### Using external CSS
- In the `<head>`, specify the CSS file that you want to style the page with.
- Use the `<link>` element with these three attributes:
  - `href` to specify the path of the file
  - `type` to specify the type of the document you link to. Usually `type="text/css"`
  - `rel` specifies the relationship between the HTML page and the file it is linked to. For a CSS file `rel="stylesheet"`
- An HTML page can use more than one stylesheet.

### Using internal CSS
- In the `<head>` element of the page, use the `<style>` element with the attribute `type="text/css"`. Write your CSS inside the latter.

### CSS Selectors
- **Universal Selectors**- applies to all elements in the document. `* {}`
- **Type Selectors**- matches element names. `h1, h2, h3 {}`
- **Class Selectors**- matches an element whose `class` attribute matches the one specified after the dot. 
  - `.note {}` refers to all the elements with `class="note"`
  - `p.note {}` refers only to `<p>` elements with `class="note"`
- **ID Selectors**- match elements whose `id` attributes match the one after the pound or hash symbols. `#intro {}`
- **Child Selectors**- match elements that are children of other elements. `ol>a {}` matches all the immediate `<a>` children of `<ol>` elements
- **Descendant Selectors**- match elements that are descendants of another specified element. `ol a {}` matches all the `<a>` elements within a `<ol>` element.

### How CSS Rules Cascade
- **Last Rule**- If two selectors are identical, the latter of the two will take precedence.
- **Specificity**- If one selector is more specific than the others, it will take precedence.
- **Important**- You can add `!important` after any property value to indicate that it should be considered more important than other rules that apply to the same element. E.g. `p { color:blue !important; }

### Inheritance
- Some properties are inherited from the parent elements.
- Others are not.
- You can specify which properties you want to inherit from their ascendants' properties by adding `inherit` to the property value. E.g. `.page { padding: inherit; }

### Use external stylesheets
- It keeps the structure and the styling separate
- It keeps the HTML document readable
- If you have a very small HTML page, or want to apply rules only to that HTML page, then you may use internal styling with `<style>`

## 11. Colour
- **RGB Values**- Red, green and blue. `rgb(100, 100, 100)`
  - Also `rgba(100, 100, 100, 0.5)`. The last letter refers to the **alpha** value (transparency). The alpha value is expressed as a number between 0 and 1.0.
- **HEX Codes***- Red, green and blue, but in hexadecimal representation. `#ffaabb`
- **Colour Names**- 147 colour names like `DarkCyan`
- **HSL Values**- Hue, saturation and lightness.
  - Also `hsla(100, 100, 100, 0.5)`.

### Foreground colour
- `color`

### Background colour
- `background-color`
- If you do not specify the background colour, it will simply be transparent.

### Understanding Colours
- **Hue** is a value between 0 and 360. Usually all the colours in a wheel, and the value is the angle. 
- **Saturation** is the amount of gray in a colour. The less saturated, the less gray. At maximum saturation, there is no gray in the colour.
- **Brightness** refers to the amount of black in a colour. The brighter a colour, the lesser the black. At maximum brightness, there should be no black in the colour.
- **Lightness** refers to the amount of white (lightness) or black (darkness) in a colour. This is different from brightness, as it can be completely black (dark) or light (white). The "normal" colour is at 50%, or 0.5.

## 12. Text

### Typeface terminology
- **Serif** fonts have extra details on the end of the main strokes of the letters.
- **Sans-serif** fonts have straight end to letters.
- **Cursive** fonts either have joining strokes or cursive characteristics
- **Fantasy** fonts are usually decorative fonts
- **Monospace** (fixed-width) fonts have letters of the same width.
- The **weight** of a font is how thick the letter lines are. (_Light_, _Medium_, _Bold_ and the thickest, _Black_).
- The **style** of a font is _Normal_, _Italic_ (usually with characters having a coursive aspect and sligthly tilted) and _Oblique_ (which is the normal style at an angle).
- The **stretch** of a font can be _Condensed_, _R e g u l a r_ or _E  x  t  e  n  d  e  d_
- **Ascender** is above the cap height
- **Cap height** is the top of flat letters
- **X-height** is the height of the letter _x_
- **Baseline** is the line the letters sit on
- **Descender** is below the baseline

### Techqniques that offer a wider choice of typefaces
- Suitable for any length of text
  - **Font-family**. The user's computer needs the typeface installed
  - **Font-face**. CSS specifies where the font can be downloaded from
  - **Service-based font-face**. Commercial services giving users access to fonts using `@font-face`
- Not suitable for long passages of text
  - **Images**
  - **sIFR**
  - **Cufon**
### Specifying typefaces
- `font-family`. The user needs to have the font installed
- You can specify more than one font separating them with commas.
- It is common to end with a generic font name for that type of font.
`body { font-family: Georgia, Times, serif; }`

### Size of type
- `font-size`. Specify the font size with:
  - Pixels. `15px`
  - Percentages. `200%` (percentage of the default text size of the browser)
  - Ems. `1.7m` (`1m` is equivalent to the width of a letter _m_)

### More font choice
```
@font-face {
  font-family: 'FontName';
  src:url('fonts/FontName.tff');}
  
h1, h2 {
  font-family: FontName, Georgia, sans-serif;}
```

### Bold
- `font-weight: normal;`
- `font-weight: bold;`

### Italic
- `font-style: normal;`
- `font-style: italic;`
- `font-style: oblique;`

### Uppercase and lowercase
- `text-transform:` can have values `uppercase`, `lowercase` or `capitalize`

### Underline and strike
- `text-decoration:` can have values `none`, `underline`, `overline`, `line-through` or `blink`

### Leading
- This is the vertical gap between lines of text
- `line-height: 1.3m`

### Letter and word spacing
- `letter-spacing`
- `word-spacing`

### Alignment
- `text-align` can be `left`, `right`, `center` or `justify`
- `vertical-align` can be many things including `top`, `bottom`, ...

### Indenting text
- `text-indent`. It can also have negative values, if you want to shift something away from the page, but still keep it in the HTML. e.g
```
h1 {
  background-image: url("images/logo.png");
  background-repeat: no-repeat;
  text-indent: -9999px;}
```

### Drop shadow
- `text-shadow: len1, len2, len3, colour;`
- `len1` indicates how far to the left or right the shadow should fall
- `len2` indicates the distance to the top or bottom the shadow should fall
- `len3` is optional and indicates the amount of blur

### First letter or line
- Using **pseudo-elements**
- `p.intro:first-letter { font-size: 200%; }`
- `p.intro:first-line { color: DarkGray; }`

### Styling links
- Using **pseudo-classes**
- `a:link { ... }`
- `a:visited { ... }`
- `a:hover { ... }`
- `active`, `focus`

### Attribute selectors
- There is a set of attribute selectors that allow you to create rules that apply to elements that have an attribute with a specific value.

## 13. Boxes

### Box dimensions

- `width`,  `min-width`,  `max-width`
- `height`, `min-heigth`, `max-heigth`

### Overflowing content

- The `overflow` property tells the browser what to do if the content contained within a box is larger than the box itself.
  - `overflow: hidden` hides any extra content that does not fit in the box
  - `overflow: scroll` adds a scrollbar to the box

### White Space & Vertical Margin

- If the bottom margin of any box touches the top margin of another, the browser will only show the larger of the two margins. 

### Border styling

- The border separates the edge of one box from another

- `border-width`
  - `border-top-width`
  - `border-right-width`
  - `border-bottom-width`
  - `border-left-width`
- `border-style` : `solid`, `dotted`, `dashed`, `double`, `groove`, `ridge`, `inset`, `outset`, `hidden`/`none`.
- `border-color`
  - `border-top-color`
  - ...
- **Shorthand** `{ border: <width> <style> <color>;}`, e.g. `{ border: 1px dotted DarkGray; }`

### Padding

- Padding is the space between the border of a box and any content within it.
- `padding: 1px`
  - `padding-top`
  - `padding-left`
  - ...

### Margin

- Margins sit outside the border. They create a gap between the borders of two adjacent boxes
- `margin: 12px`
  - `margin-top`
  - ...

### Centering content

- Specify the `width` of the box, otherwise it will take the entire width of the browser.

- Set the `left-margin` and `right-margin` to `auto`. This will put an equal gap on each side of the box.

### Change Inline/Block display

- `dsplay` property with `inline`, `block`, `inline-block` or `none` values.
- The `inline-block` value makes a block element flow like an `inline` element while retaining other features of a block-level element.

### Hiding boxes

- `visibility` property can have values `hidden` or `visible`
- If the `visibility` property is set to `hidden`, a blank space will appear in the element's place. If you don't want a blank space, you should use `display: none;`

### Border images

- `border-image`

### Box shadows

- `box-shadow` that can take four values:
  - Horizontal offset
  - Vertical offset
  - Blur distance. If ommited, the shadow is a solid line like a border.
  - Spread of shadow. If used, a positive value will cause the shadow to expand in all directions.
- `inset` value can be used to create an inner-shadow

### Rounded corners

- `border-radius`
  - `border-top-right-radius`
  - `border-bottom-left-radius`
  - ...
- e.g. `{ border-radius: 10px; }`

### Elliptical shapes

- Specify different distances for the horizontal and the vertical parts of the rounded corners
- e.g. `{ border-radius: 5px 10px; }`

## 14. Lists, Tables and Forms

### Bullet point styles

- `list-style-type`
  - For `<ul>`: `disc`, `circle`, `square` or `none`
  - For `<ol>`: `decimal`, `decimal-leading-zero`, `lower-alpha`, `upper-alpha`, `lower-roman`, `upper-roman`

### Images for bullets

- `list-style-image`

### Positioning the marker

- `list-style-position`
  - `inside`- The marker sits inside the box of text (which is indented).
  - `outside`- Default.

### List shorthand

- e.g. `list-style: inside circle;`

### Table properties

- `width`, `padding`
- `text-transform`
- `letter-spacing`, `font-size`
- `border-top`, `border-bottom`
- `text-align`
- `background-color`
- `:hover` 

### Border on empty cells

- `empty-cells`:
  - `show`- shows the borders of any empty cells
  - `hide`- hides the borders of any empty cells
  - `inherit`

### Gaps between cells

- `border-spacing` controls the distance between adjacent cells.
- `border-collapse`:
  - `collapse` collapses borders into a single border where possible
  - `separate`- borders are detached from each other. 

### Cursor styles

- `auto`, `crosshair`, `default`, `pointer`, `move`, `text`, `wait`, `help`, `url("cursor.gif")`

## 15. Layout

- **Block-level elements** start on a new line
- **Inline elements** flow in between surrounding text
- **Containing elements**. If one block-level element sits inside another block-level element then the outer box is known as the *containing* or *parent* element.

### Controlling the positioning of elements

- **Normal flow**(`position: static`). The paragraphs appear one after another, vertically down the page.
- **Relative positioning**(`position: relative`). The element is moved at a specified position relative to its normal flow position.
- **Absolute positioning**(`position: absolute`). The position of the element in relation to its containing element.
- **Fixed positioning**(`position: fixed`). A form of absolute positioning that positions the element in relation to the browser window.
- **Floating elements**(`float: left` or `float: right`). Take an element out of normal flow and position it to the far left or right of a containing box.
  - Clearing floats with `clear` (`clear: left`, `right`, `both` or `none`). This makes elements (within the same containing element) not touch the element `clear` hase been applied to.
- When you move any element from the normal flow, boxes can overlap. The `z-index` property allows you to control which box appears on top.

### Layouts

- **Fixed Width Layouts** do not change size along with the browser window. They tend to use pixels.
- **Liquid Layouts** stretch and contrasts to fill the browser window. They tend to use percentages.
- *Layout Grids* are good tools for arranging the page.

### Multiple Style Sheets

- `@import` style sheets from `url(link.com);`
- `link`

## 16. Images

- Control the **size** with `width` and `height`
- Align with `float`
- Center with `margin: 0px auto`

### Background images

- `background-image`
- `background-image-repeat`
  - `repeat`
  - `repeat-x` or `repeat-y`
  - `no-repeat`
- `background-attachment`
  - `fixed`
  - `scroll`
- `background-position`
  - You can use a pair of pixels or percentages or
  - `left top`, `center bottom`, `right center` etc. Imagine a square split in 9.
- Shorthand `{ background: DarkGray url("images/bg.gif") no-repeat top right; }`

### Use image sprites to reduce page load time

## 17. HTML5 Layout

- Instead of using `<div>`s, HTML5 has specialised tags for usual elements:
  - `<header>` and `<footer>` used as :
    - the main header and footer that appear at the top and bottom of every page on the site. or
    - a header or footer of an `<article>` or `<section>`
  - `<nav>` is used to contain the major navigational blocks on the site.
  - `<article>` acts as a container for any element that could stand alone
  - `<aside>` 
    - When used inside an `<article>`, it should contain information related to the article but not essential to its overall meaning
    - When used outside of an article, it acts as a container for the content that is related to the entire page.
  - `<section>` groups related elements together.
  - `<hgroup>` groups together a set of one or more `<h1>` to `<h6>`
  - `<figure>` that may include a `<figcaption>`
  - `<div>` for everything else

## 18. Process and Design

- *Who is the site for?*
- *Why do people visit your site?*
- *What are your visitors trying to achieve?*
- *What information do your visitors need?*
- *How often will people visit your site?*

- Thing about creating a **site map**
- Use **wireframes** in the early design process
- **Get your message accross** using design.
- **Visual hierarchy** helps you **communicate** through design.
- **Grouping and similarity** guides the users in finding what they're looking for.

## 19. Practical information

- Search Engine Optimisation (SEO)
  - On-page techniques
    - Page title
    - Hyperlink text should be explicit and not "click here"
    - Headings
    - Text
    - Image alt text
    - Page descriptions
  - Off-page techniques
- Identify keywords:
  1. Brainstorm
  2. Organise
  3. Research
  4. Compare
  5. Refine
  6. Map

