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
