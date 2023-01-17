# Basic Syntax Notes

## Overview

### Headings

* Use (#) in front of word or phrase to create headings
  * Use up to (6) (#)'s for each level of heading
* Use any number of (==) for level 1 or (--) for level 2 headings
* Put blank lines before and after a heading for compatibility

### Paragraphs

* Use a blank line to create paragraphs
  * Do not indent paragraphs with spaces or tabs
* Use two or more spaces ("trailing whitespace") for line breaks in nearly every Markdown application. 
  * Because this is hard to see, you can use the line break or new line HTML tag to identify the "trailing whitespace"

### Emphasis

* To bold text, add two **asterisks** or __underscores__ before and after a word or phrase. 
* To italicize text, use one *asterisk* or _underscore_ before and after 
* To bold and italicize at the same time, add three ***asterisks*** or ___underscores___ before and after a word or phrase.

### Blockquotes

* To create a blockquote, add a > in front of a paragraph

##### Example

> Santa is always at the right place at the right time

* For multiple paragraphs, add a > on the blank lines between the paragraphs as well

##### Example

> Santa is always at the right place at the right time
>
> He never catches Mrs. Clause making her famous cookies from the **Tollhouse** carton

* Blockquotes can be nested. Add a >> in front of desired nested paragraph

##### Example

  > Santa is always at the right place at the right time
  >
  >> He never catches Mrs. Clause making her famous cookies from the **Tollhouse** carton

### Lists 

* To create an ordered list, add line items with numbers followed by periods
  * Numbers don't thave to be in numerical order, but the list should start with the number one.

##### Example

1. Make list
2. Check it twice
3. Who is *nice*
4. Who is *naughty*

* Use periods only, no paranthesis
* Create an unordered list by adding dashes(-), astrisks, or plus signs (+) in front of line items. 
* Use a backslash when starting an unordered list item with a number followed by a period. This escapses the period. 
* Use the same delimiter in the same list

#### Code Blocks & Images and Lists

* Code blocks, images, & lists are normally indented four spaces or one tabe. 
  * When they're in a list, indent them eight spaces or two tabs.

### Code

* To denote a word or phrase as code, enclose it in `backticks`.
* If the word or phrase you want to denote as code includes one or more backticks, you can escape it by enclosing the owrd or phrase in drouble backticks.
* To create code blocks, indent every line of the block by at least four spaces

### Horizontal Rules

* To create a horizontal rule, us three or more asterisks, dashes, or underscores on a line by themselves. 

##### Example

Try to put a blank line before...

---

...and after a horizontal rule

### Links & Formatting Links

* To create a link, enclose the link text in brackes (e.g., [Duck Duck Go]) and the follow it immediately with the URL in parentheses
* You can optionally add a title for a link.
* To quickly turn a URL or email address into a link, enclose it in angle brackets.
* To emphasize links, add asterisks before and after the brackets and parentheses. 

##### Example 

My favorite search engine is also ***[Duck Duck Go](https://duckduckgo.com "Best little search engine that could")***.

<123email@worstpassword.com>

### Reference-style Links

* Reference-style links are a special kind of link that make URLs easier to display and read in Markdown.
  * The first part of a reference-style link is formatted with two sets of brackets. The first set of brackets surrounds the text that should appear linked. 
  * The second set of brackets displays a label used to point to the link you're storing elsewherein your document. 
* The second part of a reference-style link is formatted with the following attributes:
  * The label, in brackes, followed immediately by a colon and at least one space (e.g., [label]: ).
  * The URL for the link, which you can optionally enclose in angle brackets. 
  * The optional title for the link, which you can enclose in double quotes, single quotes, or parentheses.

##### Example

In the coming of dawn of Christmas, Santa was rushing to grab the final present to deliver in his sack. As he reached into his sack he found a [hole][1], and that struck fear in his heart. 

[1]: <merriam-webster.com/dictionary/abyss> "Deepest of holes"

### Images

* To add an image, add an exclamation mark (!), followed by alt text in brackets, and the path or URL to the image asset in parentheses. You can optionally add a title after the URL in the parentheses. 

![heavy_metal_santa_claus](https://user-images.githubusercontent.com/95889943/145916691-b7334aeb-bf3b-4f94-892b-54a6386ff442.jpeg)


### Escaping Characters

* To display a literal character that would otherwise be used to format text in a Markdown document, add a backslash in front of the character

\* Without the backslash, this would be a bullet in an unordered list. 

[<---BACK](README.md)


