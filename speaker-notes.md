# Course Content - Speaker Notes

## Contents
- [Introduction to HTML](#introduction-to-html)
- [Introduction to CSS](#introduction-to-css)
- [Introduction to CSS Grid](#introduction-to-css-grid)
- [Introduction to CSS Flex](#introduction-to-css-flex)
- [Introduction to JavaScript](#introduction-to-javascript)
  - [Expressions](#expressions)
  - [Variables](#variables)
  - [Data Types](#data-types)
  - [Arrays](#arrays)
  - [Objects](#objects)
  - [Outputting to the Console](#outputting-to-the-console)
  - [Comments](#comments)
  - [Operators](#operators)
    - [Assignment Operators](#assignment-operators)
    - [Arithmetic Operators](#arithmetic-operators)
    - [Comparison Operators](#comparison-operators)
    - [Relation Operators](#relational-operators)
    - [Logic Operators](#logic-operators)
  - [Conditional Statements](#conditional-statements)
  - [Array Functions](#array-functions)
- [Challenge 5 - JavaScript Basics](#challenge-5---javascript-basics)
- [Going further with JavaScript](#going-further-with-javascript)
  - [Functions](#functions)
  - [Including JS in a HTML Page](#including-js-in-a-html-page)
  - [Interacting with the DOM](#interacting-with-the-dom)
  - [Asynchronous JavaScript](#asynchronous-javascript)

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
```html
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

Here is a list of common HTML tags that we'll be using:

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

**style**  
```html
<style>// CSS goes in here</style>
```  
Used to embed CSS styling directly into a HTML document

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

### Margin and Padding

Margin and padding are properties in CSS used to create space inside and outside of items. They do a very similar thing, but in slightly different ways.

**Padding** creates space **inside** of a HTML element

**Margin** creates space **outside** of a HTML element

I created a grey square that is 100px wide, put a smaller orange square that is 50px wide inside it, and a 50px green square below it. This is what it looks like without any margin or padding:

![](https://i.imgur.com/nNwrAhG.jpg)

By default, HTML elements sit as far to the top left as they can, if I wanted to move the orange box away from the edge of the grey box, I can add `padding: 10px` to the grey box:

![](https://i.imgur.com/ipczxiQ.jpg)

---

`padding: 10px` adds padding to **all** sides of the grey box, if you only want to add padding to one side you could use `padding-left`, `padding-right`, `padding-top` or `padding-bottom`, this works exactly the same for margin as well!

---

I can use the Chrome DevTools to hover over the grey box to visually see where the padding is, the green outline inside the grey box shows the padding that is pushing the orange box 10px inwards:

![](https://i.imgur.com/888RcXp.jpg)

Now we can move the green box away from the grey box, shown below is the result of adding `margin-bottom: 10px` to the grey box:

![](https://i.imgur.com/Nlc8KNt.jpg)

And if I hover over the grey box again, I can see the 10px of margin that has been added to the bottom of the grey box, shown highlighted in orange:

![](https://i.imgur.com/Xz6e7ea.jpg)

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
JavaScript makes the web interactive. It's _not_ java! We'll teach the basics of the programming language, but there's lots more to be done independently

### Expressions
  - Expressions are one of the fundamental principles behind JavaScript logic, essentially it is a bunch of *values* and *operators*, that result in a return value, here are a few examples:
  ```js
  const myName = "James" // this is a variable callde myName with the value of "James"
  
  // this is an expression that returns the value "My name is James"
  "My name is " + myName
  
  // this is also an expression, but returns the value 19
  9 + 10
  ```
  
### Variables
  - Variables can be looked at as pockets where you can store data, identified by their unique names
  - The data that variables store can be in many different data types (see section below), such as *strings*, *numbers* and *booleans* to name a few
  - Unlike other programming languages, in JavaScript you don't need to tell the code what data types you want your variables to be. This led to the creation of the [TypeScript](https://www.typescriptlang.org/) language by Microsoft
  - To create a variable you need to know:
    - Whether to use *let* or *const* (*let* variables can change, *const* variables can't)
    - The name of the variable (can only contain alphanumeric characters, no symbols)
    - A value to give to the variable (optional for *let*, required for *const*)
    
  - How to create a variable:
    - const (value of variable must be set at variable creation and cant be changed after)
    ```js
    const myConstant = 5 // this can't be changed
    myConstant = "Hello!" // TypeError: Assignment to constant variable.

    const myName; // SyntaxError: Missing initializer in const declaration
    ```
    
    - let
    ```js
    let myVariable = "Hello!"
    console.log(myVariable) // Hello!

    myVariable = "Hello world!"
    console.log(myVariable) // Hello world!
    ```
    
    - var (we don't use this one since let was introduced)
    
### Data types
  - Data types define the format that a piece of data is in. It can be from one of the folowing (as well as many more)
    - String: Any form of text
    ```js
    const name = "James" // this is a string
    console.log("My name is " + name) // James
    ```
    
    - Number: Any whole number
    ```js
    const age = 20 // this is a number
    console.log("I am " + age + " years old")
    ```
    
    - Boolean: A true or false value
    ```js
    const canDrive = true
    console.log(canDrive ? "Yes!" : "No!") // Yes!
    // ^ we'll explain what this means later ^
    ```
    
### [Arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
  - Arrays are another data type, they are essentially a list of elements
  - Arrays can contain many different types
  - Each item in the array is called an *element*
  - Arrays are written using square brackets with commas to seperate the elements 
  ```js
  const myArray = ["Apple", 5, true, "Orange"]
  ```
  
  - Each element has an index (position in the array) starting at 0. The first element is index 0, the second is 1 etc. Here is how you would index each element of the array:
  ```js
  console.log(myArray[0]) // Apple
  console.log(myArray[2]) // true
  console.log(myArray[4]) // undefined (index 4 (the 5th element) doesn't exist)
  ```
  
  - There are many methods you can use to modify arrays:
  ```js
  const myArray = [1, 2, 3, 4, 5]
  
  // returns the number of items in the array, starting from 1 not 0
  console.log(myArray.length) // 5
  
  // adds the element(s) to the end of the array and returns the new length of the array
  console.log(myArray.push(6)) // 6 
  console.log(myArray) // [1, 2, 3, 4, 5, 6]
  
  // removes the last element of the array and returns it
  console.log(myArray.pop()) // 6
  console.log(myArray) // [1, 2, 3, 4, 5]
  
  // adds element(s) to the start of the array and returns the new length of the array
  console.log(myArray.unshift(0)) // 6
  console.log(myArray) // [0, 1, 2, 3, 4, 5]
  
  // removes the first element of the array and returns it
  console.log(myArray.shift()) // 0
  console.log(myArray) // [1, 2, 3, 4, 5]
  ```
  
### [Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
  - Objects are also another data type, written using curly braces. They contain data (known as *properties*) stored as key-value pairs
  ```js
  let person = {
    name: "James", // property called 'name' with the value of "James"
    age: 20, // property called 'age' with the value of 20
  };
  ```
  
  - The properties of objects can be accessed and changed using the *dot notation*
  ```js
  console.log(person.name) // "James"
  console.log(person.age) // 20
  
  person.age = 99 // set the age property to 99
  console.log(person.age) // 99
  ```
  
  - Objects and arrays are commonly used together to chain up complex amounts of data together
  ```js
  const james = {
    name: "James",
    age: 20,
    likes: ["cars", "dogs"]
  }
  
  const collwyn = {
    name: "Collwyn",
    age: 20,
    likes: ["japan", "vr"]
  }
  
  const people = [james, collwyn]
  console.log(people) // copy/paste this section of code into your browser's console and see what it returns
  ```

### Outputting to the console
  - This is used to log the values of variables and expressions to the developer console
  - It is very useful for debugging and testing code 
  ```js
  console.log(1 + 1) // 2
  console.log("Hello world!") // Hello World!
  console.log(50 + 50 === 100) // true
  console.log([1, 2, 4, 5].includes(3)) // false
  
  // you can also use
  console.warn()
  
  // and
  console.error()
  
  // to display yellow and red messages to the console
  ```
  
### [Comments](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#Comments)
  - Comments are used to annotate and describe your code
  - Single line comments are written using double forward-slashes
  ```js
  // this is a comment and won't affect the code in any way!
  let number = 5
  console.log(number) // 5
  
  // number = 10
  console.log(number) // 5
  ```
  
  - Multi-line comments are written using a forward slash and an asterisk (/\*) and the reverse to close it (\*/)
  ```js
  let number = 5
  console.log(number) // 5
  
  /*
  number = 6
  number = 7
  number = 9
  */
  console.log(number) // 5
  ```
  
### [Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators)
#### [Assignment operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#Assignment_operators)
  - These are used to change the value of a variable
  ```js
  let myNumber = 0;

  // assignment (=)
  myNumber = 5 // set myNumber to 5
  console.log(myNumber) // 5

  // addition assignment (+=)
  myNumber += 7 // add 7 to myNumber
  console.log(myNumber) // 12

  // subtraction assignment (-=)
  myNumber -= 2 // minus 2 from myNumber
  console.log(myNumber) // 10

  // multiplication assignment (*=)
  myNumber *= 5 // multiply myNumber by 5
  console.log(myNumber) // 50

  // division assignment (/=)
  myNumber /= 2 // divide myNumber by 2
  console.log(myNumber) // 
  ```

#### [Arithmetic operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#Arithmetic_operators)
  - These are used to add values together (and concatenate strings)
  ```js
  // addition (+)
  console.log(10 + 4 + 6) // 20
  console.log("Hello" + " " + "World!") // Hello World!

  // subtraction (-)
  console.log(6 - 4) // 2

  // multiplication (*)
  console.log(5 * 5) // 25

  // division (/)
  console.log(100 / 25) // 4

  // remainder (%)
  // this basically does 10 divided by 3, and then returns the remainder
  console.log(10 % 3) // 1

  // exponents/power (**)
  // 2 to the power of 3
  console.log(2 ** 3) // 8

  // these can be chained up using brackets to change the order of precedence
  // this evaluates as (5) * 3, then to 15
  console.log((50 / 10) * 3) // 15
  ```

#### [Comparison operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#Equality_operators)
  - These are used to compare the values of two pieces of data
  ```js
  // equality operator, compare the values only, in JavaScript the number 20 and the string "20" are identical values
  console.log(10 == "10") // true

  // inequality operator (the opposite of equality)
  console.log(10 != "10") // false

  // identity operator, compare the values and the types, their values are identical but their types aren't, as one is a number and the other is a string
  // use this operator 99% of the time instead of the equality operator
  console.log(10 === "10") // false

  // non-identity operator (the opposite of identy)
  // use this operator 99% of the time instead of the inequality operator
  console.log(10 !== "10") // true
  ```

#### [Relational operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#Relational_operators)
  - These are used to compare values based on their size 
  ```js
  // less than operator (<)
  console.log(5 < 8) // true
  console.log(10 < 6) // false

  // less than or equal to operator (<=)
  console.log(7 <= 7) // true
  console.log(7 <= 9) // false

  // greater than operator (>)
  console.log(2 > -6) // true
  console.log(10 > 20) // false

  // greater than or equal to operator (>=)
  console.log(9 >= 2) // true
  console.log(4 >= -7) // false
  ```

#### [Logic operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#Binary_logical_operators)
  - These are used to compare values based on their truthiness
  ```js
  const myName = "James"
  const myAge = 20

  // AND operator (&&)
  // both expressions have to be true for this statement to return true
  console.log(myName === "James" && myAge > 20) // false

  // OR operator (||)
  // one or more of these expressions has to be true for this statement to return true
  console.log(myName === "James" || myAge > 20) // true
  ```
    
### Conditional statements
  - These are used to run a block of code depending on the truthiness of an expression
  ```js
  if (expression) {
    // if expression is true, do this
  } else {
    // otherwise, do this
  }
  ```
  
  - Can use any number of *else if* blocks inbetween the *if* and *else*
  ```js
  const myName = "James"
  
  if (myName === "James") {
    // run code if name is James
  } else if (myName === "Collwyn") {
    // run code if name is Collwyn
  } else {
    // run code if name is anything else
  }
  ```
  
  - In some situations you might want to have all of this logic on one line, for this you can use ternary expressions
  - Ternary expressions are written with `?` and `:` like this: `const returnValue = [expression] ? [value if true] : [value if false]`
  ```js
  const age = 20
  const canDrink = age >= 18 ? "Yes" : "No"
  
  // this is literally 'if age is 18 or over, return "Yes", else return "No"'
  // equivalent to:
  // if (age >= 18) {
  //   canDrink = "Yes"
  // } else {
  //   canDrink = "No"
  // }
  
  console.log(canDrink) // Yes
  ```
### [Array Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array#Common_operations)
  - These are functions that loop over each element of an array, and give you the current element in a variable to perform actions on (depending on the function)
  #### Looping through an array
  - The .forEach function takes an array and runs a piece of code once on each element
  - Changes the original array
  ```js
  const fruits = ["apples", "oranges", "bananas", "grapes"]
  
  fruits.forEach(fruit => {
    // this code is run once for each element in the fruits array
    // fruit represents the current element in the fruits array
    console.log("I like: " + fruit)
  })
  
  // this code will log:
  
  // I like: apples
  // I like: oranges
  // I like: bananas
  // I like: grapes
  ```
  
  #### Creating a new array from an existing array
  - The .map function takes an array and returns a new array with modified elements
  - Doesn't change the original array, creates a new one
  ```js
  const twoTimesTables = [2, 4, 6, 8, 10]
  let fourTimesTables
  
  fourTimesTables = twoTimesTables.map(number => {
    // multiply each element of the array by two
    return number * 2
  })
  
  console.log(fourTimesTables) // [4, 8, 12, 16, 20]
  ```
  
  - This can also be written in shorthand 
  ```js
  fourTimesTables = twoTimesTables.map(number => number * 2)
  ```
  
  #### Filtering the values of an array
  - The .filter function returns a new array with the filtered elements
  - Creates a new array containing values that pass a condition
  
  ```js
  const numbers = [12, 154, 288, 100, 23]
  
  let numbersUnder100
  
  numbersUnder100 = numbers.filter(number => {
    // the condition here is that 'the number is less than 100'
    return number < 100
  })
  
  console.log(numbersUnder100) // [12, 23]
  ```
  
  - This can also be written in shorthand
  ```js
  numbersUnder100 = numbers.filter(number => number < 100)
  ```
  
## Challenge 5 - Javascript Basics
- Print out your name with a message (like 'Hello there [your name]')
- Create 2 variables, `a` & `b`, and assign different numbers to them. Then do some multiplication, division, addition, and subtraction, with them.
- Create a new variable `x`, and assign it the number 20 like so: `const x = "20"`. Add that to one of your previous variables. What do you notice? Why do you think that is?
- Create an array, filled with names, then use a loop to print out their name & the same message for each one. You should end up with something like "Hey Bill", "Hey Fred", "Hey Sally", etc.
- Create a variable called age and assign it to your age. Use an if/else statement to tell you if you're allowed to legally drink
- Create another variable called `likesBeer` and assign it to a boolean (true or false). Modify your existing if statement so that if you're over 18 & like beer, it says you can drink. If not, print out a message to say no.
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

  > There's (at least) 2 ways of doing this - if you're looking to stretch yourself, look at the `Array.reduce()` function!

- For an additional challenge - write a check for palindrome - taking a variable (such as `const input = "hello there"`) and returning (outputting) a `true` or `false`. If it's the same in reverse it should tell you. For example, inputting `"racecar"` should output `true`, but `"nope"` should be `false`

## Going further with JavaScript

### Functions
  - Functions are a named block of code that you write to perform an action, that you can reuse anywhere in your code
  - They are written by writing the word `function`, followed by a name for the function `sayHello`, a pair of brackets `()`, and a pair of curly braces `{}`
  ```js
  function sayHello() {
    // your code goes inbetween the curly braces
    console.log("Hello!")
  }
  ```
  
  - Functions are called/invoked by writing the name of the function followed by a pair of brackets
  ```js
  sayHello() // Hello!
  ```
  
  - Functions can also be passed *parameters* which are values that can be used in the function to change its action
  - You can pass as many parameters as you want to a function
  ```js
  // parameters are written between the brackets when you declare a function
  function sayHello(name) {
    console.log("Hello " + name + "!")
  }
  
  // parameters are passed to the function by putting them inside the brackets
  sayHello("James") // Hello James!
  ```
  
  - Functions can also return values to the point that you called them
  ```js
  function total(num1, num2) {
    // the return statement tells the function to end after this line, and return the value of the expression that comes after return
    return num1 + num2
  }
  
  total(10, 15) // this won't do anything!
  
  console.log(total(10, 15)) // 25
  ```
  
### Including JS in a HTML page
  - JavaScript can be added to a HTML page by using a `<script>` tag
  ```html
  <body>
    <script>
    // the JavaScript code in this script tag will run as soon as the HTML page is opened
    console.log("Hello!")
    </script>
  </body>
  ```
  
  - This is also how you reference external `.js` JavaScript files to use on a HTML page
  ```html
  <body>
    <!-- this JavaScript file will run as soon as the HTML page is opened -->
    <script src="script.js"/>
  </body>
  ```
  
### Interacting with the DOM
  - The Document Object Modal (DOM) is an interface that JavaScript has for interacting with HTML elements. You can use JavaScript to dynamically create, edit, remove HTML elements and much more.
  - HTML elements are targeted using the same selectors that you use in CSS (`.` for classes, `#` for IDs, tag names for HTML elements)
  
  #### Finding a HTML element
  - Using `document.querySelector` to find a single HTML element, and `document.querySelectorAll` to find multiple HTML elements
  ```js
  const myForm = document.querySelector(".my-form") // find the first HTML element with the class of .my-form
  const allDivs = document.querySelectorAll("div") // find all HTML <div> elements
  ```
  
  #### Creating a new HTML element
  ```js
  const newListItem = document.createElement("li") // create the new HTML <li> list item element as a JavaScript variable
  newListItem.innerHTML = "This is a new list item!" // put some text in the new element
  ```
  
  #### Adding a HTML element to the page
  ```js
  const myList = document.querySelector(".my-list") // find my list
  myList.appendChild(newListItem); // attaches the new list item into the list
  ```
  
  #### Creating an event listener
  ```js
  // find the submit button by its class of submit-button
  const submitButton = document.querySelector(".submit-button")
  
  // attaching the onButtonClick function to the click event of the button
  submitButton.addEventListener("click", onButtonClick)
  
  // function to run when the button is clicked
  function onButtonClick(e) {
    // the parameter e is automatically passed through to this function
    // it contains information about the click event
    
    // preventDefault() stops the browser from performing its default action when an event occurs
    // if this button was to submit a form, the default action is to make a HTTP request and reload the page which we don't want
    e.preventDefault()
    
    console.log("You have clicked my button!")
  }
  ```
  
### Asynchronous JavaScript
  - Not everything in your code happens instantly, some things will have delays which can cause issues in our code
  - An example of this is a HTTP request to a resource on another website, your code doesn't know how long it will take to resolve, or if it even will
  - If we run the code below, the `response` variable won't ever resolve to the data we want from tvmaze.com. It's basically told "You'll get some data eventually, but I don't know when", and because of that, the program carries on and it basically gets forgotten, This causes the `data` variable to throw an error because it can't work on the `response` variable properly
  ```js
  function callAPI(query) {
    // we can use the fetch function to make a HTTP GET request to the URL we give it
    const response = fetch(`http://api.tvmaze.com/search/shows?q=${query}`) // make API call
    
    // we need to do this to get the data
    const data = response.json() // TypeError: response.json is not a function
    
    // this line would run as soon as the function runs, if an error wasn't thrown above 
    return data
  }
  ```
  
  - To fix this, we can use async/await to tell the code to make the request, and wait for the data to be returned before we carry on with the rest of the code
  ```js
  // we have to tell the function to be asyncronous by using the async keyword
  async function callAPI(query) {
    // wait for a response to be received from the website
    const response = await fetch(`http://api.tvmaze.com/search/shows?q=${query}`)
    
    // wait for the JSON data from the response to be received
    const data = await response.json()
    
    // this line will only run once the data has all been received properly
    return data
  }
  ```
  
  - As callAPI is now an asynchronous function, we'd need to use await when we call it
  ```js
  async function someOtherAsyncFunction() {
    // ...
    // await can ONLY be used inside an async function!
    await callAPI("Breaking Bad")
    // ...
  }
  ```

## Challenge 6 - Including JavaScript on the page, and JavaScript API calls with async/await
- Include some JavaScript directly onto your html page. Make it `console.log()` the word `"test"`.
- Make an alert box pop up when you open the webpage. Customise the message.
- Make an alert box pop up when you press a button.
- Make an element appear on the page when you press a button
- Use the `async`/`await` syntax to make an API call to the TVMaze API. Hard-code the query to be your favourite TV show. Use a `console.log` to simply print out the results.
- Create the following user story:
  - Users can enter a TV show and press search. When they do, they will see their query added to a list underneath.
- Create the following user story:
  - Users can search for a TV show, and be shown a list of matching responses as a list on the page below.
  - Users can add a show from the list to a seperate list of their favourites.
- Create the following user story:
  - Users can remove a TV show from their list of favorites
