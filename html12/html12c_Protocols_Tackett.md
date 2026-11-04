**Before you start:** rename this file to `html12c_Protocols_lastname.md`, using your own last name. Watch videos 7–11 and use **Part 3** of `html12_ColorsSeoProtocols_StudyGuide.md` (in this folder) to answer. Put the file in an `html12` folder in your `htmlCssJavaScript` repo. Commit and push when you're done.

**Name:** Aurora Tackett

---

# Task 12c — Internet Protocols

Type your answers on the blank line under each **Answer:**, or fill in the tables. Explain in your own words where a question asks why.

## 1. Which protocol?

**a.** For each situation, write the protocol that does the job: **HTTP, HTTPS, FTP, SFTP, DNS, TCP, or IP**.

| Situation | Protocol |
|---|---|
| You type `example.com` and your computer needs its IP address | DNS |
| You upload your website's files to a web host | FTP |
| You log in to your bank's website | SFTP |
| A server sends a plain web page to your browser | TCP |
| Packet 7 of a file never arrived, so it gets sent again | HTTP |
| Each packet needs an address so it reaches the right computer | IP |
| You upload files to a server and want the transfer encrypted | HTTPS |

**b.** In your own words, what is a protocol? Give an example from everyday life of two people following the same "rules" so they understand each other.

**Answer:** A protocol is pretty much a set of rules---like a function in Python, when it's time to do it, it's done that way. Like... A fire drill, we're expected to do whatever it is we need to do during a fire drill once one is called. 


## 2. IP addresses and DNS

**c.** Which of these are valid IPv4 addresses? Write **Valid** or **Not valid**, and give the reason for any that are not.

| Address | Valid? | Reason |
|---|---|---|
| `192.168.0.1` | Valid | |
| `10.0.300.5` | Not valid | a number exceeds 255 |
| `172.16.4` | Not valid | not enough numbers |
| `8.8.8.8` | Valid | |

**d.** DNS is called the internet's "phone book." Explain why that comparison makes sense.

**Answer:** Because it's every number for every website. 


## 3. Packets

**e.** A photo is sent across the internet. It is split into 20 packets, and they take different paths. Packet 12 arrives last and packet 5 never arrives at all. Explain what happens, and which protocol handles it.

**Answer:** Probably, like... HTTP, or something, I don't fully understand the question. 


## 4. HTTP and HTTPS

**f.** Write the status code for each situation.

| Situation | Status code |
|---|---|
| The page loaded fine | Status: Fine |
| You typed a page name that does not exist | ERR:[TYPED WORDS] NOT FOUND |
| Something broke on the server | ERR: SERVER ERROR, RESTART REQUIRED |

**g.** A website has a login form but uses `http://` instead of `https://`. What is the risk? What would the browser show?

**Answer:** The browser is not secure. It'd show everything about the page or smth, idk.


**h.** What do SSL and TLS have to do with HTTPS? Which one is newer?

**Answer:** TLS is newer, but they both likely have to do with the transfering of files.


## 5. FTP

**i.** What is FTP used for in web design? Why is SFTP a better choice than plain FTP?

**Answer:** SFTP is literally just the secure version of FTP, both transfer files, just SFTP does it more securely.


## 6. The parts of a URL

**j.** Break each URL into its parts.

`https://www.medinapets.com/dogs/grooming.html`

| Part | Answer |
|---|---|
| Protocol | https |
| Subdomain | www. |
| Domain name | medinapets |
| Top-level domain (TLD) | .com |
| Path | /dogs/ |
| File name | grooming.html |

`http://library.example.edu/books/index.html`

| Part | Answer |
|---|---|
| Protocol | http |
| Subdomain | library. |
| Domain name | example |
| Top-level domain (TLD) | .edu |
| Path | /books/ |
| File name | index.html |

**k.** Is the second URL secure? How can you tell?

**Answer:** No, because it has HTTP and not HTTPS


## 7. Putting it together

**l.** These steps happen when you type a URL and press Enter, but they are out of order. Number them 1–5.

| Order | Step |
|---|---|
| 5 | The browser puts the packets back together and draws the page |
| 3 | DNS finds the server's IP address |
| 2 | The browser sends an HTTPS request for the page |
| 1 | TCP/IP opens a connection to the server |
| 4 | The server sends back the HTML, CSS, and images in packets |

**m.** FTP is not one of those steps. When does FTP get used instead?

**Answer:** For a file transfer, this didn't send files, it showed them, downloading a file from elsewhere would use FTP.


## Closing 12c — Vocabulary

| Term | Your definition |
|---|---|
| Protocol | A set of rules that are used amungst everyone for things to work well |
| IP address | Basically your online address |
| DNS | Domain Name System |
| Packet | a single piece of information of something online |
| HTTPS | HTTP but secure, sends web pages |
| URL | Uniform Resource Locator |
