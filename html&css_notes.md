# HTML & CSS

## Introduction

### How people access the Web
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

### Structural markup

#### Headings
- HTML has six "levels" of headings: `<h1>`,`<h2>`,...
- Paragraphs (`<p>`). By default, browsers will show each paragraph on a new line and with some spacing between paragraphs.
- Bold & Italic. `<b>` and `<i>`.
- Superscript & Subscript. `<sup>` and `<sub>`.
- Whitespace. Two or more spaces are displayed as one space. A line break is also treated as one space. This is known as **white space collapsing**.
- Line breaks & Horizontal rules. `<br />` will add a line break. `<hr />` will add a horizontal rule (a horizontal line). Because these elements have only one tag, and don't contain any text, they are called **empty elements**. 

### Semantic markup
- Strong & Emphasis. `<strong>` indicates that the content is of strong importance (by default, this text will be boldened). `<em>` indicates emphasis that subtly changes the meaning of a sentence (by default italicised).
- Quotations. `<blockquote>` element is used for longer quotes that take up an entire paragraph. `<q>` is used for shorter quotes. Both elements may use the `cite` attribute to indicate where the quote is from (URL). E.g. `<q cite="https://example.com/source">Quoted text</q> from a source.`
- Abbreviations & Acronyms. `<abbr>` tag with a `title` attribute specifying the full term. E.g. `<abbr title=Deoxyribonucleic acid>DNA<abbr>`.
- Citations & Definitions. `<cite>` is used to reference works (books, papers, etc.). `<dfn>` should be used the first time a specific term is defined.
- Author details. `<address>` contains specific details about the author of the page.
- Changes to content. `<ins>` for insertions, `<del>` for deletions. `<s>` shows that something is no longer accurate or relevant (but that should not be deleted).

## 3. Lists

### Ordered lists
- `<ol>` ordered list
- `<li>` list item

### Unordered lists
- `<ul>` unordered list
- `<li>` list item

### Definition lists
- `<dl>` definition list
- `<dt>` defined term. A definition can define many terms.
- `<dd>` definition. A defined term can have many definitions.

### Nested lists
- List elements can nest other list elements.

## 4. Links
- Links are creating using an `<a>` element with an `href` attribute.

### Linking to other sited
- When linking to other websites, the `href` attribute should be an **absolute** URL.

#### Absolute URLs
- An absolute URL starts with the domain name and can be followed by the path to a specific page.

### Linking to other pages on the same site
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

### Email links
- The `mailto:` attribute will start the user's email program and address an email to the specified email address.
- E.g. `<a href="mailto:me@domain.com">Email me</a>`.

### Open links in a new window
- The `target="_blank"` attribute opens the link in a new window.
- It is nice to let the user know the link will open in a new window.
- E.g. `<a href="https://github.com/cristiean" target="_blank">My GitHub page</a>(opens in a new window)`

### Linking to a specific part of the same page
- Any HTML element can have an `id` attribute. Each element must have a unique `id` attribute for that page.
- To link to specific elements on the page associate `id` attributes to the elements you want to link to, and link to them using the `href` attribute with the value as the `#` key followed by the element's `id`.
- E.g. `<a href="#top">Go to the top</a>`

### Linking to a specific part of another page
- The same as above. You just need to append the `#id_of_element` to the absolute URL.
- E.g. `<a href="html.com/tutorial/#bottom">



### Directory structure
- On larger websites it's a good idea to organise the pages in folders.
- Each section of the website should be its own folder (also referred to as _directory_).
- Folders can have parents, children, grandparents or grandchildren of other folders.

## 5. Images

### Storing images on your site
- Keep images organised as your website grows by storing them in a directory tree.

### Adding images
- Use the **empty element** `<img>` with attributes:
  - `src` for the source of the image. This is usually a relative URL.
  - `alt` provides a text description of the image for those who cannot see it. Often referred to as **alt text**.
  - `title` provides additional information about the image. Most browsers will display this information as a tooltip when the user hovers the pointer over the image.

### Where to place images in your code
1. Before a paragraph
2. Inside the start of a paragraph
3. In the middle of a paragraph
- **Block elements always appear on a new line**. Examples include `<h1>` and `<p>` elements.
- **Inline elements sit within a block level element and do not start on a new line**. Examples include `<em>`, `<img>` and `<b>`.

### Image formats
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

