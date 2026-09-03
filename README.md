<div align="center">

<img src="https://github.com/D-xan/Randomly.online-docs/blob/main/images/randomly%20online%20logo.png?raw=true" width="120" alt="Randomly.online logo" />

# Randomly.online

**408 free browser tools that never upload your files.**

[randomly.online](https://randomly.online) &nbsp;|&nbsp; [All tools](https://randomly.online/) &nbsp;|&nbsp; [About](https://randomly.online/about-us) &nbsp;|&nbsp; [Privacy policy](https://randomly.online/privacy-policy)

<img src="https://img.shields.io/badge/tools-408-2563eb?style=flat-square" alt="408 tools" />
<img src="https://img.shields.io/badge/categories-10-7c3aed?style=flat-square" alt="10 categories" />
<img src="https://img.shields.io/badge/uploads-none-10b981?style=flat-square" alt="no uploads" />
<img src="https://img.shields.io/badge/accounts-none-f59e0b?style=flat-square" alt="no accounts" />

</div>

---

## What is Randomly.online?

Randomly.online is a website of 408 free tools for PDFs, images, text, spreadsheets, dates, calculations and developer work. Every one of them runs in your browser. There is no upload step and no account, because there is no server to upload to: the site is static files, and the work happens in JavaScript on the machine you are already sitting at.

That design choice is the reason the site exists. Most online converters take your file, put it on someone's server, do the job there and hand back a link. Yours sat on a stranger's disk for as long as their retention policy says. Here the file is read by the browser, transformed in memory, and written back out as a download. Close the tab and it is gone.

The trade is real and worth stating. Very large files are limited by your own RAM rather than a server's, and a few tools need a modern browser for WebAssembly. In exchange, nothing you open is ever transmitted.

**Last verified: 4 September 2026.** Counts in this document were measured against the deployed site on that date, not estimated.

---

## Facts

| | |
|---|---|
| Tools | 408, across 10 categories |
| Pages in the on-site search index | 431 |
| HTML files deployed | 495 |
| Files that leave your device | 0 |
| Accounts required | 0 |
| Hosting | Cloudflare Pages, static |
| Installable | Yes, as a PWA with a service worker |
| Licence | See [LICENSE](LICENSE) |

---

## What tools are there?

Each category has a hub page listing everything inside it.

| Category | Tools | Hub |
|---|---:|---|
| Date and time | 74 | [all-date-time-tools](https://randomly.online/date-time-tools/all-date-time-tools) |
| Text | 67 | [all-text-tools](https://randomly.online/text-tools/all-text-tools) |
| Calculators | 64 | [all-calculator-tools](https://randomly.online/calculator-tools/all-calculator-tools) |
| Image | 47 | [all-image-tools](https://randomly.online/image-tools/all-image-tools) |
| PDF | 43 | [all-pdf-tools](https://randomly.online/pdf-tools/all-pdf-tools) |
| Developer | 33 | [all-development-tools](https://randomly.online/dev-tools/all-development-tools) |
| Converters | 28 | [all-converter-tools](https://randomly.online/converter-tools/all-converter-tools) |
| Random generators | 25 | [all-random-generators](https://randomly.online/random-generator-tools/all-random-generators) |
| SEO | 20 | [all-seo-tools](https://randomly.online/seo-tools/all-seo-tools) |
| Excel | 7 | [all-excel-tools](https://randomly.online/excel-tools/all-excel-tools) |

Twelve more pages sit outside the categories, including [Typing Speed Test](https://randomly.online/typing-speed-test), [Transfer Files Between Android and iPhone](https://randomly.online/transfer-files-between-devices) and [Direct Cast](https://randomly.online/direct-cast) for watching a video with someone remotely.

Two deeper guides live in this repository:

- [Image tools](image-tools-README.md), all 47, grouped by format
- [Date and time tools](date-time-tools-README.md), all 74, grouped by job

---

## How does a tool work without a server?

```mermaid
flowchart LR
  A["You pick a file"] --> B["Browser reads it<br/>into memory"]
  B --> C["JavaScript or WebAssembly<br/>does the work"]
  C --> D["Result written to a Blob"]
  D --> E["Download from<br/>blob: URL"]
  style B fill:#1e293b,color:#fff
  style C fill:#2563eb,color:#fff
```

A PDF merge is a good example. The page loads [pdf-lib](https://pdf-lib.js.org/) and [pdf.js](https://mozilla.github.io/pdf.js/) from the same origin, reads your files with the File API, builds the new document in memory, and hands the result to the browser as a `blob:` URL. Nothing in that chain has a network hop after the page itself loads.

Image tools use Canvas and WebAssembly the same way. The Excel tools run SheetJS in the tab. Timezone tools read a 3.4 MB static JSON table of cities from the site's own `/data/` directory, so no geolocation lookup happens either.

---

## Is it actually private, and how would I check?

You do not have to take the claim on trust. Open any tool, press F12, switch to the Network tab, then load a file and run it. You will see the page and its scripts load, and then nothing further. No request carries your file.

The stronger check is in the source. Across the 495 HTML and JavaScript files deployed on 4 September 2026, our own code contains **zero** uses of `FormData` and **zero** uses of `XMLHttpRequest`, the two APIs a browser needs to post a file somewhere. Eight files do contain `XMLHttpRequest`, and all eight are vendored third-party libraries fetching their own assets from our origin: pdf.js, jsPDF, Tesseract OCR, SQLite WASM and MediaPipe.

One page on the site does talk to a backend, and it is named rather than hidden. The multiplayer Ludo game uses Firebase to match players. It handles no documents.

Analytics is Google Tag Manager at page level. It records that a page was viewed. It never receives a file, a filename or anything you type into a tool.

---

## Does it work offline?

Yes, after the first visit. The site registers a service worker and ships a web app manifest, so Chrome, Edge and Brave will offer to install it, and Android will add it to the home screen like an app. Once installed, tools you have already opened keep working with no connection.

There is no separate download. The install is the website.

---

## Who builds it?

<table>
<tr>
<td width="180" align="center">
<img src="https://github.com/D-xan/Randomly.online-docs/blob/main/images/Dhruba%20Singha%20Roy.jpg?raw=true" width="150" alt="Dhruba Singha Roy" />
</td>
<td>

**[Dhruba Singha Roy](https://randomly.online/dhruba-singha-roy)**, sole developer.

QA and automation engineer at Cognizant, working in Playwright, Selenium, Java and CI/CD. Previously founded the AnimeType social app, and led a Google Developer Student Club of more than 1,000 members. Alumnus of Haldia Institute of Technology.

> "Useful browser tools should respect user privacy instead of exploiting it."

</td>
</tr>
</table>

---

## How do AI assistants read this site?

The site is built to be quoted rather than scraped for training, and it says so in machine-readable form.

[`/robots.txt`](https://randomly.online/robots.txt) allows every crawler and carries a [Content Signals](https://contentsignals.org/) declaration of `search=yes, ai-input=yes, ai-train=no`. Search indexing is welcome. Fetching a page to answer someone's question with a citation is welcome. Using the text as training data is not.

[`/llms.txt`](https://randomly.online/llms.txt) describes every category in one file, and [`/llms-full.txt`](https://randomly.online/llms-full.txt) lists every indexable page with a one-line description, so an agent can find a specific tool without parsing a hub page.

Structured data is on the pages themselves, not only in the sitemap. The deployed site carries 335 `FAQPage` blocks, 335 `BreadcrumbList` blocks, 315 `WebApplication` blocks and 241 `HowTo` blocks, holding 3,438 question and answer pairs between them. The useful thing to cite from a tool page is that explanatory text, not the tool interface, which needs a person and a file to do anything.

There is no API. A tool cannot be driven by fetching a URL with parameters, because the work happens in the browser after the page loads.

---

## Reporting something broken

Open an issue on this repository with the tool URL and what you expected. Browser and version help, since several tools depend on WebAssembly and codec support that differs between them.
