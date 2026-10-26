# Lesson 08 DIY: Add a Contact Form to Your Website

Add a real, styled contact form to the **Contact page** of the website you have been building all year. This is the one graded item for Lesson 08. The walkthrough and `html08_Task.html` are practice.

1. A contact form on `contact.html`, **below** the email link that is already there
2. Styling for the form, added to your existing `styles.css`

Then test, validate, and push with GitHub Desktop.

**Keep your mailto link.** Some visitors would rather just email you. The form goes under it.

**Important for Lesson 09:** give the form `id="contact-form"` and use the ids `name`, `email`, and `message` exactly as shown below. In Lesson 09 you will write JavaScript that finds the form by these ids and checks it before it is sent.

---

## Where Everything Goes

Work in your `DiyWebsite_Lastname` folder at the top of your `htmlCssJavaScript` repo. Only two files change:

```
htmlCssJavaScript/
└── DiyWebsite_Lastname/
    ├── index.html      <- no change
    ├── about.html      <- no change
    ├── contact.html    <- CHANGE: add the form (Part 2)
    ├── gallery.html    <- no change
    ├── template.html   <- no change
    ├── styles.css      <- CHANGE: add form styles at the bottom (Part 3)
    ├── images/
    └── media/
```

| File | What changes |
|---|---|
| `contact.html` | Add a new `<section>` with the form, below your existing contact info and mailto link |
| `styles.css` | Add a "Contact form" block of rules at the bottom, plus a rule inside your existing media query |

Do **not** add a `<style>` block or `style` attributes to `contact.html`. All styling goes in `styles.css`.

---

## Part 1: Plan the Form

Your form should fit your site's topic. Before you type any code, decide (on paper or in a comment):

1. **A radio group (pick one):** why is the visitor contacting you? At least 3 choices.
2. **A checkbox group (pick any):** what are they interested in? At least 3 choices.
3. **A dropdown (select):** one more question with at least 4 choices.

Ideas:

| Site topic | Radio: reason for contacting | Checkboxes: interests | Dropdown |
|---|---|---|---|
| Coffee shop | Question, catering order, feedback | Drinks, pastries, events | Which location |
| Band | Booking, merch question, fan mail | Tour news, new music, merch | How did you hear about us |
| Pet care | Booking, question, feedback | Dogs, cats, small pets | Service wanted |
| Fitness studio | Class question, sign-up, feedback | Yoga, cycling, weights | Preferred class time |
| Tech blog / portfolio | Hire me, question, feedback | Web, games, hardware | How did you find this site |

---

## Part 2: Build the Form (contact.html)

### 2a. Add the section and the form tag

Open `contact.html`. Find your existing contact info and mailto link inside `<main>`. **Below** it, add a new section:

```html
<section id="contact-us">
  <h2>Send Us a Message</h2>
  <p>Fill out the form below. Fields marked * are required.</p>

  <!-- id="contact-form": Lesson 09 JavaScript will use this id. Don't change it.
       action="#": we don't have a server yet, so the form sends back to this same page.
       method="get": the answers show up in the address bar so you can check them. -->
  <form id="contact-form" action="#" method="get">

    <!-- Parts 2b - 2e go in here -->

  </form>
</section>
```

**About action and method.** On a real business site, `action` would be the address of a program on a server that saves the message or emails it to the owner, and `method` would be `post` so the message is not shown in the address bar. Our site is plain HTML files with no server, so `action="#"` sends the answers back to the same page and nothing is saved. That is expected. Using `get` for now lets you see what your form sends.

### 2b. Fieldset 1: About You

Every text-style input needs a `<label>` whose `for` matches the input's `id`, and a `name`.

```html
<fieldset>
  <legend>About You</legend>

  <!-- Keep these three ids: name, email, message (message is in 2d). Lesson 09 uses them. -->
  <label for="name">Name: *</label>
  <input type="text" id="name" name="name" placeholder="First and last name" required>

  <label for="email">Email: *</label>
  <input type="email" id="email" name="email" placeholder="you@example.com" required>

  <!-- Phone is optional, so no required -->
  <label for="phone">Phone:</label>
  <input type="tel" id="phone" name="phone" placeholder="330-555-0100">

  <!-- OPTIONAL: a date input, if it fits your site (a booking date, a visit date).
       Or a number input (party size, number of pets). Delete this if it doesn't fit. -->
  <label for="visitDate">Preferred Date:</label>
  <input type="date" id="visitDate" name="visitDate">
</fieldset>
```

Change the placeholders and the optional field to fit your site. You must have **text, email, and tel or number** at least.

### 2c. Fieldset 2: your radio group and checkbox group

Use your plan from Part 1. Here is the coffee shop version:

```html
<fieldset>
  <legend>Why are you contacting us? *</legend>
  <!-- Radio buttons: same name, different values. Only one can be picked.
       required on the first one makes the whole group required. -->
  <label class="choice"><input type="radio" name="reason" value="question" required> I have a question</label>
  <label class="choice"><input type="radio" name="reason" value="catering"> Catering order</label>
  <label class="choice"><input type="radio" name="reason" value="feedback"> Feedback</label>
</fieldset>

<fieldset>
  <legend>What are you interested in?</legend>
  <!-- Checkboxes: same name, different values. Any number can be checked. -->
  <label class="choice"><input type="checkbox" name="interests" value="drinks"> Drinks</label>
  <label class="choice"><input type="checkbox" name="interests" value="pastries"> Pastries</label>
  <label class="choice"><input type="checkbox" name="interests" value="events"> Events</label>
</fieldset>
```

### 2d. Fieldset 3: dropdown and message

```html
<fieldset>
  <legend>Your Message</legend>

  <label for="location">Which location? *</label>
  <select id="location" name="location" required>
    <!-- Empty value = a "choose one" prompt. required won't accept it. -->
    <option value="">-- Choose one --</option>
    <option value="downtown">Downtown</option>
    <option value="square">On the Square</option>
    <option value="mall">At the Mall</option>
    <option value="campus">Near Campus</option>
  </select>

  <!-- Keep id="message". Lesson 09 uses it. -->
  <label for="message">Message: *</label>
  <textarea id="message" name="message" rows="6" cols="40"
            placeholder="Type your message here" required></textarea>
</fieldset>
```

Use your own dropdown question and choices.

### 2e. Buttons

After the last `</fieldset>`, still inside the form:

```html
<div class="button-group">
  <button type="submit">Send Message</button>
  <button type="reset">Clear Form</button>
</div>
```

### 2f. Tab order

Click in the Name box and press Tab over and over. Every control should light up in order, top to bottom, ending with the buttons.

Because your HTML is in order, **you should not need `tabindex` at all.** Do not add `tabindex="1"`, `"2"`, and so on. That makes Tab jump around. (`tabindex="0"` is only for making a non-form item, like a clickable `<div>`, reachable by Tab. A normal contact form doesn't need it.)

---

## Part 3: Style the Form (styles.css)

Open your `styles.css`. Scroll to the bottom, **above** your media query if it is at the bottom. Add a comment and the form rules. Use **your site's colors and fonts**, not the blue below. Look at the top of your stylesheet for the colors you already use.

```css
/* ===== Contact form ===== */

/* The form as a card, like your other cards */
#contact-form {
  max-width: 600px;
  background-color: white;       /* use your card background color */
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

/* Section boxes and their titles */
#contact-form fieldset {
  border: 1px solid #ccc;
  border-radius: 5px;
  padding: 15px;
  margin: 15px 0;
}

#contact-form legend {
  font-weight: bold;
  padding: 0 8px;
}

/* Each label on its own line, above its box */
#contact-form label {
  display: block;
  margin: 10px 0 5px;
  font-weight: bold;
}

/* Radio and checkbox labels: plain, not bold */
#contact-form .choice {
  font-weight: normal;
}

/* Text-style boxes, the dropdown, and the textarea (not radios or checkboxes) */
#contact-form input[type="text"],
#contact-form input[type="email"],
#contact-form input[type="tel"],
#contact-form input[type="number"],
#contact-form input[type="date"],
#contact-form select,
#contact-form textarea {
  width: 100%;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 1rem;
  font-family: inherit;          /* same font as the rest of your site */
  box-sizing: border-box;        /* width includes padding and border */
}

/* The box the cursor is in: must still be easy to see */
#contact-form input:focus,
#contact-form select:focus,
#contact-form textarea:focus {
  outline: none;
  border-color: #007bff;         /* use your accent color */
  box-shadow: 0 0 5px rgba(0, 123, 255, 0.4);
}

/* Buttons */
#contact-form button {
  padding: 12px 20px;
  margin: 5px 5px 0 0;
  border: none;
  border-radius: 4px;
  font-size: 1rem;
  cursor: pointer;
  background-color: #007bff;     /* use your accent color */
  color: white;
  transition: background-color 0.3s ease;
}

#contact-form button:hover {
  background-color: #0056b3;     /* a darker version of your accent color */
}

/* Reset looks less important than submit */
#contact-form button[type="reset"] {
  background-color: #6c757d;
}
```

Then, **inside the media query you already have** (from Lesson 07), add:

```css
  /* Small screens: full-width buttons, easier to tap */
  #contact-form button {
    width: 100%;
    margin: 5px 0;
  }
```

Why `#contact-form` in front of every rule? So these styles only change the form, not other labels, buttons, or inputs on your site.

**Requirements for the styles:**
- Labels on their own line above their box
- Text boxes, dropdown, and textarea full width with padding and `box-sizing: border-box`
- A visible `:focus` style (never remove the outline without replacing it)
- Buttons styled, with a `:hover` color
- Colors that match the rest of your site
- A small-screen rule inside your media query
- Font sizes in `rem`

---

## Part 4: Test and Push

1. Open `contact.html`. The nav, header, footer, and mailto link still work.
2. Click each label. The cursor or check goes to the right control.
3. Click **Send Message** with the form empty. The browser stops you at the first required field.
4. Type an email with no @ sign. The browser stops you.
5. Pick a radio button, then another. Only one stays picked. Checkboxes: several can be checked.
6. Fill in everything and click **Send Message**. Look at the address bar: you should see `?name=...&email=...`. Every field you filled in should be there. A field that's missing has no `name`.
7. Click **Clear Form**. Everything empties.
8. Tab through the whole form. It goes top to bottom and you can always see which box you are in.
9. Check a phone width: open the page in a Chrome **Guest** window (copy the address from Live Preview's address bar, click your profile picture in Chrome > **Guest**, and paste it in), right-click > **Inspect**, then click the **device toolbar** button (phone-and-tablet icon). The form still fits and the buttons go full width.
10. Run `contact.html` through https://validator.w3.org/ and fix the errors.
11. In GitHub Desktop, commit with a message like `Add contact form` and push. Check on github.com that `contact.html` and `styles.css` changed.

---

## Checklist

**The form (contact.html)**
- [ ] Form is in a new section below the existing mailto link (the mailto link is still there)
- [ ] `<form id="contact-form" action="#" method="get">`
- [ ] Ids `name`, `email`, and `message` used exactly
- [ ] Every text-style input, select, and textarea has a `<label>` with `for` matching its `id`
- [ ] Every control has a `name`
- [ ] Input types: text, email, and tel or number (date optional)
- [ ] One radio group, 3+ choices, same name
- [ ] One checkbox group, 3+ choices, same name
- [ ] One `<select>` with a "Choose one" first option and 4+ real choices
- [ ] One `<textarea>` for the message
- [ ] `required` on name, email, message, the radio group, and the select
- [ ] `placeholder` on the text boxes and textarea
- [ ] At least 2 `<fieldset>` sections, each with a `<legend>`
- [ ] Submit and reset buttons
- [ ] Tab order is top to bottom, no positive `tabindex`
- [ ] Fits your site topic (not the coffee shop example, unless your site is a coffee shop)

**The styles (styles.css)**
- [ ] Form rules are in `styles.css`, not in `contact.html`
- [ ] Labels, boxes, fieldsets, legend, and buttons styled
- [ ] Visible `:focus` style and a button `:hover`
- [ ] Colors match your site
- [ ] Small-screen rule inside your media query

**Finish**
- [ ] All tests in Part 4 pass
- [ ] `contact.html` passes the validator
- [ ] Pushed with GitHub Desktop

---

## Grading

| Criteria | Looking for |
|---|---|
| **Form structure** | `id="contact-form"`, action and method, fieldsets with legends, submit and reset buttons, mailto link kept |
| **Controls** | Text, email, tel or number, a radio group, a checkbox group, a select, and a textarea, all with names, fitting the site topic |
| **Labels and required** | Every box has a matching label; required and placeholder used on the right fields; the browser stops an empty or bad submit |
| **Styling** | Form styled in `styles.css` with the site's colors, visible focus, button hover, works on a narrow screen |
| **Site still works** | Same header, nav, and footer on every page; every link works; nothing broken |
| **Valid and pushed** | `contact.html` passes the validator; pushed to GitHub |

**How it is graded:**
- **Complete:** Everything in the checklist is there, the form fits your site, and it looks like part of your site.
- **Mostly complete:** The form works, but a few things are missing (a control, a label, focus style, or the media query rule).
- **Started:** The form is there but several controls are missing, labels aren't connected, or it isn't styled.
- **Missing:** Nothing pushed.

---

## If something goes wrong

- **Clicking a label does nothing:** the label's `for` doesn't match the input's `id`. They must be spelled the same, including capital letters.
- **More than one radio button stays picked:** the radio buttons don't all have the same `name`.
- **A field is missing from the address bar after you submit:** that control has no `name`.
- **The form submits even when it's empty:** `required` is missing, or the button is outside the `<form>`.
- **The dropdown accepts "-- Choose one --":** that option needs `value=""` and the select needs `required`.
- **The boxes stick out past the right edge:** add `box-sizing: border-box`.
- **Radio buttons and checkboxes are huge or stretched:** your selector hits all inputs. Use the `input[type="text"]` style list, not plain `input`.
- **The textarea font looks different:** add `font-family: inherit`.
- **Your other buttons or labels on the site changed:** start each form rule with `#contact-form`.
- **Nothing styled at all:** check that `contact.html` still has `<link rel="stylesheet" href="styles.css">` and that you saved `styles.css`.
- **Validator error "The for attribute of the label element must refer to a form control":** a `for` has a typo, or names an id that doesn't exist.
- **Page reloads after Send and your answers are gone:** that is normal. There is no server yet. Look at the address bar to see what was sent.
