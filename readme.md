# CSS Layout


### Learning Objectives
- linking files (paths)
- normalize
- relative, fixed, absolute
- floats, clearfix
- block, inline, inline-block
- flexbox
- grids

# You do: Layout Games (30)

Take your time reading [learn layout](http://learnlayout.com/) as you go through it please try out what you're learning in the layout-games exercise.

[layout-games](https://github.com/ga-wdi-exercises/layout-games)

### Questions (10)

# Grids
## Opening Exercise (10)

Whiteboard a wireframe for [Craigslist](http://washingtondc.craigslist.org/).
* Focus on the main components of the page, sections that would be defined by the rows and columns in our grid.
* Don't worry about site content (e.g., text, images).
* Keep an eye out for width, height, proportion, number of components.
* [Sample wireframe.](http://www.comentum.com/images/wireframes-sample/ecommerce/home.png)

## Why use a CSS grid? (5)

### Structure
* Grids are a simple way to apply layout to a webpage. A better layout improves the user experience.
* Grids help avoid stressful CSS debugging by starting out on the right foot.

### Reusability
* Grids make the layout process easier because of resusable, semantically-named "utility classes" (i.e., a library of CSS class selectors).
* Grids aren't limited to a particular project. We can apply them to pretty much everything we do.
* Grids are highly customizable. You can really make them your own.

_Even if you don't use a grid system, these concepts will translate across other layout problems._

### Basic components of a grid (5)

#### Rows
* The highest-level component of a grid.
* Comprised of columns.

#### Columns
* Contain and separate site content.

#### Gutters
* Provides spacing between our columns. Optional, but useful.

## You do: Craigslist-grid  (10)

You don't need a fancy-schmancy front-end framework to reap the benefits of a CSS grid. Let's explore one built from scratch.

[craigslist grid exercise](https://github.com/ga-wdi-exercises/craigslist_grid)

### Clearfix

Our grid relies on being able to float columns. These columns will most likely contain content of various sizes.
* We need to make sure each piece of content is constrained to its respective row and column containers

Let's [illustrate this problem](http://codepen.io/adambray/pen/GoWobo?editors=110).
* As this code stands, we have a row that contains two squares. But these squares are overflowing out of the row, which appears as a straight black line.

This is where the clearfix technique comes in. Fortunately, it's easy to implement (as long as you don't care about how your site looks in Internet Explorer).

```css
.row {
  overflow: auto;
}
```

Here is a more robust version of clearfix and the one you should use most of the time:
```css
.row:after {
  content: "";
  display: table;
  clear: both;
}
```

# You Do: Hyrule Potion Shop (30)

Please count off again, and complete this exercise:

Google is your friend, please look up things you don't know!
These might also help:

- [css-tricks: complete guide to flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [scotch.io: visual guide to flexbox](https://scotch.io/tutorials/a-visual-guide-to-css3-flexbox-properties)

The exercise: [hyrule potion shop](https://github.com/ga-wdi-exercises/hyrule_potion_shop)

### Questions (10)

# Outtro (5)

There are over 500 CSS properties. It's impossible to memorize them. The key is to just get an idea of what you can accomplish with CSS, and then know what to Google.

### Tools that can help

**[The CSS Validator](http://jigsaw.w3.org/css-validator/#validate_by_input)** is a tool into which you can copy and paste your CSS, and it'll tell you precisely what's wrong with it. We'll be expecting you to validate your CSS during this course.

**The Chrome element inspector** lets you look at a specific element on a page, see exactly which CSS rules are being applied to it, and turn those rules on and off and modify them. It doesn't change your file; refresh the page, and the changes are gone.

### Q. What is Bootstrap, and how do you feel about it?

> Bootstrap is a CSS *library*: it's a stylesheet you can link to in your HTML, and it provides you with a bunch of classes that you can apply that make things look really nice.

> Many designers sniff at Bootstrap because, they argue, sites that use it all look the same. However, unless you plan on specializing in front-end design, a Bootstrapped site may be better than a site with no CSS, or a site with handmade CSS: it shows that you recognize what your strengths are and are focused on delivering a product, rather than doing things the "right" way.

There are [many other](http://designsparkle.com/bootstrap-alternatives/) 'design frameworks' that are similar to bootstrap

## Browser Styles (10)

Browsers have default styles for different elements. For example `<body>` tags often have a default margin of ~8px. A `div` element in Chrome will has a height of 18px, in Firefox it's 19.2px. While this difference may be small it does vary. We often start our CSS by overriding, or reseting, some of these default properties:

```css
body {
  margin: 0;
}
```
We can override or work with these default styles on an ad-hoc bassis, simple changing things when they seem appropriate.

#### Reset

An alternative is to use a [CSS Reset](http://meyerweb.com/eric/tools/css/reset/).
To use the reset we can save this into it's own CSS file and link it in our head, or we can copy it into the top of our current CSS file.

- _**Reset removes all built-in styling, essentially provides a blank canvas**_

#### Normalize

Another approach instead of unstyling all of the default properties is to try to work with them. [Normalize CSS](https://necolas.github.io/normalize.css/) seeks to make syles consistent across browsers. Normalize is often linked as file in the project directory, or from a CDN link.

```html
<link rel="stylesheet" href="normalize.css">
/* VS. */
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/normalize/4.0.0/normalize.css">
```

- _**Normalize provides a cross-browser starting point with some properties**_

## Quiz Questions

- What is the purpose of `flex-box`?
- What does `*` select?
- What does `box-sizing:border-box` do?
- What's the difference between `position:relative`, `position:absolute`, and `position:fixed`?
- What's the difference between borders, margins, and padding?
- What's the difference between an outline and a border?
- How would you apply styles only for screens narrower than 480 pixels?

## Further Reading

- [Shay Howe's HTML/CSS Guide](http://learn.shayhowe.com)
- [LearnLayout.com](http://learnlayout.com/)
  - An great interactive tutorial that details CSS' many properties and quirks.
- [W3Schools CSS Reference](http://www.w3schools.com/cssref/default.asp)
  - Almost every CSS property ever.
- [Mozilla Developer Network CSS Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)
  - Like W3Schools, but in *much* more detail.
- [CanIUse.com](http://caniuse.com/)
  - Search for a CSS property (or HTML, or JS), and it'll tell you on which web browsers it functions.
- [CSS Validator](https://jigsaw.w3.org/css-validator/#validate_by_input)
  - Copy and paste your CSS in here and it tells you what's wrong with it.
- [CSS Tricks Almanac](https://css-tricks.com/almanac/)
  - A list of css selectors and properties
- [CSS Units - em vs px etc](http://kyleschaeffer.com/development/css-font-size-em-vs-px-vs-pt-vs/)

## Additional Resources

- [Codrops](http://tympanus.net/codrops/)
- [Codyhouse](https://codyhouse.co/library/)

