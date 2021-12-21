# Desing Web pages with CSS

## What is CSS?

> Definition: [css](<https://developer.mozilla.org/en-US/docs/Glossary/CSS"This is CSS">) (Cascading Style Sheets) allow you to create great-looking web pages, but how does it work under the hood? This article explains what CSS is, with a simple syntax example, and also covers some key terms about the language.

## Browser defaults

The browser will style HTML documents using an internal stylesheet. This will ensure that headings are larger than normal text, links are highlighted and structures such as lists and tables are understandable.

Paragraphs are spaced out. List items get a bullet or number.

* Item One
* Item Two

## What is CSS for?

CSS is a language for specifying how documents are presented to users with their style, laid out, etc.

[HTML](<https://developer.mozilla.org/en-US/docs/Glossary/HTML>) is the most common markup language, but you may also come across other markup languages such as [SVG](<https://developer.mozilla.org/en-US/docs/Glossary/SVG>) or [XML](<https://developer.mozilla.org/en-US/docs/Glossary/XML>).

## CSS syntax

CSS is a rule-based language - you define rules specifying groups of styles that should be applied to particulare elements or groups of elements on your web page. For example "I want the main heading on my page to be shown as large red text."

> h1 {\
> color: red;\
> font-size: 5em\
>}
>

The rule opens with a [selector](<https://developer.mozilla.org/en-US/docs/Glossary/CSS_Selector>). This *selects* the HTML element that we are going to style. In thi scase we are style level one headings.

The curly braces represent **declarations**, which take the form of **property** and **value** pairs. Each pair specifies a property of the element(s) we are selecting, then a value that we'd like to give the property.

Before the colon, there is the property, after the colon, the value. CSS properties have different allowable values, depending on which property is being specified.

### Tools

* [How to Add CSS](<https://developer.mozilla.org/en-US/docs/Web/CSS/Reference>)
* [CSS Color](<https://www.w3schools.com/cssref/pr_text_color.asp>)

### Short References

* [CSS Reference](<https://developer.mozilla.org/en-US/docs/Web/CSS/Reference>)
* [Myers Web Reset Stylesheet](<https://meyerweb.com/eric/tools/css/reset/>)
