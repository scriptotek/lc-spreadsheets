---
title: Importing and exporting data
teaching: 15
exercises: 15
questions:
  - What problems are there with Excel files?
  - How can these problems be solved?
objectives:
  - Store spreadsheet data in universal file formats.
  - Export data from a spreadsheet to a .csv file.
  - Import data from .csv files.
keypoints:
  - Use the CSV file format for data storage and exchange

authors:
  # - Jez Cope
  - Christie Bahlai
  - Aleksandra Pawlik
contributors:
  - Jennifer Bryan
  - Alexander Duryee
  - Jeffrey Hollister
  - Daisie Huang
  - Owen Jones
  - Ben Marwick
---

## The Excel file format

By default, Excel, stores spreadsheet data in the Excel file format
(`*.xls` or `*.xlsx` - depending on the Excel version).

- The format can contain not only data, but also formulas, visualizations, images, comments,
  formatting (color, text styles, etc.), even scripts (a common source of viruses in the past)
  and what have you. This is worth spelling out, since it's what makes *spreadsheets* different
  from *data tables*.

- The format is *proprietary* and its development is linked to a specific piece of
  (non-free) software (Excel).
  - This is less of an issue with the Excel format than many other proprietary
    formats because the ubiquity of Excel has led to good third-party support
    for the format.
    There's no shortage of *free* and *open* software that supports the format.
    Not all implementations support all features of the format though.

- The format changes over time together with the software itself.
  Different versions of Excel may handle data differently, leading to inconsistencies.

- It's a *very complex* file format. This is an issue that is often overlooked,
  but for long-term storage it's imporant to keep in mind.
  The more flexible and complex a file format is, the more things can go wrong,
  and thus the greater the chance that something actually does go wrong.
  - The *complexitity* issue is not only an issue with the Excel format, but also the
    Open Document Format (ODF).
  - More complexity also means that more processing power and memory is needed to work
    with the files. Not something you have to worry about on your everyday spreadsheet,
    but for large datasets or automated data processing, it can be a reason to choose
    an alternative.

<!-- - Finally, more **journals and grant agencies** are requiring you -->
<!--   to deposit your data in a data repository, and most of them **don't -->
<!--   accept Excel format**. It needs to be in one of the formats -->
<!--   discussed here. -->

As an example, do you remember how we talked about how Excel stores **dates** earlier? Turns out there are **multiple defaults for different versions of the software**. And you can switch between them all willy-nilly. So, say you’re compiling Excel-stored data from multiple sources. There’s dates in each file- Excel interprets them as their own internally consistent serial numbers. When you combine the data, Excel will take the serial number from the place you’re importing it from, and interpret it using the rule set for the version of Excel you’re using. Essentially, you could be adding a huge error to your data, and it wouldn’t necessarily be flagged by any data cleaning methods if your ranges overlap.

## The CSV format for data tables

When **archiving**, **publishing** or **sharing** data, it's a good idea to consider
an alterative format – one which is **universal**, **open** and **static**
(no formulas, scripts, etc.) format.

The de facto standard format in these cases would be the [CSV format](https://en.wikipedia.org/wiki/Comma-separated_values) (*comma-separated values*).
- CSV files are *plain text files*. The cells are separated by a delimiting character (commas, tabs or similar)
  and the rows by linebreaks.
  If a part of the file gets corrupted, the rest of the file is still fine.
- They can be opened using just about any software that works with tabular data.
  You can even open them in a **text editor** like Notepad for inspection and simple editing.  
- Data in a CSV file can be **easily imported** into other formats and environments, so it's a good format to work with for maximum portability and endurance.

When it comes to data exchange and long-term storage, simplicity is king and CSV is perfect!
But CSV files can only contain data tables (one per file), nothing of the other stuff you
can have in a spreadsheet like formulas, merged cells, formatting, comments, figures, etc.

### Options for CSV files

A CSV file comes with some options that you need to be aware of when saving data as CSV or importing data from CSV.
The most important are:

* **Separator**: The table cells in a CSV file can in principle be separated by any type of symbol as
  long as the file is consistent. The most common is comma (therby the name), but tab is also very
  common, and you might also come across semicolon. Files separated by tabs sometimes use the file ending
  `.tsv` rather than `.csv`, but this is by no means standardized.

* **Escape character** or **text qualifier**: If there's an actual comma symbol (or whatever separator token you have)
  within a cell, that value must be "escaped" in some way so it's not interpreted as a separator.
  Again, there's different ways to do this.

* **Character encoding**: As with other text files, a CSV file has a character encoding that determines how characters are stored.
  The de facto standard today is to use Unicode (UTF-8), which supports all the alphabets of the world
  and lots of other characters like technical symbols and emojis.
  Unfortunately, Excel still exports CSV files using legacy character encodings.
  LibreOffice is better in this case, as it provides you with an option of what character encoding to use.

### Saving a table in Excel as CSV

All spreadsheet programs can save to CSV, but they differ a bit in how well they do it.

1. From the top menu select 'File' and 'Save as'.
2. In the 'Format' field, from the list, select 'Comma Separated Values' (`*.csv`).
3. Double check the file name and the location where you want to save it and hit 'Save'.

![Saving an Excel file to CSV](../fig/excel-to-csv.png)

Warning: Excel does not give you the option to choose character encoding, but instead selects
a legacy character encoding based on which language you'r system is using.
Before sharing a CSV file from Excel you should convert it to Unicode (UTF-8) – this can be
done in a text editor like Notepad++.
Or export CSV from LibreOffice or Google Sheets instead.
LibreOffice provides you with all the options you need, while Google Sheets just use sensible defaults.

## Importing CSV files

Some software are quite smart when it comes to detecting the above-mentioned CSV options upon import.
Excel is not, but it provides you with an import wizard where you can select the settings yourself
by trying and failing. If you see question marks like this it means the file is encoded using
a different encoding than the one you have selected:

![Wrong encoding during import](../fig/import-encoding-problem.png)

In this case, the file was encoded as a legacy encoding called "Windows (ANSI)" or 
"[CP-1252](https://en.wikipedia.org/wiki/Windows-1252)", which is limited to the Latin alphabet
with some extensions.

In the next step of the import, you have to select delimiter and text qualifier.
This is easier since there are fewer options to choose from, and Excel will preview the result live.
For the text qualifier setting, the default value is also usually the correct one.

![Correct delimiter during import](../fig/import-csv-delimiter.png)

> ## Challenge: Importing a CSV file ##
> 
> 1. Download the CSV file with a list of all countries from DataHub: https://datahub.io/core/country-list (look for "csv" under "Download")
> 2. Import the file into Excel.
> 
{: .challenge}


## A final note on cross-platform operability
(or, how typewriters are ruining your work)

By default, most coding and statistical environments expect UNIX-style line endings (`\n`) as representing line breaks.  However, Windows uses an alternate line ending signifier (`\r\n`) by default for legacy compatibility with Teletype-based systems.  As such, when exporting to CSV using Excel, your data will look like this:

>data1,data2\r\n1,2\r\n4,5\r\n…

which, upon passing into most environments (which split on `\n`), will parse as:

>data1<br>
>data2\r<br>
>1<br>
>2\r<br>
>...

thus causing terrible things to happen to your data.  For example, `2\r` is not a valid integer, and thus will throw an error (if you’re lucky) when you attempt to operate on it in R or Python.  Note that this happens on Excel for OSX as well as Windows, due to legacy Windows compatibility.

There are a handful of solutions for enforcing uniform UNIX-style line endings on your exported CSVs:

1. When exporting from Excel, save as a “Windows comma separated (.csv)” file
2. If you store your data file under version control (which you should be doing!) using Git, edit the `.git/config` file in your repository to automatically translate `\r\n` line endings into `\n`.
   Add the follwing to the file ([see the detailed tutorial](http://nicercode.github.io/blog/2013-04-30-excel-and-line-endings)):

   ```
   [filter "cr"]
   clean = LC_CTYPE=C awk '{printf(\"%s\\n\", $0)}' | LC_CTYPE=C tr '\\r' '\\n'
   smudge = tr '\\n' '\\r'` 
   ```
   
   and then create a file `.gitattributes` that contains the line:
 
   ```
   *.csv filter=cr
   ```
	
3. Use [dos2unix](http://dos2unix.sourceforge.net/) (available on OSX, *nix, and Cygwin) on local files to standardize line endings.

#### A note on Python and `xls`

There are Python packages that can read `xls` files (as well as
Google spreadsheets). It is even possible to access different
worksheets in the `xls` documents.

**But**

- this equates to replacing a (simple but manual) export to `csv` with
  additional complexity/dependencies in the data analysis Python code
- **data formatting best practice STILL apply**
- Is there really a good reason why `csv` (or similar) is not adequate?
