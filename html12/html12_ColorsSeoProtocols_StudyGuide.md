# Web Design Exam Review: Colors, SEO, and Protocols

This guide covers three topics for the state Web Design exam: **web colors (RGB and hex)**, **Search Engine Optimization (SEO)**, and **internet protocols**. Watch the videos first, then read the section for each topic. Practice questions with answers are at the end.

## Table of Contents

- [Videos](#videos)
- [Part 1: Web Colors (RGB and Hex)](#part-1-web-colors-rgb-and-hex)
  - [1.1 How screens make color](#11-how-screens-make-color)
  - [1.2 RGB values](#12-rgb-values)
  - [1.3 Hex codes](#13-hex-codes)
  - [1.4 Counting in hex](#14-counting-in-hex)
  - [1.5 Reading a hex code](#15-reading-a-hex-code)
  - [1.6 Writing colors in CSS](#16-writing-colors-in-css)
- [Part 2: Search Engine Optimization (SEO)](#part-2-search-engine-optimization-seo)
  - [2.1 How a search engine works](#21-how-a-search-engine-works)
  - [2.2 What helps a page rank](#22-what-helps-a-page-rank)
  - [2.3 Organic vs. paid results](#23-organic-vs-paid-results)
  - [2.4 SEO you control in your HTML](#24-seo-you-control-in-your-html)
  - [2.5 Weak vs. strong choices](#25-weak-vs-strong-choices)
  - [2.6 SEO and accessibility](#26-seo-and-accessibility)
- [Part 3: Internet Protocols](#part-3-internet-protocols)
  - [3.1 What a protocol is](#31-what-a-protocol-is)
  - [3.2 IP addresses and DNS](#32-ip-addresses-and-dns)
  - [3.3 Packets and TCP/IP](#33-packets-and-tcpip)
  - [3.4 HTTP: request and response](#34-http-request-and-response)
  - [3.5 HTTPS: secure HTTP](#35-https-secure-http)
  - [3.6 FTP: uploading files](#36-ftp-uploading-files)
  - [3.7 The parts of a URL](#37-the-parts-of-a-url)
  - [3.8 Putting it together](#38-putting-it-together)
- [Vocabulary](#vocabulary)
- [Practice Questions](#practice-questions)
- [Answer Key](#answer-key)

---

## Videos

Watch these in order. Video numbers match the slides.

| # | Topic | Video | Channel | Length |
|---|---|---|---|---|
| 1 | Colors | [RGB color model (Pixar in a Box)](https://youtu.be/T0jzClmP2pc) | Khan Academy | 2:49 |
| 2 | Colors | [How Do Hex Color Code and RGB Color Work?](https://youtu.be/st5LSDxtKY4) | GoDaddy Developer | 4:25 |
| 3 | Colors | [How Do HEX Color Codes Work? (in 60 seconds)](https://youtu.be/c56x1aj2CPA) | PolyMatter | 1:00 |
| 4 | SEO | [How Google Search Works (in 5 minutes)](https://youtu.be/0eKVizvYSUQ) | Google | 5:15 |
| 5 | SEO | [What Is Search Engine Optimization](https://youtu.be/hF515-0Tduk) | Search Engine Land | 3:29 |
| 6 | SEO | [SEO Meta Tags Tutorial](https://youtu.be/SGZr1da5tH8) | Simplilearn | 1:36 |
| 7 | Protocols | [The Internet: IP Addresses & DNS](https://youtu.be/5o8CwafCxnU) | Code.org | 6:44 |
| 8 | Protocols | [The Internet: Packets, Routing & Reliability](https://youtu.be/AYdF7b3nMto) | Code.org | 6:25 |
| 9 | Protocols | [The Internet: HTTP & HTML](https://youtu.be/kBXQZMmiA4s) | Code.org | 7:07 |
| 10 | Protocols | [SSL, TLS, HTTP, HTTPS Explained](https://youtu.be/hExRDVZHhig) | PowerCert Animated Videos | 6:31 |
| 11 | Protocols | [What is FTP? And how does it work?](https://youtu.be/HI0Oh4NJqcI) | Hostinger Academy | 3:38 |

Backup FTP video (no ad at the end): [FTP, SFTP, TFTP Explained](https://youtu.be/tOj8MSEIbfA) (PowerCert, 7:54).

The tasks for this review are in this folder: `html12a_Colors_lastname.md`, `html12b_SEO_lastname.md`, `html12c_Protocols_lastname.md`. The slides for each topic are in the `slides` folder.

---

## Part 1: Web Colors (RGB and Hex)

### 1.1 How screens make color

A screen is made of tiny dots called **pixels**. Each pixel has three small lights: **red**, **green**, and **blue**. By turning each light up or down, the screen can make almost any color. This is called the **RGB color model**.

Mixing light is **additive**: the more light you add, the brighter the color gets.

| Light mixed | Color you see |
|---|---|
| Red + Green | Yellow |
| Red + Blue | Magenta |
| Green + Blue | Cyan |
| Red + Green + Blue (all full) | White |
| No light at all | Black |

Paint and printer ink work the opposite way (mixing all paint colors gets darker). That is a different model called CMYK. Web pages use RGB.

### 1.2 RGB values

In CSS, an RGB color gives a number for each light:

```css
rgb(red, green, blue)
```

- Each number goes from **0** (none of that color) to **255** (full amount).
- That is **256 levels** for each color. (A computer stores each one in one byte, which holds 0 through 255.)
- 256 × 256 × 256 = about **16.7 million** possible colors.
- Hex codes can make **exactly the same colors**. Each hex pair goes from `00` to `FF`, which is also 256 choices (16 × 16). Hex just writes the number with fewer digits.

| RGB value | Color |
|---|---|
| `rgb(255, 0, 0)` | Red |
| `rgb(0, 255, 0)` | Green (CSS name: lime) |
| `rgb(0, 0, 255)` | Blue |
| `rgb(255, 255, 255)` | White |
| `rgb(0, 0, 0)` | Black |
| `rgb(128, 128, 128)` | Gray |

### 1.3 Hex codes

A **hex code** is the same three numbers written in a shorter way.

```
#FF8800
 RRGGBB
```

- Every hex code starts with **#**.
- Then **6 digits**: 2 for red, 2 for green, 2 for blue.
- The order is always **RR GG BB**.

In `#FF8800`: red is `FF` (full), green is `88` (about half), blue is `00` (none). Full red plus some green makes **orange**.

### 1.4 Counting in hex

Normal numbers are **base 10** (digits 0–9). Hex is short for **hexadecimal**, which is **base 16**. It needs 16 digits, so after 9 it uses letters:

```
0 1 2 3 4 5 6 7 8 9 A B C D E F
```

A = 10, B = 11, C = 12, D = 13, E = 14, F = 15.

You do not need to convert every pair on the exam. Know these three:

| Hex pair | Normal number | Meaning |
|---|---|---|
| `00` | 0 | None of that color |
| `80` | 128 | About half |
| `FF` | 255 | Full amount |

**How to convert a pair (if you want to):** first digit × 16, plus the second digit.
`80` = 8 × 16 + 0 = 128. `FF` = 15 × 16 + 15 = 255.

### 1.5 Reading a hex code

Look for the **biggest pair**. That color is the strongest.

| Hex | What to notice | Color |
|---|---|---|
| `#FF0000` | Only red is on | Red |
| `#0000FF` | Only blue is on | Blue |
| `#FFFF00` | Red and green are full | Yellow |
| `#FF00FF` | Red and blue are full | Magenta |
| `#00FFFF` | Green and blue are full | Cyan |
| `#808080` | All three pairs are equal | Gray |
| `#333333` | All equal and low | Dark gray |
| `#FFFFFF` | All full | White |
| `#000000` | All off | Black |

**Rule:** when all three pairs are the same, the color is a **gray**. Low numbers = dark gray. High numbers = light gray.

**Trick question to watch for:** the CSS color name for `#00FF00` is **lime**. The CSS name **green** is a darker green, `#008000`.

### 1.6 Writing colors in CSS

You can write a color as a **name**, a **hex code**, or an **RGB value**. All three work.

```css
/* color = the text color */
h1 {
  color: navy;                        /* a color name */
}

p {
  color: #333333;                     /* a hex code: dark gray text */
}

/* background-color = the color behind the element */
body {
  background-color: rgb(240, 248, 255);   /* an RGB value: very light blue */
}

/* rgba adds a 4th number: how see-through it is (0 = clear, 1 = solid) */
.box {
  background-color: rgba(0, 0, 255, 0.5); /* blue, half see-through */
}

/* Short hex: 3 digits, each one doubled. #F00 is the same as #FF0000 */
.warning {
  color: #F00;
}
```

**What is rgba?** `rgba` is RGB with a 4th number added. The **a** stands for **alpha**, which means how see-through (transparent) the color is. Alpha goes from **0** (completely clear, you can't see it) to **1** (completely solid). For example, `rgba(0, 0, 0, 0.5)` is black that is half see-through, so whatever is behind it shows through. It is often used for shadows and for dark boxes placed over pictures so the text on top is easy to read.

**Contrast matters.** Use dark text on a light background, or light text on a dark background, so everyone can read it. This is part of making a site accessible.

---

## Part 2: Search Engine Optimization (SEO)

### 2.1 How a search engine works

A search engine (Google, Bing, DuckDuckGo) works in three steps:

| Step | What happens |
|---|---|
| **1. Crawl** | Programs called **crawlers** (or **spiders**) follow links from page to page to find pages. |
| **2. Index** | The search engine stores what each page is about in a huge list, like the index in the back of a book. |
| **3. Rank** | When someone searches, it sorts the matching pages and shows the most useful ones first. |

Search engines also look for **spam**: pages that try to trick the ranking. Those pages get pushed down or removed.

### 2.2 What helps a page rank

| Factor | What it means |
|---|---|
| Relevance | The words on the page match what the person searched for |
| Links | Other trusted sites link to the page |
| Quality | Useful, original content, not copied |
| Usability | The page loads fast and works on phones |
| Freshness | Content is kept up to date |

**Keyword stuffing** means repeating the same search words over and over to trick the ranking. Search engines treat it as spam, and it hurts the page.

### 2.3 Organic vs. paid results

**SEO** stands for **Search Engine Optimization**: making pages easy for search engines to find and understand, so they show up **higher in the search results**.

When you search for something, the page of results is called the **SERP** (Search Engine Results Page). It has two kinds of results mixed together:

- **Paid results** are ads. A business paid the search engine to put its link there. They are usually at the very top and are marked **"Sponsored"** or **"Ad"**.
- **Organic results** are everything else. Nobody paid for them. The search engine chose them because it thinks they are the best match for what you typed.

**Example:** you search for "pizza Medina Ohio."

```
Sponsored   Big Chain Pizza – Order Online Now       <- paid: the business bought this spot
Sponsored   Pizza Delivery App – $5 Off First Order  <- paid
            Tony's Pizza – Medina, OH                <- organic: earned by being a good match
            Best Pizza in Medina (local news list)   <- organic
```

SEO only helps with the **organic** results. Paying for an ad is advertising, not SEO.

| Question | Organic results | Paid results |
|---|---|---|
| Does the business pay the search engine? | No, it is free | Yes, the business pays |
| How does the link get on the page? | The search engine decides it is a good match | The business buys the spot |
| Is it labeled? | No label | Marked "Sponsored" or "Ad" |
| Other name | Natural results | Pay-per-click (PPC) ads: the business pays each time someone clicks |
| Does SEO help it? | Yes | No |
| What happens if the business stops paying? | Nothing. It keeps showing up | The ad goes away |

**Why do SEO if you can just buy ads?** Organic traffic is free and keeps coming without paying for every click, and many people skip past the ads and click the first organic result.

### 2.4 SEO you control in your HTML

These are called **on-page SEO**. You control all of them in your own code.

| Item | What to do |
|---|---|
| `<title>` | A clear, unique title for every page |
| Meta description | A 1–2 sentence summary of the page |
| Headings | One `<h1>` per page, then `<h2>`, `<h3>` in order (do not skip levels) |
| Alt text | Describe every image in its `alt` attribute |
| Link text | Say where the link goes, not "click here" |
| File names and URLs | Short, readable words: `about-us.html`, not `page7.html` |
| Viewport meta tag | Makes the page work on phones |

The title and meta description go in the `<head>`. Neither one shows on the page itself.

```html
<head>
  <meta charset="UTF-8">

  <!-- Makes the page fit phone screens. Mobile-friendly pages rank better. -->
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <!-- Shows in the browser tab AND as the blue link in search results -->
  <title>Dog Grooming in Medina, OH | Clean Paws</title>

  <!-- Often shown as the gray text under the link in search results -->
  <meta name="description" content="Baths, haircuts, and nail trims for dogs of all sizes. Book online.">
</head>
```

How that page can look in search results:

> **Dog Grooming in Medina, OH | Clean Paws**
> Baths, haircuts, and nail trims for dogs of all sizes. Book online.

(Clean Paws is a made-up business for the example.)

### 2.5 Weak vs. strong choices

| Item | Weak | Strong |
|---|---|---|
| Title | `Home` | `Dog Grooming in Medina, OH \| Clean Paws` |
| Alt text | `alt="img1"` | `alt="Golden retriever after a bath"` |
| Link text | Click here | See our grooming prices |
| File name | `page2.html` | `prices.html` |
| Headings | Three `<h1>` tags | One `<h1>`, then `<h2>` sections |

```html
<!-- Weak: tells nobody anything -->
<img src="img1.jpg" alt="img1">
<a href="page2.html">Click here</a>

<!-- Strong: a screen reader and a search engine both understand it -->
<img src="golden-retriever-bath.jpg" alt="Golden retriever after a bath">
<a href="prices.html">See our grooming prices</a>
```

### 2.6 SEO and accessibility

Good SEO and good accessibility overlap. Building for everyone also helps a page get found.

- **Alt text** helps screen readers and image search.
- **Heading order** helps screen readers and search engines read the page outline.
- **Clear link text** tells everyone where a link goes.
- **Mobile-friendly** pages are easier to use and rank better.

---

## Part 3: Internet Protocols

### 3.1 What a protocol is

A **protocol** is a set of rules that computers agree to follow so they can communicate. It works like two people agreeing to speak the same language.

| Protocol | Stands for | Its job |
|---|---|---|
| HTTP | HyperText Transfer Protocol | Sends web pages to the browser |
| HTTPS | HyperText Transfer Protocol Secure | Same as HTTP, but encrypted |
| FTP | File Transfer Protocol | Moves files to and from a server |
| TCP/IP | Transmission Control Protocol / Internet Protocol | Addresses data and makes sure it all arrives |
| DNS | Domain Name System | Turns a name like example.com into an IP address |

### 3.2 IP addresses and DNS

An **IP address** is a number that identifies a device on a network, like a mailing address for a computer.

```
IPv4 example:  192.168.1.25
               4 numbers, separated by dots, each from 0 to 255
```

- `192.168.1.256` is **not** valid: 256 is too big.
- **IPv6** addresses are much longer. They were created because the world is running out of IPv4 addresses.

People remember names like `example.com`, but computers need numbers. **DNS** (Domain Name System) is the internet's phone book: it looks up a domain name and returns its IP address.

```
You type:      example.com
DNS answers:   203.0.113.10   (example number)
Browser then:  connects to that IP address
```

### 3.3 Packets and TCP/IP

Files are not sent across the internet in one piece. They are broken into small pieces called **packets**.

1. The file is split into packets.
2. **Routers** send each packet along whatever path is open. Packets from the same file can take different paths.
3. The packets arrive, maybe out of order, and are put back together.

Two protocols work together:

| Protocol | Its job |
|---|---|
| **IP** (Internet Protocol) | Puts the address on each packet and gets it to the right place |
| **TCP** (Transmission Control Protocol) | Numbers the packets, checks that they all arrived, and asks for any missing ones to be sent again |

Together they are called **TCP/IP**, the main protocols the internet runs on.

### 3.4 HTTP: request and response

**HTTP** works as a **request** and a **response**.

1. The browser (the **client**) sends a request: "Please send me `/about.html`."
2. The **server** sends back a response: a status code and the HTML.
3. The browser reads the HTML and draws the page.

```
Request (from the browser):    GET /about.html
Response (from the server):    200 OK   + the HTML for the page
```

| Status code | Meaning |
|---|---|
| 200 | OK: here is the page |
| 404 | Not Found: there is no page at that address |
| 500 | Server error: something broke on the server |

You have used HTTP methods already in Lesson 08 forms: `method="get"` asks for something, and `method="post"` sends data to the server.

### 3.5 HTTPS: secure HTTP

**HTTPS** is HTTP with **encryption**. The data is scrambled so anyone who intercepts it cannot read it.

| | HTTP | HTTPS |
|---|---|---|
| Data sent as | Plain text anyone could read | Encrypted (scrambled) |
| Uses | Nothing extra | SSL/TLS and a certificate |
| Usual port | 80 | 443 |
| Browser shows | "Not secure" | Padlock icon |

- **SSL** is the older name; **TLS** is the newer, safer version. People still say "SSL certificate."
- The **certificate** proves the website is who it says it is.
- Any page with a login, password, or payment form should use HTTPS.

### 3.6 FTP: uploading files

**FTP** (File Transfer Protocol) moves files between your computer and a server. In web design, it is used to **publish a website**: upload the HTML, CSS, and image files to the web host.

- You use an **FTP client** (for example, FileZilla) to log in to the server and move files.
- FTP normally uses **port 21**.
- Plain FTP is **not encrypted**. **SFTP** is the secure version.
- **Upload** = your computer → server. **Download** = server → your computer.

Our class publishes with Firebase Hosting, but the idea is the same: get the site's files onto a web server.

### 3.7 The parts of a URL

**URL** stands for **Uniform Resource Locator**: the full address of a page.

```
https://www.example.com/products/shoes.html
```

| Part | Example | What it is |
|---|---|---|
| Protocol | `https://` | The rules used to send the page |
| Subdomain | `www` | A part of the site. It is not always `www`: in `library.example.edu`, the subdomain is `library` |
| Domain name | `example` | The site's name |
| Top-level domain (TLD) | `.com` | The ending: `.com`, `.org`, `.edu`, `.gov` |
| Path | `/products/` | The folder on the server |
| File name | `shoes.html` | The file being requested |

### 3.8 Putting it together

What happens when you type a URL and press Enter:

1. **DNS** looks up the domain name and finds the server's IP address.
2. **TCP/IP** opens a connection to that address.
3. The browser sends an **HTTPS** request for the page.
4. The **server** sends back the HTML, CSS, and images in packets.
5. The **browser** puts the packets back together and draws the page.

FTP is not in this list. It is used earlier, to put the files on the server before anyone visits.

---

## Vocabulary

| Term | Meaning |
|---|---|
| Additive color | Making color by mixing light; more light = brighter |
| Alt text | An image's `alt` attribute; describes the image |
| Crawler (spider) | A program that follows links to find web pages |
| DNS | Domain Name System; turns domain names into IP addresses |
| Encryption | Scrambling data so only the right receiver can read it |
| FTP / SFTP | File Transfer Protocol / its secure version |
| Hex code | A color written as # and 6 hex digits (RR GG BB) |
| Hexadecimal | Base 16 counting: 0–9 and A–F |
| HTTP / HTTPS | Protocol for sending web pages / its encrypted version |
| Index (search) | The search engine's stored list of what pages are about |
| IP address | A number that identifies a device on a network |
| Keyword stuffing | Repeating search words to trick rankings; treated as spam |
| Meta description | A summary in the `<head>` often shown in search results |
| Organic results | Unpaid search results |
| Packet | A small piece of data sent across a network |
| Protocol | A set of rules computers follow to communicate |
| RGB | Red, Green, Blue; each from 0 to 255 |
| rgba | RGB plus a 4th number, alpha, for how see-through the color is (0 = clear, 1 = solid) |
| SEO | Search Engine Optimization |
| SERP | Search Engine Results Page |
| SSL / TLS | Encryption used by HTTPS (TLS is the newer one) |
| TCP/IP | The protocol pair that addresses and reliably delivers packets |
| TLD | Top-level domain, like .com or .org |
| URL | Uniform Resource Locator; a page's full address |

---

## Practice Questions

**Colors**

1. What color is `#00FF00`?
2. What color is `rgb(255, 255, 255)`?
3. Write pure blue as a hex code.
4. What is the highest number allowed in `rgb()`?
5. In `#1A2B3C`, which pair is the green value?
6. What kind of color is `#555555`?
7. What does the 4th number in `rgba(0, 0, 0, 0.3)` control?
8. Which CSS property sets the color behind an element?

**SEO**

9. What does SEO stand for?
10. Name the three steps a search engine uses.
11. Which tag sets the text in the browser tab and the link in search results?
12. Where in the HTML does the meta description go?
13. Rewrite this to be better for SEO: `<a href="page3.html">Click here</a>`
14. What is the difference between organic and paid results?
15. What is keyword stuffing, and why is it bad?

**Protocols**

16. What is a protocol?
17. Which protocol turns `example.com` into an IP address?
18. Which protocol would you use to upload your website files to a server?
19. What does the padlock icon in the browser mean?
20. What does a 404 status code mean?
21. Is `10.0.300.5` a valid IPv4 address? Why or why not?
22. What does TCP do with packets?
23. In `https://shop.example.org/cart/view.html`, name the protocol, the TLD, and the file name.

---

## Answer Key

1. Green (the CSS name is lime)
2. White
3. `#0000FF`
4. 255
5. `2B`
6. A gray (all three pairs are equal), a medium-dark gray
7. How see-through the color is (0 = clear, 1 = solid); 0.3 is mostly see-through
8. `background-color`
9. Search Engine Optimization
10. Crawl, index, rank
11. `<title>`
12. In the `<head>`
13. Something like `<a href="prices.html">See our prices</a>`: a readable file name and link text that says where it goes
14. Organic results are free and earned by being a good match; paid results are ads the business pays for
15. Repeating search words over and over to trick the ranking; search engines treat it as spam and rank the page lower
16. A set of rules computers follow so they can communicate
17. DNS
18. FTP (or SFTP for a secure transfer)
19. The site uses HTTPS: the connection is encrypted with SSL/TLS
20. Page not found
21. No. Each number must be from 0 to 255, and 300 is too big.
22. Numbers them, checks that they all arrived, and asks for missing ones to be sent again
23. Protocol: `https://`; TLD: `.org`; file name: `view.html`
