#  Sass 
===========

+ Sass stands for Syntactically Awesome Stylesheet
+ Sass is an extension to CSS
+ Sass is a CSS pre-processor
+ Sass is completely compatible with all versions of CSS
+ Sass reduces repetition of CSS and therefore saves time
+ Sass was designed by Hampton Catlin and developed by Natalie Weizenbaum in 2006
+ Sass is free to download and use

+ Sass lets you use features that do not exist in CSS, like variables, nested rules, mixins, imports, inheritance, built-in functions, and other stuff

+ Sass files has the ".scss" file extension.

+ [SASS WebSite](https://sass-lang.com/)


+ [Installation of sass](https://www.youtube.com/watch?v=PJP-CR-9YM4)


## Sass variables

+ Variables are a way to store information that you can re-use later.

+ With Sass, you can store information in variables, like:

  + strings
  + numbers
  + colors
  + booleans
  + lists
  + nulls


+ So, when the Sass file is transpiled, it takes the variables (myFont, myColor, etc.) and outputs normal CSS with the variable values placed in the CSS, like this:

## Sass Nested Rules and Properties


# Sass Nested Rules:
====================
+ Sass lets you nest CSS selectors in the same way as HTML

## Sass Nested Properties:
==========================
+ Many CSS properties have the same prefix, like font-family, font-size and font-weight or text-align, text-transform and text-overflow.

+ With Sass you can write them as nested properties:


### SCSS Syntax:
================

```


font: {
  family: Helvetica, sans-serif;
  size: 18px;
  weight: bold;
}

text: {
  align: center;
  transform: lowercase;
  overflow: hidden;
}
```

### CSS Output:
===============
```
font-family: Helvetica, sans-serif;
font-size: 18px;
font-weight: bold;

text-align: center;
text-transform: lowercase;
text-overflow: hidden;
```


## Sass @import and Partials


* You can create small files with CSS snippets to include in other Sass files. Examples of such files can be: reset file, variables, colors, fonts, font-sizes, etc. 

### Sass Importing Files

* Just like CSS, Sass also supports the @import directive.

* The ```@import``` directive allows you to include the content of one file in another.

* The CSS @import directive has a major drawback due to performance issues; it creates an extra HTTP request each time you call it. However, the Sass @import directive includes the file in the CSS; so no extra HTTP call is required at runtime!

* You do not need to specify a file extension, Sass automatically assumes that you mean a .sass or .scss file. You can also import CSS files. The @import directive imports the file and any variables or mixins defined in the imported file can then be used in the main file.

* SCSS Syntax (reset.scss):

```
html,
body,
ul,
ol {
  margin: 0;
  padding: 0;
}

```

* SCSS Syntax (standard.scss):

```
@import "reset";

body {
  font-family: Helvetica, sans-serif;
  font-size: 18px;
  color: red;
}
```

+ So, when the "standard.css" file is transpiled, the CSS will look like this:

+ CSS output:
```
html, body, ul, ol {
  margin: 0;
  padding: 0;
}

body {
  font-family: Helvetica, sans-serif;
  font-size: 18px;
  color: red;
}
```
### Sass Mixins

+ The @mixin directive lets you create CSS code that is to be reused throughout the website.

+ The @include directive is created to let you use (include) the mixin.

+ Defining a Mixin
+ A mixin is defined with the @mixin directive.

* Sass @mixin Syntax:

```
@mixin name {
  property: value;
  property: value;
  ...
}
```
+ The following example creates a mixin named "important-text":

+ SCSS Syntax:
```
@mixin important-text {
  color: red;
  font-size: 25px;
  font-weight: bold;
  border: 1px solid blue;
}

```
```
Tip: A tip on hyphens and underscore in Sass: Hyphens and underscores are considered to be the same. This means that @mixin important-text { } and @mixin important_text { } are considered as the same mixin!
```
+ Using a Mixin
The ```@include``` directive is used to include a mixin.

+ Sass @include mixin Syntax:
```
selector {
  @include mixin-name;
}
```
+ So, to include the important-text mixin created above:

+ SCSS Syntax:
```
.danger {
  @include important-text;
  background-color: green;
}
```
+ The Sass transpiler will convert the above to normal CSS:

* CSS output:

```
.danger {
  color: red;
  font-size: 25px;
  font-weight: bold;
  border: 1px solid blue;
  background-color: green;
}

```