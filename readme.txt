github site

Jekyll Commands
---------------

test server

$ jekyll serve
# => A development server will run at http://localhost:4000/
# Auto-regeneration: enabled. Use `--no-watch` to disable.

Markdown
--------

**bold**

*italic*

# h1
## h2
### h3


LISTS

Markdown supports ordered (numbered) and unordered (bulleted) lists.

Unordered lists use asterisks, pluses, and hyphens — interchangably — as list markers:

*   Red
*   Green
*   Blue
is equivalent to:

+   Red
+   Green
+   Blue
and:

-   Red
-   Green
-   Blue
Ordered lists use numbers followed by periods:

1.  Bird
2.  McHale
3.  Parish


CODE BLOCKS

Pre-formatted code blocks are used for writing about programming or markup source code. Rather than forming normal paragraphs, the lines of a code block are interpreted literally. Markdown wraps a code block in both <pre> and <code> tags.

To produce a code block in Markdown, simply indent every line of the block by at least 4 spaces or 1 tab. For example, given this input:

This is a normal paragraph:

    This is a code block.

{% highlight swift %}
keychain.set("hello world", forKey: "my key")

keychain.get("my key")
{% endhighlight %}


IMAGES
------

Sadly this kramdown variant does not work with GFM, ![test](https://github.com/favicon.ico){:height="24px" width="48px"}

No scaling, with HTML <img src="https://github.com/favicon.ico">

Setting width to 48, with HTML <img src="https://github.com/favicon.ico" width="48">

Setting height to 24, with HTML <img src="https://github.com/favicon.ico" height="24">

Setting height to 24, and width to 48, with HTML <img src="https://github.com/favicon.ico" height="24" width="48">
