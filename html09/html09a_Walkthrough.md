# Lesson 09a Walkthrough: JavaScript Basics for the Web Exam

In this walkthrough you build one small page with JavaScript in it. You add a script, print messages in the Console, write comments, and make a few variables. Then you move the script to its own file, the way a real website does it.

This lesson covers what the state Web Design exam asks about JavaScript. The full JavaScript lesson (buttons, dark mode, form checks) comes after the exam.

## Table of Contents

1. [Before You Start](#1-before-you-start)
2. [What JavaScript Does](#2-what-javascript-does)
3. [Client-Side and Server-Side Scripting Languages](#3-client-side-and-server-side-scripting-languages)
4. [The script Tag](#4-the-script-tag)
5. [Showing Output in the Console](#5-showing-output-in-the-console)
6. [Comments](#6-comments)
7. [Variables: let and const](#7-variables-let-and-const)
8. [Data Types: String, Number, Boolean](#8-data-types-string-number-boolean)
9. [Joining Strings](#9-joining-strings)
10. [What Happens After a Form Is Sent](#10-what-happens-after-a-form-is-sent)
11. [Moving the Script to Its Own File](#11-moving-the-script-to-its-own-file)
12. [Try This Answers](#12-try-this-answers)

---

## 1. Before You Start

1. In your `htmlCssJavaScript` repo, open the `html09a_javascriptExamPrep` folder.
2. Make a new file named `html09a_Walkthrough_lastname.html` (use your real last name).
3. Paste in this starter. You will add JavaScript inside the `<script>` block at the bottom as you go.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>html09a Walkthrough</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 1rem;
    }
  </style>
</head>
<body>
  <h1>html09a Walkthrough</h1>
  <p>Open the Console to see what this page's JavaScript prints.</p>

  <!-- Scripts go at the end of the body -->
  <script>
    // Your walkthrough JavaScript goes below this line

  </script>
</body>
</html>
```

---

## 2. What JavaScript Does

A web page is built from three languages:

| Language | Job | Example |
|---|---|---|
| HTML | What is on the page | a heading, a form, a button |
| CSS | How it looks | colors, fonts, layout |
| JavaScript | What it does | a button that switches to dark mode, a form that checks your email |

JavaScript is a **scripting language**. A scripting language is a programming language that runs inside another program. JavaScript runs inside the **web browser**.

JavaScript can:

- Change text and styles on the page after it loads
- Respond when someone clicks, types, or sends a form
- Check what a user typed before a form is sent

Things CSS can already do stay in CSS. A hover effect on a link, for example, is `a:hover` in your stylesheet. You don't need JavaScript for it.

---

## 3. Client-Side and Server-Side Scripting Languages

Scripts on a website run in one of two places.

**Client-side** means the script runs in the browser, on the visitor's computer. The **client** is the visitor's browser. The web server sends the file, and the browser runs it.

**Server-side** means the script runs on the **web server** before the page is sent. The visitor never sees the code. They only see the finished page the server sends back.

| | Client-side | Server-side |
|---|---|---|
| Where it runs | In the visitor's browser | On the web server |
| Main language | JavaScript | PHP, Python, Node.js, Ruby, C# (ASP.NET), Java |
| Can the visitor see the code? | Yes (View Page Source) | No |
| Good for | Quick changes on the page, checking a form before it sends, responding to clicks | Saving to a database, logging in, sending email, building pages from stored data |
| Example | A dark mode button | An online store showing your order history |

A few notes:

- **JavaScript is the client-side language.** Every modern browser runs it, and nothing else has replaced it.
- **Node.js** is JavaScript running on a server instead of in a browser. Same language, different place.
- **SQL** is not a scripting language for web pages. It is the language for asking a database for data. A server-side script often uses SQL to talk to the database.
- **Old languages you might see in questions:** VBScript and Flash (ActionScript) were used in older websites. Browsers don't support them anymore.

**Static and dynamic sites**. A static site sends the same files to every visitor. Pages change only when someone edits the files. A dynamic site can change its content or behavior based on user interaction, user information, or data from a database. For example, a shopping cart or personal messages can be different for each visitor. Dynamic sites may use client-side JavaScript, server-side scripting, or both. The site you built in this class is static, although adding JavaScript can make it interactive.

> **Try This 3:** Is each one client-side or server-side?
> a. Checking that an email box has an `@` before the form sends
> b. Saving a new account to a database
> c. Switching a page to dark mode when a button is clicked
> d. Showing a logged-in user their own order history

---

## 4. The script Tag

JavaScript goes on a page with the `<script>` tag. There are two ways to do it.

**Internal script:** the code goes between the tags, in the HTML file.

```html
<script>
  // JavaScript code goes here
</script>
```

**External script:** the code goes in its own `.js` file. The tag points to it with the `src` attribute, and nothing goes between the tags.

```html
<script src="script.js"></script>
```

External is better for a real site. One `script.js` file can be linked on every page, the same way one `styles.css` file styles every page. If you fix something in `script.js`, every page gets the fix.

**Where the tag goes:** put it at the **end of the body**, right before `</body>`. The browser reads the page from top to bottom. If a script runs before the rest of the page loads, it can't find the parts of the page it needs.

You may also see the tag in the `<head>` with `defer`. `defer` tells the browser to wait until the page is loaded before running the script. Both ways work.

```html
<head>
  <script src="script.js" defer></script>
</head>
```

Compare it to how CSS is added:

| | CSS | JavaScript |
|---|---|---|
| Inside the HTML file | `<style> ... </style>` | `<script> ... </script>` |
| In its own file | `<link rel="stylesheet" href="styles.css">` | `<script src="script.js"></script>` |
| File extension | `.css` | `.js` |

---

## 5. Showing Output in the Console

When you write code, you need to see what it is doing. Programmers use `console.log()`. It prints a message to the **Console**, a panel in the Developer Tools. Visitors to your page never see the Console. It is a tool for the programmer.

Add this inside your `<script>` block:

```js
console.log('Hello, world!');
console.log('JavaScript is running.');
```

### Open the Console

The Console is part of the Developer Tools in VS Code's Live Preview. (Developer Tools in Chrome are turned off on school computers, but the ones in Live Preview work.)

1. Open your page with **Live Preview** in VS Code.
2. In the preview's toolbar, click the **Developer Tools** button. A panel opens next to the page.
3. Click the **Console** tab.

Both lines should show up in the Console. Keep the Console open for the whole walkthrough.

**The Console also shows errors.** If your code has a mistake, the Console shows a red error message with the line number where it happened. One mistake stops the whole script, so if a message you expect is missing, look for red. Then check the spelling, the quotes, and that every `(` has a matching `)`.

If you change your code and the Console doesn't show the new messages, save the file and refresh the preview.

> **Try This 5:** Use `console.log()` to print your name, then your favorite food.

---

## 6. Comments

A **comment** is a note in your code. The browser skips it. Comments explain what the code does, for other people and for you next week.

JavaScript has two kinds of comments:

```js
// A one-line comment starts with two slashes.

console.log('Hi');   // A one-line comment can go at the end of a line too.

/*
  A multi-line comment starts with slash-star
  and ends with star-slash.
  Use it for longer notes.
*/
```

Each language you have used has its own comment style. Know all three:

| Language | Comment |
|---|---|
| HTML | `<!-- comment -->` |
| CSS | `/* comment */` |
| JavaScript | `// comment` or `/* comment */` |

Good comments say **what the code is for**, not just repeat the code:

```js
// Bad: print hello
// Good: check that the script file is linked and running
console.log('Hello, world!');
```

Add a comment block at the very top of your `<script>`:

```js
/*
  html09a Walkthrough
  Name: Your Name
  This script practices console output, comments, and variables.
*/
```

From here on, put a comment above each new part you add.

> **Try This 6:** Write a one-line comment and a multi-line comment that each say what your page is for.

---

## 7. Variables: let and const

A **variable** is a named box that holds a value. You make one with `let` or `const`.

```js
// let: the value can change later
let score = 0;
score = 10;          // this works
console.log(score);

// const: the value is set once and never changes
const schoolName = 'Medina County Career Center';
console.log(schoolName);
```

What happens if you try to change a `const`?

```js
// schoolName = 'Another School';   // ERROR: can't change a const
```

If you take the `//` off that line, it causes an error, and the error stops the script. The Console shows it in red. Put the `//` back so the rest of your script runs.

**Which one should you use?** Use `const` when the value should never change. Use `let` when it will. You may see `var` in older code online. It is the old way. Use `let` and `const`.

**Naming:** use **camelCase**. Start lowercase, and start each new word with a capital: `firstName`, `favoriteColor`, `isStudent`. No spaces or dashes. Pick names that say what the box holds.

> **Try This 7:** Make a `let` variable called `favoriteColor` and a `const` called `birthYear`. Print both with `console.log()`.

---

## 8. Data Types: String, Number, Boolean

The kind of value a variable holds is its **data type**. You need these three:

```js
// String: text, always inside quotes
let firstName = 'Alex';

// Number: no quotes. Can be whole or decimal.
let age = 16;
let price = 3.75;

// Boolean: only true or false. No quotes.
let isStudent = true;

console.log(firstName);
console.log(age);
console.log(isStudent);
```

Quotes matter. `'16'` is a string. `16` is a number. Watch what `+` does with each:

```js
console.log(5 + 3);       // 8   (two numbers: adds them)
console.log('5' + '3');   // 53  (two strings: joins them)
```

> **Try This 8:** What data type is each one? `'blue'`, `42`, `false`, `'42'`

---

## 9. Joining Strings

Joining strings together is called **concatenation**. You do it with `+`.

```js
let firstName = 'Alex';
let age = 16;

// Join text and variables with +
console.log('My name is ' + firstName + ' and I am ' + age + ' years old.');
```

Watch the spaces. `'My name is' + firstName` prints `My name isAlex`. The space has to be inside the quotes.

> **Try This 9:** Make a variable `city`. Print `I live in ___.` using `+`.

---

## 10. What Happens After a Form Is Sent

In html08 you built forms. The form's `action` attribute says where the data goes when the user clicks Submit. On a real website, that is a **web server**. Scripts on both sides handle the data.

**In the browser (client-side, JavaScript):**

1. **JavaScript checks the form before it sends.** For example, it can show "Please enter your email" if the box is empty. This is called **form validation**. It gives the user quick, friendly feedback without waiting for the server.

**On the server (server-side, a language like PHP, Python, or Node.js):**

2. **The server checks the data again.** A user can turn off JavaScript or get around it. So the server never trusts the data just because the browser checked it. Browser checks are for convenience. Server checks are for safety.
3. **The server stores it.** It usually saves the data in a **database**, which is an organized place to keep records, like a table of every message that was sent.
4. **The server may pass it on.** It might send the data to a **web service**, another program that does one job, like sending an email to the site owner or adding the person to a mailing list.
5. **The server answers.** It sends back a page or message like "Thanks, we got your message."

| Term | Meaning |
|---|---|
| Form validation | Checking that form data is filled in and makes sense |
| Web server | The computer that stores a website and sends it to browsers |
| Database | An organized collection of records the server can save to and look up |
| Web service | A program on the internet that does one job when another program asks, like sending email or looking up weather |

In this class, our forms don't actually send anything. The server side comes in later courses.

> **Try This 10:** A user fills in a sign-up form and clicks Submit. Put these in order: the server saves the account in a database; JavaScript checks that the email box isn't empty; the server sends back "Welcome!"; the server checks the data again.

---

## 11. Moving the Script to Its Own File

On a real site, the JavaScript goes in its own file, like your CSS does.

1. Make a new file next to your HTML named `html09a_Walkthrough_lastname.js`.
2. Cut everything **between** `<script>` and `</script>` and paste it into the new file. Don't bring the `<script>` tags. A `.js` file has only JavaScript in it.
3. Change the script tag at the end of the body to:

```html
<!-- Link the external JavaScript file -->
<script src="html09a_Walkthrough_lastname.js"></script>
```

4. Save both files and refresh the preview. The Console should show the same messages as before.

If nothing shows up, check that the file name in `src` matches exactly, including capital letters, and that the `.js` file is in the same folder as the HTML file.

Commit and push with GitHub Desktop.

---

## 12. Try This Answers

**Try This 3**
a. Client-side
b. Server-side
c. Client-side
d. Server-side

**Try This 5**

```js
console.log('Alex');
console.log('Pizza');
```

**Try This 6**

```js
// This page practices JavaScript basics.

/*
  This page practices JavaScript basics:
  the Console, comments, and variables.
*/
```

**Try This 7**

```js
let favoriteColor = 'green';
const birthYear = 2010;
console.log(favoriteColor);
console.log(birthYear);
```

**Try This 8**
`'blue'` is a string. `42` is a number. `false` is a boolean. `'42'` is a string, because it is in quotes.

**Try This 9**

```js
let city = 'Medina';
console.log('I live in ' + city + '.');
```

**Try This 10**

1. JavaScript checks that the email box isn't empty.
2. The server checks the data again.
3. The server saves the account in a database.
4. The server sends back "Welcome!"

[Back to top](#table-of-contents)
