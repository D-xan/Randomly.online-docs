<div align="center">

<img src="https://github.com/D-xan/Randomly.online-docs/blob/main/images/randomly%20online%20logo.png?raw=true" width="100" alt="Randomly.online logo" />

# Randomly.online Random Generators

**25 generators and pickers. Fair draws from a cryptographic random source.**

[Open all random generators](https://randomly.online/random-generator-tools/all-random-generators) &nbsp;|&nbsp; [Main README](README.md) &nbsp;|&nbsp; [randomly.online](https://randomly.online)

</div>

---

## What are the Randomly.online random generators?

They are 25 tools for picking, drawing, shuffling and generating: a winner from a list, teams from a class, dice for a game, a PIN, a name, a colour, a Secret Santa draw. This is the category the site is named after.

They run in your browser, which for this category buys two things. The list of names you paste into a picker is not sent anywhere, and the draw itself is not something a server decided for you. The result comes from your own machine, from the browser's cryptographic random source, and you can watch it happen offline with the network disconnected.

**Last verified: 4 September 2026.** All 25 links below returned HTTP 200 on that date.

---

## Deciding, drawing and picking

| Tool | What it does |
|---|---|
| [Coin Flip](https://randomly.online/random-generator-tools/coin-flip) | Heads or tails, once or many times with a running tally |
| [Yes No Spinner](https://randomly.online/random-generator-tools/yes-no-spinner) | A yes/no wheel, with an optional maybe |
| [Dice Roller](https://randomly.online/random-generator-tools/dice-roller) | d6 and the RPG set, several dice at once, with modifiers |
| [Wheel of Names](https://randomly.online/random-generator-tools/wheel-of-names) | A spinning picker wheel from your own entries |
| [Random Name Picker](https://randomly.online/random-generator-tools/random-name-picker) | A winner from a pasted list, removing each one for sequential draws |
| [List Randomizer](https://randomly.online/random-generator-tools/list-randomizer) | Shuffle a list, or pull a random subset |
| [Random Team Generator](https://randomly.online/random-generator-tools/random-team-generator) | Split names into balanced teams by count or size |
| [Secret Santa Generator](https://randomly.online/random-generator-tools/secret-santa-generator) | Pairings with exclusions, revealed one at a time or in secret |
| [Bingo Number Generator](https://randomly.online/random-generator-tools/bingo-number-generator) | A 75 or 90 ball caller that draws without repeats |
| [Lottery Number Generator](https://randomly.online/random-generator-tools/lottery-number-generator) | Powerball, Mega Millions, EuroMillions, Lotto or a custom game |

Secret Santa is the one that genuinely needs to run locally. The whole point is that the organiser does not learn the pairings, and a version that posts the list of names to a server has quietly given someone else the answer. Here the draw happens on the organiser's machine and the reveal happens per person.

---

## Numbers, letters and strings

| Tool | What it does |
|---|---|
| [Random Number](https://randomly.online/random-generator-tools/random-number) | Any range, any count, unique or repeatable |
| [Random Letter Generator](https://randomly.online/random-generator-tools/random-letter-generator) | A to Z, with case, vowel and consonant filters |
| [Random String Generator](https://randomly.online/random-generator-tools/random-string-generator) | Tokens over a character set you define, with batch export |
| [Random PIN Generator](https://randomly.online/random-generator-tools/random-pin-generator) | 4, 6 or any length, with weak patterns avoided |
| [Random Password Generator](https://randomly.online/random-generator-tools/random-password-generator) | Full character control with a live strength meter |
| [Random Date Generator](https://randomly.online/random-generator-tools/random-date-generator) | Dates in a range, formatted, for test data |

---

## Names, words and colours

| Tool | What it does |
|---|---|
| [Name Generator](https://randomly.online/random-generator-tools/name-generator) | Modern, fantasy, brand and pet names |
| [Random Username Generator](https://randomly.online/random-generator-tools/random-username-generator) | Handles by style, with patterns and numbers |
| [Random Word Generator](https://randomly.online/random-generator-tools/random-word-generator) | Filtered by part of speech and length |
| [Random Quote Generator](https://randomly.online/random-generator-tools/random-quote-generator) | A quote by category, with attribution |
| [Random Emoji Generator](https://randomly.online/random-generator-tools/random-emoji) | By category, copied with one click |
| [Random Country Name](https://randomly.online/random-generator-tools/random-country-name) | A country with its capital and flag, filtered by region |
| [Random Color Picker](https://randomly.online/random-generator-tools/random-color-picker) | Colours and palettes with HEX and RGB values |

---

## Party and icebreakers

| Tool | What it does |
|---|---|
| [Would You Rather Generator](https://randomly.online/random-generator-tools/would-you-rather-generator) | Questions by category for groups and long drives |
| [Truth or Dare Generator](https://randomly.online/random-generator-tools/truth-or-dare-generator) | Prompts by mode and intensity |

---

## Is it actually random, or just random enough?

It is drawn from `crypto.getRandomValues`, the browser's cryptographically secure random source, rather than `Math.random`. That distinction matters for a PIN or a token, and it costs nothing for a coin flip, so the tools use the good source throughout.

The subtler part is turning a random 32-bit number into a number in your range. Taking the remainder is the obvious way and it is slightly unfair: if the range does not divide evenly into 2^32, the low values come up marginally more often. The generators here discard the values in that uneven tail and draw again, so every outcome in the range is equally likely. Shuffles and multi-draws use the same source, taking each position from the remaining pool rather than sorting by a random key, which is the version of a shuffle that does not favour the original order.

Practical consequences: a draw cannot be predicted or reproduced, there is no seed to set, and there is no server that could have decided the result before you clicked.

---

## Other categories

[Image](https://randomly.online/image-tools/all-image-tools) &nbsp;|&nbsp; [PDF](https://randomly.online/pdf-tools/all-pdf-tools) &nbsp;|&nbsp; [Text](https://randomly.online/text-tools/all-text-tools) &nbsp;|&nbsp; [Developer](https://randomly.online/dev-tools/all-development-tools) &nbsp;|&nbsp; [Date and time](https://randomly.online/date-time-tools/all-date-time-tools) &nbsp;|&nbsp; [Calculators](https://randomly.online/calculator-tools/all-calculator-tools) &nbsp;|&nbsp; [Converters](https://randomly.online/converter-tools/all-converter-tools) &nbsp;|&nbsp; [Excel](https://randomly.online/excel-tools/all-excel-tools) &nbsp;|&nbsp; [SEO](https://randomly.online/seo-tools/all-seo-tools)
