# How to use theme

## Get Started
Using Theme Academic PP is based on the normal Vivliostyle creation process.  
Please refer to the official Vivliostyle [documents](https://docs.vivliostyle.org/#/create-book).

Create a template for your publication using `Create Book`, choose `vivliostyle-theme-academic-pp` in the choose theme selection.  
You can then create a publication using Theme Academic PP. From then on, please follow the documents to prepare your manuscript.

## Functions
Theme Academic PP is based on @vivliostyle/theme-academic, so it consists of functions derived from @vivliostyle/theme-academic and functions unique to Theme Academic PP.  
Basically, you can use both functions.

See @vivliostyle/theme-academic author's article below for @vivliostyle/theme-academic derived features. (in Japanese)  
[@vivliostyle/theme-academic でレポート書いてみた！](https://vivliostyle.github.io/vivliostyle_doc/ja/vivliostyle-user-group-vol4/artifacts/content/yamasy/index.html)

Unique functions of Theme Academic PP include.

- Two-Column Layout
- Image Row
- Abstract
- KeyWords
- Font Selection
- Compact Mode
- External Page Annotations

### Columns Layout
You can choose between 1-column (standard) and 2-column formatting. 2-column formatting is a format in which text is divided vertically into two groups for layout.  

![2-column sample](../_img/2columns.png ':size=900')

To use a two-column layout, add the following YAML front matter at the beginning of the Markdown file. For a single-column layout, either leave it unspecified or set `column: '1'`.

```md
---
body:
  column: '2'
---
```

When two columns are set, the [Abstract](en/guide?id=Abstract) and [Keywords](en/guide?id=Keywords) sections are excluded from the columns and spread across the entire width of the page.  
If a class named `column-span` is added, the element will be excluded from the columns.

```md
<div class="column-span">

This text section is excluded from the columns.

</div>
```

### Image Row
You can arrange multiple images in parallel.

Display any number of images inside a div element with the class name `image-row`, as shown below. Make sure to leave a blank line between the div tag and the image tags.

```md
<div class="image-row">

![](Image Link 1)

![](Image Link 2)

</div>
```

?> There is no limit to the number of images that can be arranged in parallel, but it is recommended to use 2 or 3 images depending on their size.

### Abstract
You can write an abstract for the manuscript.

![Abstract sample](../_img/abstract-keywords.png ':size=600')

Write the abstract inside a div element with the class name `abstract`, as shown below. Be sure to leave a blank line between the div tag and the text.

```md
<div class="abstract">

Write the abstract of the manuscript here...

</div>

```

You can also customize the title of the abstract using the YAML front matter. Add the following YAML front matter:

```md
---
html:
  abstract-title: 'true'
---
```

The available values are as follows:

|Value|Title Display|Language|Notes|
|---|---|---|---|
|true|Enabled|Based on manuscript settings	|Default|
|false|Disabled|||
|en|Enabled|English||
|ja|Enabled|Japanese||

### Keywords
You can list keywords for the manuscript.

![Keywords sample](../_img/abstract-keywords.png ':size=600')

Write the keywords inside a div element with the class name `keywords`, as shown below. Be sure to leave a blank line between the div tag and the keywords.

```md

<div class="keywords">

**Bold Keyword 1**, **Bold Keyword 2**, Keyword 3, Keyword 4

</div>

```

As shown in the example, enclosing text in ** makes it bold. However, the text "KEY WORDS" cannot be changed.

### Compact Mode
You can condense the entire text to reduce space usage on the page.  
This mode decreases the font size of both the main text and headings.

To enable compact mode, set the following YAML front matter:
Available values are true and false. The default is false.

```md
---
html:
  compact-text: 'true'
---
```

### Font Selection
You can specify the font type used for headings.

Set the font type in the YAML front matter as follows:
Available values are Sans serif (`sans-serif`) and Serif (`serif`). The default is sans-serif.

```md
---
html:
  section-font: 'serif'
---
```

### External Page Annotations
You can configure the presence of the page counter at the bottom center of the page and the title at the upper left.

To set this up, specify the following in the YAML front matter:

```md
---
html:
  page-counter: 'false'
  pub-title: 'false'
---
```

The configuration options are as follows.  
If the value is true, the element will be displayed; if false, it will be hidden.

|Configuration Item	|Key|Value|
|---|---|---|
|Display of Page Counter|html:page-counter|true/false|
|Display of Title|html:pub-title|true/false|