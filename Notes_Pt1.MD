# Codecademy React Tutorial
### Notes Pt. 1

React.js is a JavaScript library. It was developed by engineers at Facebook.

Here are just a few of the reasons why people choose to program with React:

- React is fast. Apps made in React can handle complex updates and still feel quick and responsive.
- React is modular. Instead of writing large, dense files of code, you can write many smaller, reusable files. React's modularity can be a beautiful solution to JavaScript's maintainability problems.
- React is scalable. Large programs that display a lot of changing data are where React performs best.
- React is flexible. You can use React for interesting projects that have nothing to do with making a web app. People are still figuring out React's potential. There's room to explore.
- React is popular. While this reason has admittedly little to do with React's quality, the truth is that understanding React will make you more employable.

If you are new to React, then this course is for you! No prior React knowledge is expected. We will start at the very beginning and move slowly.

If you are new to JavaScript, then consider taking our JavaScript course and then returning to React.

The three Codecademy React courses are not a high-level overview. They are a deep dive. Take your time! By the end, you will be ready to program in React with a real understanding of what you're doing.

## Intro to JSX
The following line is an example of what JSX could look like. It is a hybrid of both JS and HTML.

```JSX
const h1 = <h1>Hello world</h1>;
```

JSX is a JavaScript syntax extension, but since it's not JS, web browsers can't read it. You need a compilier to run JSX code.

JSX elements are treated as JavaScript expressions. They can go anywhere that JavaScript expressions can go.

That means that a JSX element can be saved in a variable, passed to a function, stored in an object or array...you name it.

Here's an example of a JSX element being saved in a variable:
```JSX
const navBar = <nav>I am a nav bar</nav>;
```

JSX elements can have attributes, just like HTML elements can.

A JSX attribute is written using HTML-like syntax: a name, followed by an equals sign, followed by a value. The value should be wrapped in quotes, like this:

```JSX
const p1 = <p id="large">foo</p>;
const p2 = <p id="small">bar</p>;
```

You can nest JSX elements inside of other JSX elements, just like in HTML.

If a JSX expression takes up more than one line, then you must wrap the multi-line JSX expression in parentheses. This looks strange at first, but you get used to it:
```JSX
var myDiv = (
  <div>
  	<h1>
      Hello world
    </h1>
  </div>
);
```

There's a rule that we haven't mentioned: a JSX expression must have exactly one outermost element.

In other words, this code will work:
```JSX
const paragraphs = (
  <div id="i-am-the-outermost-element">
    <p>I am a paragraph.</p>
    <p>I, too, am a paragraph.</p>
  </div>
);
```

But this will not work:
```JSX
const paragraphs = (
  <p>I am a paragraph.</p> 
  <p>I, too, am a paragraph.</p>
);
```
### Rendering JSX
Rendering JSX means to make it appear on screen. Let's take a look at this code block:
```JSX
ReactDOM.render(<h1>Hello world</h1>,
document.getElementById('app'));
```
`ReactDOM` is the name of a JavaScript library. This library contains several React-specific methods, all of which deal with the DOM in some way or another.

We'll talk more later about how `ReactDOM` got into your file. For now, just understand that it's yours to use.

Move slightly to the right, and you can see one of ReactDOM's methods: `ReactDOM.render()`.

`ReactDOM.render()` is the most common way to render JSX. It takes a JSX expression, creates a corresponding tree of DOM nodes, and adds that tree to the DOM. That is the way to make a JSX expression appear onscreen.

### Passing a Variable to ReactDOM.render()
ReactDOM.render()'s first argument should evaluate to a JSX expression, it doesn't have to literally be a JSX expression.

The first argument could also be a variable, so long as that variable evaluates to a JSX expression.
```JSX
var myList = (
	<ul>
    <li>My</li>
    <li>name's</li>
    <li>David</li>
  </ul>
);

ReactDOM.render(
myList,
document.getElementById('app')
);
```

### The Virtual DOM
One special thing about ReactDOM.render() is that it only updates DOM elements that have changed.

That means that if you render the exact same thing twice in a row, the second render will do nothing:
```JSX
const hello = <h1>Hello world</h1>;

// This will add "Hello world" to the screen:

ReactDOM.render(hello, document.getElementById('app'));

// This won't do anything at all:

ReactDOM.render(hello, document.getElementById('app'));
```
This is significant! Only updating the necessary DOM elements is a large part of what makes React so successful.

## ADVANCED JSX
### class vs className
This lesson will cover more advanced JSX. You'll learn some powerful tricks, and some common errors to avoid.

Grammar in JSX is mostly the same as in HTML, but there are subtle differences to watch out for. Probably the most frequent of these involves the word class.

In HTML, it's common to use class as an attribute name:
```JSX
<h1 class="big">Hey</h1>
```
In JSX, you can't use the word class! You have to use className instead:
```JSX
<h1 className="big">Hey</h1>
```
This is because JSX gets translated into JavaScript, and class is a reserved word in JavaScript.

When JSX is rendered, JSX className attributes are automatically rendered as class attributes.

### Self-Closing Tags
Another JSX 'gotcha' involves self-closing tags.

What's a self-closing tag?

Most HTML elements use two tags: an opening tag (`<div>`), and a closing tag (`</div>`). However, some HTML elements such as `<img>` and `<input>` use only one tag. The tag that belongs to a single-tag element isn't an opening tag nor a closing tag; it's a self-closing tag.

### JavaScript In Your JSX In Your JavaScript
So far, we've focused on writing JSX expressions. It's similar to writing bits of HTML, but inside of a JavaScript file.

In this lesson, we're going to add something new: regular JavaScript, written inside of a JSX expression, written inside of a JavaScript file.

**Curly Braces in JSX**
The code in the last exercise didn't behave as one might expect. Instead of adding 2 and 3, it printed out "2 + 3" as a string of text. Why?

This happened because 2 + 3 is located in between `<h1>` and `</h1>` tags.

Any code in between the tags of a JSX element will be read as JSX, not as regular JavaScript! JSX doesn't add numbers - it reads them as text, just like HTML.

You need a way to write code that says, "Even though I am located in between JSX tags, treat me like ordinary JavaScript and not like JSX."

You can do this by wrapping your code in curly braces.
```JSX
ReactDOM.render(
  <h1>{2 + 3}</h1>,
  document.getElementById('app')
);
```






