<div align="center">

<img src="https://github.com/D-xan/Randomly.online-docs/blob/main/images/randomly%20online%20logo.png?raw=true" width="100" alt="Randomly.online logo" />

# Randomly.online Excel Tools

**7 spreadsheet tools. Your workbook is read in the tab, not uploaded.**

[Open all Excel tools](https://randomly.online/excel-tools/all-excel-tools) &nbsp;|&nbsp; [Main README](README.md) &nbsp;|&nbsp; [randomly.online](https://randomly.online)

</div>

---

## What are the Randomly.online Excel tools?

They are 7 tools that read an .xlsx, .xlsm, .xls or .csv workbook in your browser and write it out as something else: JSON, an HTML table, a Markdown table, SQL INSERT statements or a chart. Two more convert the values Excel stores internally, serial dates and column letters, which is the other half of working with spreadsheet data.

The workbook is parsed in the tab by SheetJS. It is never uploaded, which is the whole reason to use a browser tool for this: the spreadsheets people convert are payroll, customer lists, invoices and pipeline, and those are the files least suited to a stranger's server.

**Last verified: 4 September 2026.** All 7 links below returned HTTP 200 on that date.

---

## Converting a sheet

| Tool | What it produces |
|---|---|
| [Excel to JSON](https://randomly.online/excel-tools/xlsx-to-json-converter) | JSON that parses, with NaN, Infinity and #N/A written as null |
| [Excel to HTML Table](https://randomly.online/excel-tools/xlsx-to-html-table) | A table with thead, tbody, scoped headers and a caption, keeping colspan and rowspan |
| [Excel to Markdown Table](https://randomly.online/excel-tools/xlsx-to-markdown-table) | GitHub Flavored Markdown, with pipes inside cells escaped |
| [Excel to SQL INSERT](https://randomly.online/excel-tools/xlsx-to-sql-generator) | CREATE TABLE and INSERT statements for MySQL, PostgreSQL, SQLite or SQL Server |
| [Excel to Graph](https://randomly.online/excel-tools/excel-to-graph-generator) | Line, bar, scatter, pie and radar charts, exported as PNG or PDF |

The detail those descriptions keep repeating is the point of the category. Spreadsheet exports break on the edge cases: a cell containing a pipe destroys a Markdown table, `#N/A` is not valid JSON, a merged cell has no equivalent in a naive HTML table, and a product code like `00123` becomes the number 123 in almost every converter that touches it. Each tool names how it handles its own version of that problem rather than producing output that looks right and fails later.

---

## Reading Excel's internal values

| Tool | What it does |
|---|---|
| [Excel Serial Date Converter](https://randomly.online/excel-tools/excel-serial-date-converter) | Serial number to date and back, in both the 1900 and 1904 systems |
| [Excel Column Letter to Number Converter](https://randomly.online/excel-tools/excel-column-letter-number-converter) | A=1, Z=26, AA=27, XFD=16384, plus A1 to R1C1 |

Serial dates are the classic source of a silent off-by-something. Excel counts days from an epoch, but which epoch depends on the file: Windows workbooks usually count from 1900 and Mac ones historically from 1904, four years and a day apart. The 1900 system also contains a deliberate bug, a 29 February 1900 that never existed, kept for compatibility with an even older program. When a date column arrives as numbers, this is what you are looking at.

---

## What about formulas and formatting?

These tools read values and structure, not the spreadsheet as an application. A formula's computed result comes through; the formula, conditional formatting, pivot tables, macros and charts drawn in Excel do not, because the output formats have no way to express them.

Large workbooks are limited by your machine rather than an upload cap. Parsing happens in memory, so a very large file needs the memory to hold it, and a sheet with hundreds of thousands of rows will take a moment.

---

## Other categories

[Image](https://randomly.online/image-tools/all-image-tools) &nbsp;|&nbsp; [PDF](https://randomly.online/pdf-tools/all-pdf-tools) &nbsp;|&nbsp; [Text](https://randomly.online/text-tools/all-text-tools) &nbsp;|&nbsp; [Developer](https://randomly.online/dev-tools/all-development-tools) &nbsp;|&nbsp; [Date and time](https://randomly.online/date-time-tools/all-date-time-tools) &nbsp;|&nbsp; [Calculators](https://randomly.online/calculator-tools/all-calculator-tools) &nbsp;|&nbsp; [Converters](https://randomly.online/converter-tools/all-converter-tools) &nbsp;|&nbsp; [SEO](https://randomly.online/seo-tools/all-seo-tools) &nbsp;|&nbsp; [Random generators](https://randomly.online/random-generator-tools/all-random-generators)
