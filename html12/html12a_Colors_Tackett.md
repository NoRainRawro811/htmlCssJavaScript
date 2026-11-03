**Before you start:** rename this file to `html12a_Colors_lastname.md`, using your own last name. Watch videos 1–3 and use **Part 1** of `html12_ColorsSeoProtocols_StudyGuide.md` (in this folder) to answer. Put the file in an `html12` folder in your `htmlCssJavaScript` repo. Commit and push when you're done.

**Name:** A.D. Tackett 

---

# Task 12a — Web Colors (RGB and Hex)

Type your answers on the blank line under each **Answer:**. Don't just copy the study guide. Explain in your own words where a question asks why.

## 1. How screens make color

**a.** A screen turns its red and blue lights all the way up and leaves green off. What color do you see? Why is mixing light called **additive** color?

**Answer:** Magenta 


**b.** A classmate says, "Hex has fewer colors than RGB because hex codes use fewer digits." Are they right? Explain using the number of choices for each color.

**Answer:** No, they have the same amount of colors. in fact, they're also wrong about the fewer digits thing. Nonetheless, the same colors can all be made. There's #FFFFFF, which is 15+15+15+15+15+15. I honestly don't know what else to say, this feels a bit nondescript. 


## 2. Reading hex codes

**c.** Name the color for each hex code. For the last two, say whether it is a light or dark gray and how you can tell.

| Hex | Color |
|---|---|
| `#FF00FF` | Magenta---Red and green! |
| `#00FFFF` | Cyan |
| `#FFFF00` | Ol' yella! (Yellow) |
| `#CCCCCC` | This'd be light grey, because they're all equal. |
| `#1A1A1A` | This is dark grey. because they're all a darker version of themselves. |

**d.** In `#3C9F12`, which pair is the strongest? What color family will this be?

**Answer:** 9F? Because it's 24? and the rest are lower... and the color family is... green. if that's what you're asking.


**e.** The CSS color name `lime` and the CSS color name `green` are not the same color. Give the hex code for each.

**Answer:** #00FF00 and #008000


## 3. Converting between hex and RGB

**f.** Write each color the other way.

| Given | Write it as |
|---|---|
| `rgb(255, 255, 0)` | hex: #FFFF00 |
| `#0000FF` | rgb: (0, 0, 255) |
| `rgb(0, 0, 0)` | hex: #000000 |
| `#FFFFFF` | rgb: (255, 255, 255) |

**g.** Convert the hex pair `C0` to a normal number. Show your work using the rule in section 1.4 (first digit × 16, plus the second digit). Remember C = 12.

**Answer:** 12 * 16 + 0 = 192 


**h.** `#F80` is short hex. Write it out as a full 6-digit hex code.

**Answer:** #FF8800


## 4. Colors in CSS

**i.** Write CSS that does both of these. Use **hex** for one and **rgb** for the other.
- Makes `h1` text red
- Makes the page (`body`) background white

```css
h1 {
    color: red;
}
body {
    background: white;
}

```

**j.** Write a CSS rule for a class called `.overlay` that makes its background **black and half see-through**. Which number controls the see-through part?

```css
.overlay {
    background-color: rgba(0,0,0,.5);
}

```

**Answer:** The fourth one? It controls opacity, it stands for alpha. 


**k.** Why is yellow text (`#FFFF00`) on a white background (`#FFFFFF`) a bad choice? What would you change?

**Answer:** Because it'd be hard to read. I'd make the background #000000. 


## 5. Your own site

**l.** Open the `styles.css` for your DIY website. Pick one color you used (or choose a new one you like). Write it as a hex code, then explain what the red, green, and blue pairs tell you about the color.

**Answer:** #00bfff, which in CSS is called deepskyblue, and it tells me that.. it's a mix of green and blue...? What're you even asking? 


## Closing 12a — Vocabulary

| Term | Your definition |
|---|---|
| RGB | Red Green Blue. A commonly used way to add or represent color to an exact shade. |
| Hex code | A code for an exact shade of a color. |
| Hexadecimal | What Hex in hex code is short for, and it represents a base 16 system from 0-15. |
| Additive color | A way to make color by mixing light together, making the color brighter. |
| rgba | Red Green Blue Alpha. A commonly used way to add color and transparency to soemthing in CSS. |
