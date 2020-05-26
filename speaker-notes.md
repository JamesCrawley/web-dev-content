# Course Content - speaker notes

## Background on DSA & RPT

- Use existing slides, explain plan for 2 days.
- lecture based with labs after
- webex for main call - will post timings for lectures based don how days going.

- Be on main webex all day, but feel free to get coffee etc during labs.
- Use slack for help @help
- Do prior experience poll

## Introduction to HTML

- Hyper Text Markup Language
- As in the name, HTML is a markup language (not a programming/scripting/query) 
- Used to describe the structure and layout of a webpage
- Only need a browser and an editor
- File extension .html or .htm

### HTML Tags

HTML pages are made up of HTML elements (written in the code as tags), which comprise of an opening tag, any amount of content inside, followed by a closing tag. Below is an example of a HTML element
```
<div>Hello world!</div>
```

- `<div>` - The opening HTML tag is the name of the tag surrounded by a pair of angle brackets
- `Hello world!` - The content inside the `div` tag, this can be text, or more HTML tags
- `</div>` - The closing tag is the same as the opening tag, but it has a `/` right before the tag name

---

**Some HTML tags don't have a \</closing> tag!**

---

So we know that HTML tags have their name, and the content that we put inside them. They can also have *attributes*, which let the tag do other things. Attributes go in the opening tag, right before the `>` Below is an example of an attribute on a div element with an attribute called `class`, with a value of `my-first-div`

`<div class="my-first-div">Hello world!</div>`

Here is a list of common HTML tags that we'll be using

**div**  
`<div>Stuff in here</div>`  
Used to create an area on the page that we can put stuff in, and the most commonly used element in HTML!

**paragraph**  
`<p>Text in here</p>`  
Used to put a paragraph of text on a page

**header**  
`<h1>Text in here</h1>`  
Used to create a larger piece of text, ranges from `<h1>`, the biggest, to `<h6>`, the smallest 

**input**
`<input type=""/>`
Used to create an input on a page for many different types (text, file, checkbox, radio button etc)

**button**
`<button>Click me!</button>`
Used to create a button on a page that can trigger JavaScript code

### Page Structure

All HTML files have a similar structure that they need to be in so that the 
- Head and body
- Head – things like page title, metadata (description, key words), links to CSS or JS files
- Body – the actual elements that are going to display in the browser
- Very basic example of a page:

```html
<!DOCTYPE html>
<!--declaration telling the browser that this is a html file-->
<html>
  <head>
    <title>My Webpage</title>
    <!-- will show in the tab -->
  </head>
  <body>
    <h1>My First Header</h1>
    <!-- biggest heading there is, goes down to 6 -->
    <p>My First Paragraph</p>
  </body>
</html>
```

## Challenge 1 - HTML

- Create a HTML page with some elements on it:

  - (At least) 2 sizes of headers
  - Some paragraph text
  - An input box, with a button that says “search”
  - An unordered list with some items in it

- The page should also contain the following meta information;

  - Charset should be specified as `UTF-8`
  - The page should have a title

## Introduction to CSS

- styling language, not programming language
- HTML is used for content, CSS is used for styling of that content
- simple syntax: selector and properties
  selector {
  property1: value;
  property2: value;
  }
- the selector is the element that we are applying properties to
- best way to load CSS into our HTML is by having a separate CSS file and using a link inside the head of the HTML
  ```html
  <head>
    <link rel="“stylesheet”" href="styles.css" />
  </head>
  ```
- having an external css file separates content from styling and supports reusability

### Main Selectors

1. element (could be any HTML element: h, p, div, header, footer etc.)

```css
h1 {
  color: blue;
}
```

2. class (lets you select HTML elements based on their class)

```html
<h1 class="big-header">
  Title
</h1>
```

- to select elements by class, we need to use a . to tell CSS that this is a class and not an element
  .big-header {
  color: blue;
  }
- most used selector, great for creating reusable content (example buttons)

### The div Tag

- the `<div>` tag defines a division or a section in an HTML document
- the `<div>` element is often used as a container for other HTML elements to style them with CSS or to perform certain tasks with JavaScript
- by wrapping a set of paragraph elements into a `<div>` element, we can take advantage of CSS styles and apply a font to all paragraphs at once by applying a font style to the `<div>` tag instead of coding the same style for each paragraph element

### Nesting

- to avoid using too many class or other selectors, we are going to be nesting our css, meaning that we will specify properties to selectors within other selectors, as below:

```html
<div class="“recipe”">
  <h1>Chocolate cake</h1>
  <p>This is my recipe for making chocolate cake</p>
  <p>This is totally not healthy</p>
</div>
```

```css
.recipe {
  background-color: #ccc;
  padding: 10px;
}
.recipe h1 {
  color: #ff0;
}
.recipe p {
  color: red;
  font-weight: bold;
}
```

- this removes the need for classes or IDs on the p and h1 tags
- by separating selectors with spaces, we are saying “h1 inside the class called recipe is colour #ff0" and “p inside the class called recipe is red and bold”
- using nesting in css increases the modularity and maintainability of stylesheets

## Challenge 2 - CSS

- Now style your page, using the following guides:

  - The page should have a new font
  - The Headers should have a different font size
  - Each different section should have a different background colour
  - The title should be centered on the page
  - Clicking on one element (could be anything) takes you to another webpage (e.g. google.com)
  - The background of the page should either be an image (any image), or a colour gradient.
  - Using the browser inspector, inspect and modify an element on the fly (change a colour or something idk)

## Introduction to CSS Grid

CSS Grid is used to build parts of a webpage using columns and rows, with many ways to create complex structures!

You can also put grids within grids, allowing you to have infinitely complex layouts

We'll also be using a new unit of size, the fraction (`fr`). This unit is only really used in grids, and helps to create rows and columns using proportions of the grid size rather than fixed using pixels.

### Lets make a grid...

Let's start by setting up our files!

1. Create a new folder called 'CSS Grid Lab' on your desktop, or anywhere else you'd like
2. Open up VSCode
3. Click on 'File' at the top of VSCode and click 'Open...'
4. Navigate to and click on the folder you created (make sure you don't go into the folder!), and click 'Open'
5. In this sidebar you'll see a few icons, once will create a new **file** and one will create a new **folder**
   ![](https://imgur.com/NCJS13H.png)
6. Create two new files called **grid.html** and **grid.css**, these will be the two files that we write our CSS Grid code in!

Now that we have created our files, you can copy the code below, and paste it into **grid.html**

```
<!DOCTYPE html>
<html>
  <head>
    <link rel="stylesheet" href="grid.css" />
    <link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Sans&display=swap" rel="stylesheet">
  </head>
  <body>

  </body>
</html>
```

**All of the HTML code that we will be adding will go inbetween the `<body>` and `</body>` tags!**

Start by creating a `<div>` tag and giving it a class of `my-grid`

```
<div class="my-grid"></div>
```

Next, create a CSS selector with this basic styling in your `grid.css` file for your `my-grid` class. Remember as `my-grid` is a class, it needs a `.` at the start of the selector!

```
.my-grid {
  width: 20vw; /* 20% of the width of the page */
  height: 50vh; /* 50% of the height of the page */
  background-color: lightblue;
}
```

We need to tell the browser to use this element as a grid, so add `display: grid;` to your selector

```
.my-grid {
  width: 20vw; /* 20% of the width of the page */
  height: 50vh; /* 50% of the height of the page */
  background-color: lightblue;

  display: grid;
}
```

You can use `grid-template-columns` to define how many columns will be in your grid (the same goes for `grid-template-rows`), there is a specific way to use this. For example, the following code

```
grid-template-columns: 20px auto 2fr 1fr;
```

- Will create 4 columns (the number of parts that are after the `:`)
- The first column will be 20px wide
- The second column will be as wide as it needs to be to fit its content
- The third column will be 2 fractions of the remaining width of the grid
- The fourth column will be 1 fraction of the remaining width of the grid

We won't be making any grids this complex yet, so let's add this code to our CSS selector in `grid.css` file

```
grid-template-columns: 1fr 1fr;
grid-template-rows: 1fr 1fr;
```

This is telling our grid to have 2 columns and 2 rows, each column is one fraction (ie the same ratio) of the total width of the grid, so they are going to be the same size which works out at 50% width each. The same goes for the rows, just with the height of the grid instead of width.

Now that our grid is set up, we need to add some children to it in the HTML! Inside the `<div class="my-grid"></div>` tags, add **4** of these `div` elements (with a different number inside each)

```
<div class="my-grid-child">1</div>
```

So now your HTML should look like this:

```
<div class="my-grid">
  <div class="my-grid-child">1</div>
  <div class="my-grid-child">2</div>
  <div class="my-grid-child">3</div>
  <div class="my-grid-child">4</div>
</div>
```

CSS Grid is pretty smart, so it can work out how many children to expect based on the CSS code we wrote. As we told it to have 2 columns and 2 rows, it will expect 4 children, which we gave it with the HTML elements we just added in!

Find your `grid.html` file and open it in a browser such as Chrome or FireFox, you should see something like this

![](https://imgur.com/pTFBUq0.png)

It might look a bit rough, but the grid is now in place! We can tidy it up a bit by adding the following code to the `my-grid-child` selector in `grid.css`

```
text-align: center;
font-family: "IBM Plex Sans";
font-size: 30px;
```

Just a few lines of code makes it look a lot better!

![](https://imgur.com/WEvRZjy.png)

---

**Top Tip**

Add the following code to the `my-grid-child` selector in `grid.css` to visually see each section of the grid!

```
border: 1px solid black;
```

---

## Challenge 3 - CSS Grid

- Add some more classes to change the colour of each section

- Make the grid bigger!

- If this is just too easy, then take a look at [grid-template-areas](https://tinyurl.com/GridTemplateAreas), and try and make something that looks like [this](https://imgur.com/qzbM3t5.png)!

## Introduction to Flex

FlexBox, also known as Flex, is similar to CSS Grid in that it allows you to structure your webpage, but it does so a slightly different way.

A good way to think of it is that CSS Grid is two-dimensional, as you can have multiple rows and columns in a grid, whereas Flex is one-dimensional, and will only have one column **or** one row. When creating a Flex element, you define a property called `flex-direction`, which tells the browser to flow the Flex as a row (horizontally), or as a column (vertically). These images show how the content inside a Flex flows depending on the `flex-direction`

![](https://imgur.com/vUrxecm.png)

![](https://imgur.com/8UiP99D.png)

To get started, create a div element in your HTML and give it a class (we'll use the class `my-flex`):

```
<div class="my-flex"></div>
```

Now, create a CSS selector for that class so that we can style it! We'll give it a few properties here such as `background-color`, `width` and `height` just so that it looks nice and tidy!

```
.my-flex {
  width: 20vw; /* 20% of the width of the page */
  height: 80vh; /* 80% the height of the page */
  background-color: lightblue;
}
```

Similar to declaring a grid, we'll give the div a `display` property, but with the value `flex` instead of `grid`

```
.my-flex {
  width: 20vw; /* 20% of the width of the page */
  height: 80vh; /* 80% the height of the page */
  background-color: lightblue;

  display: flex;
}
```

Now that the browser knows that the div is a Flex, we need to decide which way we want the Flex to flow across the page (horizontally or vertically). We want to make a list display from top to bottom, so we need to set the `flex-direction` to `column`

```
.my-flex {
  width: 20vw; /* 20% of the width of the page */
  height: 80vh; /* 80% the height of the page */
  background-color: lightblue;

  display: flex;
  flex-direction: column;
}
```

---

**`flex-direction` has a default value of `row`, so if you want it to be a row, you don't even need to use the `flex-direction` property!**

---

We can now add in the children as we did for the CSS Grid, add 4 `<div>` elements as children of `<div class="my-flex"></div>`, and give them the class `my-flex-child`

```
<div class="my-flex">
  <div class="my-flex-child">1</div>
  <div class="my-flex-child">2</div>
  <div class="my-flex-child">3</div>
  <div class="my-flex-child">4</div>
</div>
```

We can now style these children! Create a new CSS selector in `flex.css` targeting the children, and give them a bit of styling

```
.my-flex-child {
  height: 100px;
  background-color: orange;
}
```

If you open `flex.html` in your browser, you should see something like this

![](https://imgur.com/1tRprhj.png)

There's one more property we're going to add to our code called `justify-content`, This property tells the Flex element how to space the children inside it.

Add the `justify-content` property to the `my-flex` selector in `flex.css`, and try out the values `space-around`, `space-between` and `space-evenly` to see how they make the Flex look.

## Challenge 4 - CSS Flex

- Using what you've learnt so far about CSS Grid and Flex, make your webpage look like this [example](http://my-tv-favourites.eu-gb.mybluemix.net/)

- Don't worry about any of the functionality yet, we just want to make it look pretty!

- This will take a bit of time, so please ask any of us for a hand :)

## Introduction to JavaScript

- JS makes the web interactive. It's _not_ java!
- We'll teach the basics of the programming language, but there's lots more to be done independently
- output (console.log), comments, how to access dev tools
- variable assignment - storing bits of info (const/let)
- more assignment - ++, +=
- operators (+/- etc)
- comparisons - ==, !=, ===, !==, >, <
- conditionals - if/else: (mention booleans)
  - if (thing){
    // do thing
    }
  - else comes after if
- Arrays and objects
  - basic array declaration
  - objects:
  ```js
  let person = {
    age: 20,
    name: "phil",
    likes: ["dogs", "cats"],
  };
  ```
- JS methods - look on w3schools for methods (e.g. `.length`,`.indexOf(substr)`)

## Challenge 5 - Javascript Basics

- Print out your name with a message (like 'Hello there <person>')
- Create 2 variables, a & b and assign different numbers to them. Then do some multiplication, division, addition, and subtraction, with them.
- Create a new variable, x, and assign it the number 2 like so: `const x = "20"`. Add that to one of your previous variables. What do you notice? Why do you think that is?
- Create an array, filled with names, then use a loop to print out their name & the same message for each one. You should end up with something like "Hey bill", "Hey Fred", "Hey Sally", etc.
- Create a variable called age and assign it to your age. Use an if/else statement to tell you if you're allowed to legally drink
- Create another variable called `likesBeer` and assign it to a boolean (true or false). Modify your existing loop so that if you're over 18 & like beer, it say you can drink. If not, print out a message to say no.
- Using the following object, print out the ID & price of each item.

  ```js
  let items = [
    { id: 1, price: 20 },
    { id: 2, price: 30 },
    { id: 3, price: 10 },
    { id: 4, price: 230 },
    { id: 5, price: 1 },
  ];
  ```

- Using the same object, sum the total cost of all items.

  > note: there's (at least) 2 ways of doing this - if you're looking to stretch yourself, look at a `reduce()` function!

- For an additional challenge - write a check for palindrome - taking a variable (such as `const input = "hello there") and returning (outputting) a "true" or "false". If it's the same in reverse it should tell you. e.g inputting "racecar" should output true, but "nope" should be false

## Going further with JavaScript

- Functions - bit of code you can reuse
- Including JS on the page with `<script>` tags
- Explain DOM & interacting with it

  - 4 lines:

  ```js
  const el = document.querySelector("#el"); // copies element into JavaScript
  const newEl = document.createElement("li"); // create new element as variable
  newEl.innerHTML = "content"; // filling the element
  el.appendChild(newEl); // attaches the new element back into the DOM
  ```

  - Adding event listener:

  ```js
  const el = document.querySelector("#button"); // copies element into JavaScript
  el.addEventListener("submit", (e) => {
    // declare submit event
    e.preventDefault(); // prevent sending HTTP request to submit
    console.log("clicked"); // do stuff
  });
  ```

  - Async/await (explain async)

  ```js
  async function callAPI(query) {
    // run inside an async function
    const res = await fetch(`http://api.tvmaze.com/search/shows?q=${query}`); // make API call (await tells us to wait for)
    const results = await res.json(); // wait for results to come in
    console.log(results); // do something directly with the results
  }
  ```

## Challenge 6 - Including JavaScript on the page, and JavaScript API calls with async/await

- Include some JavaScript directly onto your html page. Make it `console.log()` the word "test".
- Make an alert box pop up when you open the webpage. Customise the message.
- Make an alert box pop up when you press a button.
- Make an element appear on the page when you press a button
- Create the following user story:
- Users can enter a TV show and press search. When they do, they will see their query added to a list underneath.
- Use the `await` syntax to make an API call to the TVMaze API. Hard-code the query to be your favourite TV show. Use a `console.log` to simply print out the results.
- Create the following user story:
- Users can search for a TV show, and be shown a list of matching responses as a list on the page below.
- Create the following user story:
- Users can search for a TV show, and be shown a list of matching responses as a list on the page below. Pressing the star (or similar) icon will add the show to a different list of their favourites.
