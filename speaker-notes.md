# Course Content - speaker notes

## Background on DSA & RPT

- Use existing slides, explain plan for 2 days.
- lecture based with labs after
- webex for main call - will post timings for lectures based don how days going.

- Be on main webex all day, but feel free to get coffee etc during labs.
- Use slack for help @help
- Do prior experience poll

## Introduction to HTML

HTML (Hyper Text Markup Language) is a language that makes up every single website that exists, all it does is tell your browser where to put things on the page. It is very simple in itself, but it can be (and often is) paired with CSS (Cascading Style Sheets) to style the page such as adding colour, changing fonts, the sizing of elements and much more. HTML can also be used with JavaScript to make the page functional and responsive, allowing the developer to program it to perform complex actions such as handle data, communicate with servers and more.

### HTML Tags

HTML pages are made up of HTML elements (written in the code as tags), which comprise of an opening tag, any amount of content inside, followed by a closing tag. Below is an example of a HTML element:
```
<div>Hello world!</div>
```

- `<div>` - The opening HTML tag is the name of the tag surrounded by a pair of angle brackets
- `Hello world!` - The content inside the `div` tag, this can be text, or more HTML tags
- `</div>` - The closing tag is the same as the opening tag, but it has a `/` right before the tag name

---

**Some HTML tags don't have a \</closing> tag!**

---

So we know that HTML tags have their name, and the content that we put inside them. They can also have *attributes*, which let the tag do other things. Attributes go in the opening tag, right before the `>` Below is an example of a div element with an attribute called `class`, with a value of `my-first-div`:

`<div class="my-first-div">Hello world!</div>`

Here is a list of common HTML tags that we'll be using

---

**div**  
```html
<div>Stuff in here</div>
```  
Used to create an area on the page that we can put stuff in, and the most commonly used element in HTML!

---

**paragraph**  
```html
<p>Text in here</p>
```  
Used to put a paragraph of text on a page

---

**header**  
```html
<h1>Text in here</h1>
```  
Used to create a larger piece of text, ranges from `<h1>`, the biggest, to `<h6>`, the smallest 

---

**list item**  
```html
<li>This is a list item</li>
```  
Used to add items to an (un)ordered list

---

**unordered list**  
```html
<ul>
  <li>Flour</li>
  <li>Water</li>
  ...
</ul>
```  
Used to create an unordered list of bullet points

---

**ordered list**  
```html
<ol>
  <li>Mix the flour and water together</li>
  <li>Put in the oven</li>
  ...
</ol>
```  
Used to create an ordered, numbered list

---

**input**  
```html
<input type="text"/>
```  
Used to create an input on a page for many different types (text, file, checkbox, radio button etc)

---

**button**  
```html
<button>Click me!</button>
```  
Used to create a button on a page that can trigger JavaScript code

---

**You can also write comments in HTML files that don't affect anything, they're just there to help you note things down!**  
```html
<!-- this is a comment! -->
```

---

### Page Structure

All HTML files have a similar structure that they need to be in so that the browser knows how to interpret them
- `<!DOCTYPE>` tag - telling the browser that this is a HTML document
- `<html>` tag - telling the browser that all of your webpage content is inside of this tag
- `<head>` tag – things like page title, metadata (description, key words), links to CSS or JS files go in here, nothing in here is displayed on the page
- `<body>` tag – everything else; the actual elements that are going to display in the browser go here
  
Here is a very basic example of a page

```html
<!DOCTYPE html>
<html>
  <head>
    <title>My Webpage</title>
  </head>
  <body>
    <h1>My First Header</h1>
    <p>My First Paragraph</p>
  </body>
</html>
```

### Nesting

HTML elements are nested, meaning that they can be put inside of each other to structure the page in different ways. Below is an example of a few nested HTML elements:
```html
<div> <!-- parent element -->
  <h1>Hello world!</h1> <!-- child element 1 -->
  <p>Hello world! (but smaller)</p> <!-- child element 2 -->
</div>
```

In the example above, the `<div>` has two **children**, `<h1>` and `<p>`. Therefore, the `<h1>` and `<p>` are **siblings**, and the `<div>` is their **parent**.

## Challenge 1 - HTML

- Create a HTML page with some elements on it:

  - (At least) 2 sizes of headers
  - Some paragraph text
  - An input box, with a button that says “search”
  - An unordered list with some items in it

- The page should also contain the following meta information:

  - Charset should be specified as `UTF-8`
  - The page should have a title

## Introduction to CSS

CSS (Cascasding Style Sheets) is a styling language that is used to style HTML pages to make them much more user friendly and appealing. You will find CSS on pretty much every website that exists as without it they would look **extremely** basic. CSS is used to changethings such as colours, fonts, sizes as well as positioning of elements using margin, padding as well as more complex properties such as grids and flexboxes. CSS is a written in a **very** simple format, making it easy to learn alongside HTML even if you're a beginner!

### Creating a CSS file and linking it to your HTML document

The first thing you need to do is create a CSS file, call it whatever you want as long as it has the .css file extension, a common name is `styles.css`.

The next thing to do is to link it to your HTML document, the code below goes inside the `<head> </head>` tags in your HTML document, all it does is point to your .css file. Just make sure that the name in `href=""` matches the name of the CSS file you have created!
```html
<link rel="“stylesheet”" href="styles.css" />
```

### CSS Selectors

CSS uses *selectors* to target parts of a HTML page, and then applies properties to them such as `width`, `height`, `background-color` etc. Below is an example of a typical CSS selector:
```css
p {
  background-color: red;
  color: white;
}
```

This selector is targeting **every** `<p>` element in our HTML page, and applying the styles inside the selector, making the background colour red and the foreground (text) colour white.

### Classes and IDs

Selectors can target HTML elements as above, but instead of this we usually target elements using classes or IDs. These are a way to target individual elements on a page and create groups for elements that you want to have the same styling. In reality, we only really use classes, the only difference between then being that **a class can be applied to as many elements as you want**, whereas **an ID can only be applied to one element**.

The code below shows how to apply a class to a HTML element:

```html
<p class="my-paragraph">
  Hello world!
</p>
```
```css
.my-paragraph {
  background-color: lightgrey;
  color: white;
  font-size: 24px;
  font-family: 'IBM Plex Sans'
}
```

The code below shows how to apply an ID to a HTML element:

```html
<p id="my-paragraph">
  Hello world!
</p>
```
```css
#my-paragraph {
  background-color: lightgrey;
  color: white;
  font-size: 24px;
  font-family: 'IBM Plex Sans'
}
```

---

**In the CSS, `.` is used to identify a class, and `#` is used to identify an ID**

---

## Challenge 2 - CSS

- Now style your page, using the following guides:

  - The page should have a new font
  - The headers should have a different font size
  - Each different section should have a different background colour
  - The title should be centered on the page
  - Clicking on one element (could be anything) takes you to another webpage (e.g. google.com)
  - The background of the page should either be an image (any image), or a colour gradient.
  - Using the browser inspector, inspect and modify an element on the fly (change a colour or something)

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

---

**All of the HTML code that we will be adding will go inbetween the `<body>` and `</body>` tags!**

---

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
