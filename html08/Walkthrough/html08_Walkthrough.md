# HTML Forms Walkthrough (html08)

In this walkthrough you build one practice form, step by step. You will use every form skill that is graded in this lesson. When you finish, you will do the practice task (`html08_Task.html`) and then add a real form to the Contact page of your own website (`html08_DIYTask.md`).

**Files you make:** `form-practice.html` and `form-practice.css`, saved together in one folder.

> **Video for this lesson:** Bro Code, "HTML forms" (about 8 minutes): https://www.youtube.com/watch?v=2O8pkybH6po
>
> We watch this video in class first. It covers the `<form>` tag, `action` and `method` (GET vs POST), labels with `for` and `id`, `name`, `placeholder`, `required`, and these input types: text, password, email, tel, date, number, radio, and checkbox. It also covers `<select>` dropdowns and submit and reset buttons.
>
> This walkthrough uses all of that, plus a few things the video does not cover: the `url` input type, `minlength`, `<textarea>`, `<fieldset>` and `<legend>`, the `<button>` tag, tab order, and styling the form with CSS. Where the video does something a little differently from this walkthrough, there is a note that says so.

## Table of Contents

1. [What a Form Is](#1-what-a-form-is)
2. [The form Tag: action and method](#2-the-form-tag-action-and-method)
3. [Labels and Text Inputs](#3-labels-and-text-inputs)
4. [Other Input Types](#4-other-input-types)
5. [Radio Buttons](#5-radio-buttons)
6. [Checkboxes](#6-checkboxes)
7. [Dropdown Menus with select](#7-dropdown-menus-with-select)
8. [Textarea for Longer Messages](#8-textarea-for-longer-messages)
9. [Grouping with fieldset and legend](#9-grouping-with-fieldset-and-legend)
10. [Submit and Reset Buttons](#10-submit-and-reset-buttons)
11. [Tab Order and tabindex](#11-tab-order-and-tabindex)
12. [Styling the Form with CSS](#12-styling-the-form-with-css)
13. [Test Your Form](#13-test-your-form)
14. [Checklist](#14-checklist)
15. [Summary](#15-summary)

---

## 1. What a Form Is

A **form** is the part of a web page where a visitor types or picks information: a login box, a sign-up page, a search bar, an order page. The form collects the answers and sends them somewhere when the visitor clicks a button.

Every form is made of:

- The **`<form>`** tag, which wraps everything.
- **Controls**: the boxes, buttons, and lists people fill in (`<input>`, `<select>`, `<textarea>`).
- **Labels** that say what each control is for.
- A **submit button** that sends the answers.

---

## 2. The form Tag: action and method

Make `form-practice.html` and start with this:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Form Practice</title>
  <!-- Link the stylesheet you will write in step 12 -->
  <link rel="stylesheet" href="form-practice.css">
</head>
<body>
  <h1>Club Sign-Up</h1>

  <!-- id: a name for this form (JavaScript will use it in Lesson 09)
       action: WHERE the answers are sent
       method: HOW the answers are sent (get or post) -->
  <form id="signup-form" action="#" method="get">

    <!-- Everything in steps 3-10 goes in here -->

  </form>
</body>
</html>
```

### `action`: where the answers go

On a real website, `action` is the address where the browser sends the answers. Usually, this is a program on a **server** that receives the information. It might save the answers in a database, send a message to the website owner, or process a sign-up.

For example: `action="https://example.com/signup"`. In the video, Bro Code points `action` at a PHP page. PHP is one of the languages that runs on a server and handles form answers.

**We do not have a server yet.** Our sites are plain HTML files. So we use `action="#"` for this practice form. The `#` generally points to the current page. Nothing is sent to a server or saved in a database. That is fine for learning. In Lesson 09, JavaScript will let us check the form before submission.

### `method`: how the answers travel

| Method | What it does | Use it for |
|---|---|---|
| `get` | Adds the answers to the URL, after a `?` | Searches, filters, and information that is fine to see or bookmark |
| `post` | Sends the answers in the body of the request instead of the URL | Submitting information that needs to be processed or saved |

Real sign-up and contact forms commonly use `post`, with a server to receive the data. As the video says, **never send a password with `get`**, because the password shows up in the address bar for anyone to see. `get` is a good fit for search boxes. Note that `post` does not make information secure by itself; real websites also use HTTPS to protect information in transit.

We use `get` for now so you can **see** what your form sends. You will try this in Step 10, after you add the boxes and a submit button.

---

## 3. Labels and Text Inputs

An `<input>` is a one-line box. A `<label>` is the text that tells people what goes in the box.

Put this inside the `<form>`:

```html
<!-- for="fullName" on the label matches id="fullName" on the input.
     That ties them together. Clicking the label now puts the cursor in the box,
     and screen readers read the label out loud. -->
<label for="fullName">Full Name:</label>
<input type="text"
       id="fullName"
       name="fullName"
       placeholder="First and last name"
       required>
```

What each attribute does:

| Attribute | What it does |
|---|---|
| `type="text"` | A plain one-line text box |
| `id` | A unique name on the page. The label's `for` must match it exactly. |
| `name` | The name sent with the answer (`fullName=Ana+Lopez`). Without a name, the answer is not sent. |
| `placeholder` | Gray hint text inside the box. It disappears when you type. It is **not** a replacement for a label. |
| `required` | The browser will not submit the form while this box is empty. |

**Try it:** Save and open the page. Click the words "Full Name:". The cursor should jump into the box. If it does not, your `for` and `id` do not match.

**Note on the video:** Bro Code puts each label and input pair inside its own `<div>` so each pair sits on its own line. We do not need the `<div>`s. In step 12, the CSS rule `label { display: block; }` puts each label on its own line instead. Both ways work.

---

## 4. Other Input Types

Changing `type` changes what the box accepts and what the browser shows. Add these under the Full Name box:

```html
<!-- email: the browser checks for an @ sign and a domain before it submits -->
<label for="email">Email:</label>
<input type="email" id="email" name="email" placeholder="you@example.com" required>

<!-- password: hides the letters as you type.
     minlength: the browser will not submit fewer than 8 characters -->
<label for="password">Password:</label>
<input type="password" id="password" name="password" minlength="8" required>

<!-- tel: a phone number. On a phone, this opens the number keypad. -->
<label for="phone">Phone:</label>
<input type="tel" id="phone" name="phone" placeholder="330-555-0100">

<!-- number: numbers only. min and max set the allowed range. -->
<label for="age">Age:</label>
<input type="number" id="age" name="age" min="13" max="19">

<!-- date: shows a date picker -->
<label for="startDate">Start Date:</label>
<input type="date" id="startDate" name="startDate">

<!-- url: a web address. The browser checks that it starts with http:// or https:// -->
<label for="website">Your Website:</label>
<input type="url" id="website" name="website" placeholder="https://example.com">

<!-- maxlength: the box will not let you type more than 20 characters -->
<label for="nickname">Nickname:</label>
<input type="text" id="nickname" name="nickname" maxlength="20">
```

Two more attributes from the video:

- `maxlength` works on password boxes too. Bro Code uses `maxlength="12"` so a password can be no more than 12 characters. You can use `minlength` and `maxlength` together.
- `value` on a number box sets the starting number. Bro Code makes a quantity box with `min="0" max="99" value="1"`, so it starts at 1 and the arrows can't go below 0 or above 99.

**Try it:**
1. Type `ana` (no @ sign) in Email and click away. Nothing happens yet. When you add the submit button in step 10, the browser will stop you and show a message.
2. Type letters into Age. The number box will not keep them.
3. Type a long nickname. It stops at 20 characters.

---

## 5. Radio Buttons

**Radio buttons let the visitor pick exactly ONE choice** from a group.

```html
<p>Meeting time:</p>

<!-- All three have the SAME name, so they form one group.
     Picking one un-picks the others.
     Each one has a DIFFERENT value. The value is what gets sent. -->
<label>
  <input type="radio" name="meetingTime" value="before" required>
  Before school
</label>
<label>
  <input type="radio" name="meetingTime" value="lunch">
  Lunch
</label>
<label>
  <input type="radio" name="meetingTime" value="after">
  After school
</label>
```

Here the `<input>` is **inside** the `<label>`. That also ties them together, so you don't need `for` and `id`. Clicking the words picks the button. Both ways (for/id, or wrapping) are correct.

**Note on the video:** Bro Code uses the `for` and `id` way for radio buttons. Each radio button gets its own unique `id`, and its label's `for` matches it. That version looks like this:

```html
<!-- The for/id way (what the video shows). Same name, different id and value for each. -->
<input type="radio" id="before" name="meetingTime" value="before" required>
<label for="before">Before school</label>

<input type="radio" id="lunch" name="meetingTime" value="lunch">
<label for="lunch">Lunch</label>

<input type="radio" id="after" name="meetingTime" value="after">
<label for="after">After school</label>
```

Use whichever way you like. This walkthrough and the practice task use the wrapping way because it is shorter. The same choice applies to checkboxes in step 6.

Putting `required` on one radio button in a group makes the whole group required.

**Try it:** Give one of the radio buttons a different `name`. Now you can pick two at once. Put the name back.

---

## 6. Checkboxes

**Checkboxes let the visitor pick as MANY as they want**, or none.

```html
<p>What do you want to learn? (Pick any)</p>

<!-- Same name for the group, different value for each box.
     If two are checked, both are sent:
     interests=html&interests=games -->
<label>
  <input type="checkbox" name="interests" value="html">
  HTML and CSS
</label>
<label>
  <input type="checkbox" name="interests" value="javascript">
  JavaScript
</label>
<label>
  <input type="checkbox" name="interests" value="games">
  Game design
</label>
```

| | Radio buttons | Checkboxes |
|---|---|---|
| How many can be picked | One | Any number |
| Shape | Circle | Square |
| Example | T-shirt size | Toppings |

---

## 7. Dropdown Menus with select

A `<select>` is a dropdown list. Each choice is an `<option>`. Use it when there are several choices and a list of radio buttons would take up too much room.

```html
<label for="grade">Grade:</label>
<!-- The label's for matches the select's id, just like an input -->
<select id="grade" name="grade" required>
  <!-- An empty value on the first option makes it a "pick one" prompt.
       With required on the select, the browser won't accept this option. -->
  <option value="">-- Choose one --</option>
  <option value="11">Junior (11th)</option>
  <option value="12">Senior (12th)</option>
  <option value="other">Other</option>
</select>
```

The text between the tags ("Junior (11th)") is what the visitor sees. The `value` ("11") is what gets sent.

---

## 8. Textarea for Longer Messages

A `<textarea>` is a box for several lines of text, like a message.

```html
<label for="message">Why do you want to join?</label>
<!-- rows = how many lines tall, cols = about how many characters wide.
     textarea has a closing tag. Leave nothing between the tags,
     or that text shows up inside the box. -->
<textarea id="message" name="message" rows="5" cols="40"
          placeholder="Tell us a little about yourself"></textarea>
```

**Try it:** Change `rows` to 10 and look. Change it back. (Later, CSS `width: 100%` will control the width, so `cols` matters less.)

---

## 9. Grouping with fieldset and legend

A long form is easier to read in sections. `<fieldset>` draws a box around related controls. `<legend>` is the title of that box.

Your form works, but everything is in one long list. In this step you will **rebuild the form in four sections**. Copying pieces out of your own file and moving them around gets messy, so you will start the form over and copy the code from **this walkthrough** instead.

### Step A: Delete your old form

In `form-practice.html`, select everything from `<form id="signup-form"` down to `</form>`, including those two lines. Delete it. Leave the `<h1>` and everything else in the page alone.

### Step B: Paste in the empty template

Paste this where the old form was:

```html
<form id="signup-form" action="#" method="get">

  <fieldset>
    <legend>About You</legend>
    <!-- Paste the Full Name code from step 3 here.
         Then paste ALL the code from step 4 under it
         (email, password, phone, age, date, website, nickname). -->
  </fieldset>

  <fieldset>
    <legend>Meeting Time</legend>
    <!-- Paste the three radio buttons from step 5 here.
         Skip the <p>Meeting time:</p> line. The legend does that job now. -->
  </fieldset>

  <fieldset>
    <legend>Interests</legend>
    <!-- Paste the three checkboxes from step 6 here.
         Skip the <p>What do you want to learn?</p> line. The legend does that job now. -->
  </fieldset>

  <fieldset>
    <legend>A Little More</legend>
    <!-- Paste the Grade dropdown from step 7 here.
         Then paste the textarea from step 8 under it. -->
  </fieldset>

  <!-- The buttons go here in step 10 -->

</form>
```

### Step C: Fill in each fieldset

Scroll back up in this walkthrough and copy each code block into the matching fieldset:

| Fieldset (legend) | Copy the code from |
|---|---|
| About You | Step 3 (Full Name), then step 4 (all the other input types) |
| Meeting Time | Step 5 (radio buttons), without the `<p>` line |
| Interests | Step 6 (checkboxes), without the `<p>` line |
| A Little More | Step 7 (Grade dropdown), then step 8 (textarea) |

You can delete the `<!-- Paste ... -->` comments once the code is in.

**Try it:** Save and look at the page. You should see four boxes, each with a title on its top border. Every control from steps 3-8 should be in one of them. If one is missing, check the table above.

A fieldset + legend is the best way to label a group of radio buttons or checkboxes. Screen readers read the legend before each choice.

---

## 10. Submit and Reset Buttons

Put these after the last `</fieldset>`, still inside the `<form>`:

```html
<!-- A div so we can style the buttons as a group -->
<div class="button-group">
  <!-- submit: checks required fields, then sends the form to the action -->
  <button type="submit">Sign Up</button>
  <!-- reset: clears every box back to how it started -->
  <button type="reset">Clear Form</button>
</div>
```

| Button | What it does |
|---|---|
| `type="submit"` | Checks the form (required, email, min/max, minlength), then sends it |
| `type="reset"` | Empties the form. Nothing is sent. |
| `type="button"` | Does nothing by itself. JavaScript gives it a job (Lesson 09). |

The video uses the other way to make these buttons: `<input type="submit">` and `<input type="reset">`. You can add `value="Sign Up"` to change the words on the button. It works the same way. We use `<button>` because it is easier to style.

**Try it:**
1. Click Sign Up with everything empty. The browser stops you at the first required box.
2. Fill in the required boxes and click Sign Up. Look at the address bar. Because the form uses `method="get"`, the answers are added to the end of the address, after a `?`. You will see something like:

   ```
   form-practice.html?fullName=Ana+Lopez&email=ana%40example.com#
   ```

   Each piece is a **name=value pair**: the `name` you gave the control, an `=` sign, and what the visitor typed or picked. An `&` separates the pairs. A control with no `name` is left out, which is why every control needs a `name`. (A `+` stands for a space, and `%40` stands for the `@` sign.) Find the pair for each box you filled in.

   Find the `password=` pair. Your password is right there in the address bar. This is why the video says never to use `get` for passwords.
3. Change `method="get"` to `method="post"` and submit again. The answers are no longer in the address bar. Change it back to `get`.

---

## 11. Styling the Form with CSS

Make `form-practice.css` next to your HTML file. This uses skills from Lessons 05-07: colors, the box model, `:hover`, and a media query. It adds three new things:

- **Attribute selectors**, like `input[type="email"]`, which pick inputs by their type.
- **`:focus`**, which styles the box the cursor is in.
- **`box-sizing: border-box`**, so `width: 100%` includes the padding and border and the boxes don't stick out.

```css
/* The page */
body {
  font-family: Arial, sans-serif;
  max-width: 600px;            /* keeps the form from getting too wide */
  margin: 0 auto;              /* centers it */
  padding: 20px;
  background-color: #f5f5f5;
}

/* The form: a white card */
form {
  background-color: white;
  padding: 25px;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

/* Each section box */
fieldset {
  border: 1px solid #ddd;
  border-radius: 5px;
  padding: 15px;
  margin: 15px 0;
}

/* Section titles */
legend {
  font-weight: bold;
  font-size: 1.1rem;
  padding: 0 8px;
}

/* Labels on their own line, above the box */
label {
  display: block;
  margin-top: 10px;
  margin-bottom: 5px;
  font-weight: bold;
}

/* The text-style boxes, the dropdown, and the textarea.
   Radio buttons and checkboxes are NOT in this list,
   because we don't want them 100% wide. */
input[type="text"],
input[type="email"],
input[type="password"],
input[type="tel"],
input[type="number"],
input[type="date"],
input[type="url"],
select,
textarea {
  width: 100%;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 1rem;
  font-family: inherit;        /* textarea uses a different font unless you set this */
  box-sizing: border-box;      /* width includes padding and border */
}

/* The box the cursor is in */
input:focus,
select:focus,
textarea:focus {
  outline: none;               /* remove the browser's default outline... */
  border-color: #007bff;       /* ...and replace it with our own, so it is still easy to see */
  box-shadow: 0 0 5px rgba(0, 123, 255, 0.4);
}

/* Buttons */
.button-group {
  text-align: center;
  margin-top: 20px;
}

button {
  padding: 12px 20px;
  margin: 5px;
  border: none;
  border-radius: 4px;
  font-size: 1rem;
  font-weight: bold;
  cursor: pointer;             /* hand pointer, so it looks clickable */
  background-color: #007bff;
  color: white;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #0056b3;
}

/* Make the reset button look less important than submit */
button[type="reset"] {
  background-color: #6c757d;
}

button[type="reset"]:hover {
  background-color: #545b62;
}

/* Small screens: buttons full width */
@media (max-width: 600px) {
  button {
    display: block;
    width: 100%;
    margin: 10px 0;
  }
}
```

The radio buttons and checkboxes are inside labels that are `display: block`, so each choice gets its own line. They are bold because of the `label` rule. To make the choices plain, you can add `class="choice"` to those labels and this rule:

```css
/* Radio and checkbox labels: normal weight */
.choice {
  font-weight: normal;
}
```

**Never remove the focus outline without adding your own focus style.** Keyboard users need to see where they are.

---

## 12. Test Your Form

1. Click each label. The cursor or check should go to the right control.
2. Click Sign Up with the form empty. The browser should stop you.
3. Type a bad email. The browser should stop you.
4. Pick two radio buttons. Only one should stay picked.
5. Check two checkboxes. Both should stay checked.
6. Fill it in and submit. Read the answers in the address bar.
7. Click Clear Form. Everything empties.
8. Tab through the whole form. The order goes top to bottom, and you can always see which box you're in.
9. Check a phone width: open the page in a Chrome **Guest** window (copy the address from Live Preview's address bar, click your profile picture in Chrome > **Guest**, and paste it in), right-click > **Inspect**, then click the **device toolbar** button (phone-and-tablet icon). The buttons should go full width.
10. Run the page through https://validator.w3.org/ and fix any errors.

---

## 13. Checklist

- [ ] `<form>` with `id`, `action`, and `method`
- [ ] Every text-style input has a `<label>` with a `for` that matches its `id`
- [ ] Every control has a `name`
- [ ] Input types used: text, email, password, tel, number, date, url
- [ ] `placeholder` and `required` used where they make sense
- [ ] `minlength`, `maxlength`, `min`, and `max` tried
- [ ] One radio group (same name, different values)
- [ ] One checkbox group (same name, different values)
- [ ] One `<select>` with a "Choose one" first option
- [ ] One `<textarea>` with `rows` and `cols`
- [ ] Four `<fieldset>` sections, each with a `<legend>`
- [ ] Submit and reset buttons
- [ ] Tab order goes top to bottom, with no positive `tabindex`
- [ ] Stylesheet styles labels, boxes, `:focus`, buttons, `:hover`, and has a media query

---

## 14. Summary

- `<form>` wraps the whole form. `action` is where the answers go. `method` is how (`get` = in the address bar, `post` = hidden).
- We have no server yet, so we use `action="#"`.
- Every input needs a label (`for` matches `id`) and a `name`.
- The `type` decides what the input accepts: text, email, password, tel, number, date, url, radio, checkbox.
- Radio = pick one. Checkbox = pick any. Same `name` makes a group. `value` is what gets sent.
- `<select>` = dropdown. `<textarea>` = long text.
- `<fieldset>` + `<legend>` split a form into titled sections.
- `required`, `type="email"`, `min`/`max`, and `minlength` let the browser check answers with no JavaScript.
- Keep HTML in a sensible order and the Tab key works without `tabindex`.
- Style forms with `display: block` labels, `width: 100%` + `box-sizing: border-box` boxes, and a visible `:focus` style.
