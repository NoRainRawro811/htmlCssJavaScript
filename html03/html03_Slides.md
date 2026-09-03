---
marp: true
theme: default
class: invert
paginate: true
---

# Lesson 03: Links & Navigation

## Web Development
### Medina County Career Center

---

<!-- _header: "Sub-Lesson 03a — Anchor Tags & Links" -->

## What is the Anchor Tag?

The `<a>` (anchor) tag creates **links** to other pages, files, or websites.

```html
<a href="destination">Link Text</a>
```

- **`href`** = where the link goes (URL or file path)
- **Link Text** = what users see and click on
- Without an `href`, the tag does nothing

```html
<a href="about.html">About Us</a>
<a href="https://google.com">Visit Google</a>
<a href="#top">Back to Top</a>
```

---

<!-- _header: "Sub-Lesson 03a — Anchor Tags & Links" -->

## Absolute vs. Relative Links

**Absolute Link** = complete URL (works from anywhere)
```html
<a href="https://www.google.com">Google</a>
<a href="https://example.com/pages/about.html">About</a>
```

**Relative Link** = path from current page (works within your site)
```html
<!-- Same folder -->
<a href="about.html">About</a>

<!-- Different folder -->
<a href="pages/contact.html">Contact</a>

<!-- Parent folder -->
<a href="../index.html">Home</a>
```

Use **relative links** for pages on your own site. Use **absolute links** for external websites.

---

<!-- _header: "Sub-Lesson 03a — Anchor Tags & Links" -->

## The Target Attribute

The **`target`** attribute controls where the link opens.

```html
<!-- Opens in same tab (default) -->
<a href="about.html">About</a>

<!-- Opens in new tab -->
<a href="about.html" target="_blank">About (new tab)</a>

<!-- Other values (less common) -->
<a href="about.html" target="_self">Same window</a>
<a href="about.html" target="_parent">Parent frame</a>
```

Use `target="_blank"` for **external links** so users don't lose your site.

---

<!-- _header: "Sub-Lesson 03a — Anchor Tags & Links" -->

## Page Anchors: Linking Within a Page

Use the **`id`** attribute to mark a spot on a page, then link to it with a **fragment identifier** (`#id`).

```html
<!-- Mark the location with id -->
<h2 id="services">Our Services</h2>

<!-- Link to that location -->
<a href="#services">Jump to Services</a>

<!-- From another page -->
<a href="index.html#services">View Services</a>

<!-- Common: "Back to Top" -->
<header id="top">...</header>
<a href="#top">Back to Top</a>
```

Each `id` must be unique on the page. Use hyphens or camelCase for names.

---

<!-- _header: "Sub-Lesson 03b — Email & Download Links" -->

## Email Links: `mailto:`

Create a link that opens the user's email client with a pre-filled recipient.

```html
<a href="mailto:contact@example.com">Email Us</a>

<!-- With subject and body -->
<a href="mailto:contact@example.com?subject=Help&body=I need assistance">Contact Support</a>

<!-- Display text can be different -->
<a href="mailto:info@company.com">info@company.com</a>
```

When clicked, it opens the default email app. Use for **contact pages** and **footer links**.

---

<!-- _header: "Sub-Lesson 03b — Email & Download Links" -->

## Download Links

Use `download` attribute to force file downloads instead of opening in the browser.

```html
<!-- Simple download -->
<a href="files/resume.pdf" download>Download Resume</a>

<!-- Rename the downloaded file -->
<a href="files/resume.pdf" download="MyResume.pdf">Download Resume</a>

<!-- Download image -->
<a href="images/photo.jpg" download="Profile-Photo.jpg">Save Photo</a>
```

Without `download`, PDFs/images usually open in the browser. With it, they save to Downloads folder.

---

<!-- _header: "Sub-Lesson 03b — Email & Download Links" -->

## Building Navigation Structures

A good site has consistent navigation.

```html
<header>
  <nav>
    <a href="index.html">Home</a>
    <a href="about.html">About</a>
    <a href="services.html">Services</a>
    <a href="contact.html">Contact</a>
  </nav>
</header>

<main>
  <!-- Page content -->
</main>

<footer>
  <a href="index.html">Home</a>
  <a href="privacy.html">Privacy Policy</a>
  <a href="mailto:support@example.com">Support</a>
</footer>
```

Navigation appears in `<header>` and/or `<footer>`. Keep it consistent across all pages.

---

<!-- _header: "Sub-Lesson 03b — Email & Download Links" -->

## Site Structure Tips

**Folder layout for a 3-page site:**
```
my-site/
  index.html          (Home page)
  about.html          (About page)
  contact.html        (Contact page)
  styles/
    style.css
  images/
    logo.png
  files/
    resume.pdf        (downloadable)
```

**Relative link examples:**
```html
<!-- From any page to home -->
<a href="index.html">Home</a>

<!-- To external site -->
<a href="https://google.com" target="_blank">Google</a>

<!-- Email link -->
<a href="mailto:hello@example.com">Email</a>
```

---

<!-- _header: "Key Takeaways" -->

## What You Learned

1. Use `<a href="">` to create links
2. Understand absolute links (full URLs) vs. relative links (local paths)
3. Use `target="_blank"` for external links
4. Create page anchors with `id` and link with `#id`
5. Use `mailto:` for email links
6. Use `download` attribute for files
7. Build consistent navigation in header and footer
8. Organize files in folders for larger sites

**Next: Build a working 3-page site with navigation!**

---
