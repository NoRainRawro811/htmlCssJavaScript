**Before you start:** rename this file to `html12b_SEO_lastname.md`, using your own last name. Watch videos 4–6 and use **Part 2** of `html12_ColorsSeoProtocols_StudyGuide.md` (in this folder) to answer. Put the file in an `html12` folder in your `htmlCssJavaScript` repo. Commit and push when you're done.

**Name:** A.D. Tackett 

---

# Task 12b — Search Engine Optimization (SEO)

Type your answers on the blank line under each **Answer:**, or fix the code inside the code boxes. Explain in your own words where a question asks why.

## 1. How a search engine works

**a.** Put the three steps a search engine uses in order, and describe each one in one sentence of your own.

| Step | Name | What happens |
|---|---|---|
| 1 | Crawling | Follows links that link to the page to see it's reliability. |
| 2 | Indexing | Analysis of things to make them into a database for stored information. |
| 3 | Serving | Giving the results to the user. |

**b.** You just built a new page, but **no other page links to it**. Why might a search engine have trouble finding it? (Hint: think about how crawlers find pages.)

**Answer:** Because there's no reputation that shows that your site is reliable, true, or helpful. 


## 2. Organic vs. paid

**c.** You search for "pizza Medina Ohio." The first two results say **Sponsored**. The next ones do not. Which results are organic and which are paid? Which kind can SEO help with?

**Answer:** SPonsored ones are paid, the organic ones are the non sponsored ones. SEO helps with organic results. 


**d.** A business owner asks, "Why would I spend time on SEO when I could just pay for ads?" Give one reason SEO is still worth it.

**Answer:** Because people tend to trust sources that didn't need to pay their way to the top. 


## 3. Fix the head

This is the `<head>` of a bakery's home page. It works, but it is weak for SEO.

```html
<head>
  <meta charset="UTF-8">
  <title>Home</title>
</head>
```

**e.** Rewrite it below. Add a strong `<title>`, a meta description, and the viewport meta tag. Make up a name and town for the bakery.

```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Baker's Bakery - Home</title>
</head>

```

**f.** Where does the text in your `<title>` show up? Where does the meta description usually show up?

**Answer:** The title is in the tab at the top or side depending on where the tab is, and the meta description is not visible outside of the code. 


## 4. Fix the page

**g.** Rewrite this code to be better for SEO and accessibility. Fix the alt text, the link text, and the file name.

```html
<img src="IMG_4471.jpg" alt="picture">
<a href="page3.html">Click here</a> to see our menu.
```

Your fixed version:

```html
<img src="IMG_4471.jpg" alt="Dog doing kickflips">
<a href="page3.html">Our menu</a>.
```

**h.** A page has three `<h1>` tags: one for the logo, one for the page title, and one for the footer. What is wrong, and how should the headings be set up?

**Answer:** One h1 per page, and they should change the logo to an image, title can stay the same, and the footer can just be a `<p>` tag. 


## 5. Spot the problem

**i.** Here is a meta description someone wrote:

`content="cheap shoes cheap shoes best cheap shoes buy cheap shoes cheap shoes near me"`

What is this called? What will a search engine do about it? Rewrite it as a good description.

**Answer:** It's called a dyslexic person's attempt at searching, and it's likely gonna be showing cheap shoes near the person's location.


**j.** Name **two** SEO choices that also help people who use screen readers. Explain how each one helps both.

**Answer:**


## 6. Your own site

**k.** Write a `<title>` and a meta description for the `index.html` of your DIY website. Then add them to your real `index.html` and push it.

```html


```


## Closing 12b — Vocabulary

| Term | Your definition |
|---|---|
| SEO | |
| Crawler (spider) | |
| Organic results | |
| Meta description | |
| Keyword stuffing | |
| SERP | |
