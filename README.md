# Starting fresh

Before we start building our app, we're going to delete some of the boilerplate code that Vite provided for us.

First, as an experiment, change the `<h1>` element in `App.jsx` so that it reads "Hello, World!", then save your file. You'll notice that this change is immediately rendered in the development server running at `http://localhost:5173` in your browser. Bear this in mind as you work on your app.

We won't be using the rest of the code! Replace the contents of App.jsx with the following:

```JSX
// import "./App.css";

function App() {
  return (
    <>
      <header>
        <h1>Hello, World!</h1>
      </header>
      <div>
        <h2>Practice with JSX</h2>
        <button type="button">Click me!</button>
      </div>
    </>
  );
}

export default App;
```

## Practice with JSX

Next, we'll use our JavaScript skills to get a bit more comfortable writing JSX and working with data in React. We'll talk about how to add attributes to JSX elements, how to write comments, how to render content from variables and other expressions, and how to pass data into components with props.

### Adding attributes to JSX elements

JSX elements can have attributes, just like HTML elements. Try adding a `<button>` below the `<h1>` element in your App.jsx file, like this:

```JSX
<button type="button">Click me!</button>
```

When you save your file, you'll see a button with the words `Click me!`. The button doesn't do anything yet, but we'll learn about adding interactivity to our app soon.

Some attributes are different than their HTML counterparts. For example, the `class` attribute in HTML translates to `className` in JSX. This is because `class` is a reserved word in JavaScript, and JSX is a JavaScript extension. If you wanted to add a `primary` class to your button, you'd write it like this:

```JSX
<button type="button" className="primary">
  Click me!
</button>
```

### JavaScript expressions as content

Unlike HTML, JSX allows us to write variables and other JavaScript expressions right alongside our other content. Let's declare a variable called subject just above the `App()` function:

```JSX
const subject = "React";

function App() {
    // code omitted for brevity
}
```

Next, replace the word "World" in the `<h1>` element with `{subject}`:

```JSX
<h1>Hello, {subject}!</h1>
```

Save your file and check your browser. You should see "Hello, React!" rendered.

The curly braces around subject are another feature of JSX's syntax. The curly braces tell React that we want to read the value of the subject variable, rather than render the literal string "subject". You can put any valid JavaScript expression inside curly braces in JSX; React will evaluate it and render the result of the expression as the final content. Following is a series of examples, with comments above explaining what each expression will render:

```JSX
{/* You can put a variable inside the curly braces */}
<p>Hello, {name}!</p>

{/* You can do concatenation inside the curly braces */}
<p>Hello, {name + ' 🙂'}!</p>

{/* You can call a string method inside the curly braces */}
<p>Hello, {name.toUpperCase()}!</p>

{/* You can put an arithmetic expression inside the curly braces */}
<p>Hello, {2 + 2}!</p>
```

Even comments in JSX are written inside curly braces! This is because comments, too, are technically JavaScript expressions. The /* block comment syntax */ is necessary for your program to know where the comment starts and ends.


### Component props

**Props** are a means of passing data into a React component. Their syntax is identical to that of attributes, in fact: prop="value". The difference is that whereas attributes are passed into plain elements, props are passed into React components.

In React, the flow of data is unidirectional: props can only be passed from parent components down to child components.

Let's open `main.jsx` and give our `<App />` component its first prop.

Add a prop of `userName` to the `<App />` component call, with a value of `Peter`. When you are done, it should look something like this:

```JSX
<App userName = "Peter" />
```

Back in `App.jsx`, let's revisit the `App()` function. Change the signature of `App()` so that it accepts `props` as a parameter and log props to the console so you can inspect it.

Your App.jsx file should look like this:

```JSX
function App(props) {
  console.log(props);
  return (
    // code omitted for brevity
  );
}
```

Update the `App` to look like this:

```JSX
<div>
    <h3>Component props</h3>

    {/* You can put a variable inside the curly braces */}
    <p>Hello, {props.userName}!</p>

    {/* You can do concatenation inside the curly braces */}
    <p>Hello, {props.userName + ' 🙂'}!</p>

    {/* You can call a string method inside the curly braces */}
    <p>Hello, {props.userName.toUpperCase()}!</p>

    {/* You can put an arithmetic expression inside the curly braces */}
    <p>Hello, {2 + 2}!</p>
</div>
```

When you save, the app should now greet you with "Hello, Peter!". If you return to `main.jsx`, edit the value of `userName`, and save, your text will change.

For additional practice, you could try adding an additional greeting prop to the `<App />` component call inside main.jsx and using it alongside the subject prop inside `App.jsx`.

## Summary

This brings us to the end of our initial look at React, including how to install it locally, creating a starter app, and how the basics work. In the next article, we'll start building our first proper application — a todo list. Before we do that, however, let's recap some of the things we've learned.

In React:

- Components can import modules they need and must export themselves at the bottom of their files.
- Component functions are named with `PascalCase`.
- You can render JavaScript expressions in JSX by putting them between curly braces, like `{so}`.
- Some JSX attributes are different than HTML attributes so that they don't conflict with JavaScript reserved words. For example, `class` in HTML translates to `className` in JSX.
- Props are written just like attributes inside component calls and are passed into components.

## How you can access this live website

<dl>
  Use the following URL:
  <dd>
    https://olumpeter.github.io/002-starting-fresh/
  </dd>
  or click the following link:
  <dd>
    <a href="https://olumpeter.github.io/002-starting-fresh/">Visit website</a>
  </dd>
</dl>
