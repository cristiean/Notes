# HTML & CSS

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
