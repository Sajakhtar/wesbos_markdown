# Mastering Markdown

[Mastering Markdown by Wes Bos](https://masteringmarkdown.com/)

Use cases for markdown

- Formatted text
  - `README.md` files for Github projects
  - general notes, communiticating on Github, reddit or email
  - writing a book/ thesis
  - text cells in Jupyter Notebooks/ Google Colab
- Markdown converts to html also

## Tooling

It's easy to write markdown within your text editor, for which there will be extentions to help with syntax and shortcuts, but there are markdown apps as well.

Markdown Apps

- [marked2](https://marked2app.com/)
- [Mou markdown editor](http://25.io/mou/) - good for people used to Microsoft Word
- [MultiMarkdown](https://multimarkdown.com/)

## Paragraphs and Text Decoration

Markdown requires a full line space between each group of text for that group to become a paragraph element.

Decorations

- wrap text in asterisks `*italic*` for it to be _italic_
- wrap text in 2 sets of asterisks `**bold**` for it to be **bold**
- wrap text in 3 sets of asterisks `***bold & italic***` for it to be **_bold & italic_**
- wrap text in underscore `_italic_` for it to be _italic_
- wrap text in 2 sets of underscore `__bold__` for it to be **bold**
- wrap text in 3 sets of underscore `___bold & italic___` for it to be **_bold & italic_**
- wrap text with 2 sets of tilda `~~striketrough~~` for it to be ~~striketrough~~

Wes uses underscore for `_italic_` and asterisk for `**bold**` so as not to confuse the readability of his markdown.

## Headings

2 ways to do headings in markdown, using hashes `#` (preferred method) and using 3+ `===` for a H1 or `---` H2 beneath the heading text

- # H1 using `#`
- ## H2 using `##`
- ### H3 using `###`
- #### H4 using `####`
- ##### H5 using `#####`
- ###### H6 using `######`

Github `READNE.md` automatically puts IDs to the headings so that you can link to them through an anchor link e.g. to link back up to [Tooling](#tooling) H2 heading the anchor is `#tooling`

## Links

Links can be created using angle brackets: `<https://masteringmarkdown.com/>` to give <https://masteringmarkdown.com/>

To add a hyper link to text, wrap the text in square brackets with the link in parenthesis immediately after: `[Mastering Markdown](https://masteringmarkdown.com/)` to give [Mastering Markdown](https://masteringmarkdown.com/)

You can also add a title attribute to the hyperlink that'll appear as you hover over the link: `[Mastering Markdown](https://masteringmarkdown.com/ "Markdown course by Wes Bos")` to give [Mastering Markdown](https://masteringmarkdown.com/ "Markdown course by Wes Bos")

To make the markdown more readable, especially when you have long URLs to link to, use a token/key to reference the URL

`[Mastering Markdown][1]` to give [Mastering Markdown][1], where `[1]: https://masteringmarkdown.com/` key can be placed elsewhere in your markdown. This useful for not only readability but also referencing same link in multiple places in your markdown, where if the link changes, you only need to update the link in the key. The key can be anything - a number or string e.g. `[Google][goo]` to give [Google][goo].

[1]: https://masteringmarkdown.com/
[goo]: https://www.google.com/

## Images

The format for images is `![alt text](url)`

- and with optional title attribute `![alt text](url) "title"`
- and using a key `![alt text][key]`

Examples using [Picsum Photos](https://picsum.photos/), the ipsum lorem of photos

600x300
![Snow mountain](https://picsum.photos/seed/picsum/500/300 "Snow mountain")

Greyscale
![Snow mountain greyscale](https://picsum.photos/seed/picsum/500/300?grayscale)

Blurred
![Snow mountain blurred](https://picsum.photos/seed/picsum/500/300?blur)

Blur intensity 2
![Snow mountain blur=2](https://picsum.photos/seed/picsum/500/300?blur=2)

Greyscale and Blur intensity 2
![Snow mountain greyscale blur=2][snow]

[snow]: https://picsum.photos/seed/picsum/500/300?grayscale&blur=2

Add a link to an image using two methods:

- with nested markdown: `[![alt text](url)](url)`
- with HTML img tag: `[<img src="url">](url)`

[![Snow mountain](https://picsum.photos/seed/picsum/50/50 "Snow mountain")](https://picsum.photos/seed/picsum/500/300)

[<img src="https://picsum.photos/seed/picsum/500/300" width="200" height="100" alt="snow mountain">](https://picsum.photos/seed/picsum/500/300)

When you can do something in markdown, you can use regular HTML instead (and CSS through a style tag, thought style tag wont work on github or forums, but would apply in blog posts)

## Lists

Unordered lists (Bullet points) can be created using asterisk `*`, hypen `-` or plus `signs`, and it's useful to switch between these when nesting

- UL 1
  - nested UL 1
- UL 2
  - nested UL 2
- UL 3
  - nested UL 3

* assads
* assd

Ordered lists - good practice to juse use `1.` for all list items, as the markdown editor will increment the number automatically, and that way you dont have to worry about adding more items in the list and re-ordering

1. OL 1
   1. nested OL 1
   1. nested OL 2
1. OL added after
1. OL 2
1. OL 3

   - nested UL 1
   - nested UL 2

     This is a paragraph nested inside UL, done simply by a line space and indenting.

     You can add nested headings, images, links and codeblocks

     codeblock are wrapped in a set of 3 backticks

     ```
     var x = 100;
     ```

## Line Breaks, Horizontal Rules and Block quotes

Line breaks can be added by adding a line space between setences or a break tag `<br>`, though you won't typically need to use a break tag, instead opting for a line space for a new paragraph.

Horizontal rules can be added using 3 hyphens `---` or 3 underscores `___`, and in some editors 3 equals `===`

Block quotes can be added using a chevron `>`

> this is a block quote
>
> add a blank chevron to get a line space/break

## Code Blocks

Developers often write markdown in slack, github, or other tools where you need to document your code.

Simply indenting the code will turn it into a code block or wrap in a set 3 backticks. If you add the language after the first set of backticks, the editor will highlight the syntax according to the language.

A single set of backticks is good for inline code: `var x = 123;`

No formatting, via indenting only:

    var y = 2*x;

Javascript:

```js
var y = 2 * x;
let z = false;
```

Python:

```python
y = 2*x;
z = False
```

Bash:

```bash
echo "hello"
```

Diff can be used to show changes you have made to the code, where the `-` line of code will be highlighted red and the `+` line of code will be highlighted green:

```diff
var x = 123;
- var y = 100;
+ var y = 234;
```

## Tables

Tables are created using pipe `|` to create the table cells. The bit that makes it a table is the row after the column headers where you need to use `|---|` (you can use however many dashes you like) which defaults to left align for the entire column

- `|:---|` for left align
- `|---:|` for right align
- `|:---:|` for center align

Example:

|   Name   | Email        | Phone         |             Title |
| :------: | :----------- | :------------ | ----------------: |
| Jon Snow | jon@snow.com | +1 12 3456789 | King of the North |
| John Doe | jd@jd.com    | +1 13 4567890 |            Nobody |
| Jane Doe | jane@jd.com  | +1 14 5678901 |          Somebody |

## Github Treats

Checkboxes are done via a bullet points/ list and `[ ]` for unchecked or `[x]` for checked

- [x] Learn Markdown - marked as done
- [ ] Learn HTML and CSS
- [ ] leanr JS

1. [x] Learn Markdown - marked as done
1. [ ] Learn HTML and CSS
1. [ ] Learn JS

Link to Github issues and pull requests by using hash `#` then selecting the issue number you wish to reference.

You can reference people's usernames by using `@` and selecting the username.
