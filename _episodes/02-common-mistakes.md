---
title: Formatting problems
teaching: 5
exercises: 0
questions:
  - What common mistakes are made when formatting spreadsheets?
objectives:
  - Recognize and resolve common spreadsheet formatting problems.
keypoints:
  - "Don't use multiple tables in one sheet"
  - "Don't use multiple tabs in a file"
  - Fill in zero when you mean zero
  - Use a blank cell to indicate a null value
  - "Don't use formatting to convey information or make the data look pretty"
  - "Don't put units or comments in cells"
  - "Don't combine several values in one cell"
  - "Take care over column names"
  - "Avoid including special characters in your data file"
  - "Put metadata (units, legends etc.) in a separate file"

authors:
  - Jez Cope
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


## Common Spreadsheet Errors

- [Multiple tables](#tables)
- [Multiple sheets](#shets)
- [Header pollution](#freezing)
- [Not filling in zeros](#zeros)
- [Using bad null values](#null)
- [Using formatting to convey information](#formatting)
- [Using formatting to make the data sheet look pretty](#formatting_pretty)
- [Placing comments or units in cells](#units)
- [More than one piece of information in a cell](#info)
- [Field name problems](#field_name)
- [Special characters in data](#special)
- [Inclusion of metadata in data table](#metadata)
- [Date formatting](03-dates-as-data.html)

---

## Multiple tables {#tables}

A common strategy is creating multiple data tables within one
spreadsheet. This is examplified in the figure below:

![multiple tabs](../fig/2_datasheet_example.jpg)

Although it is often useful to have many tables on the same spreadsheet by making the tables more accessible and simpler to visually compare, mentally group them, etc., it leads to difficulties in exporting to other formats such as csv. You will have to put each table into its own sheet (and as a seperate issue clean up the data) and export each sheet into its own csv-file. The example above depicts a typical visualization of data for reports etc, and isn't very practical to be doing analyses on.

## Multiple sheets {#sheets}

It is not easy to categorically state when it is beneficial to keep the data in one sheet, and when to split the data into separate sheets. A general rule could be to **put data that with the same columns** in the same sheet, and **only create a new sheet if the new data has a different set of columns**, i.e. **structure**. For example, if you do the same survey on library user behavior every year, it is better to keep all the data in the same sheet and not make a new one for each year: This makes it easier to compare data across years.  
But what happens if you add one question (say for age) which gives you an extra column? Should you then make a new sheet for the new data? Well, no. Just add the new column to existing sheet. Excel (and other programs) have ways of dealing with **missing data**, and you get the benefit of being able to compare all the rest of the old data with the new in the same sheet.  
But what if you add two new questions, and maybe remove one, what then? Again, it is difficult to give a categorical answer, but if you see that the new data is **structurally too different**, i.e. have to many differences, then you should place it in **a new sheet**.

## Header pollution {#freeze}
Often the title headers of columns can get confused into the data itself analysis (for example sorting or summation). Sometimes you can even get an excel file where the headers titles routinely show up every 30 rows or so to remind you of what column is what.
This is not a good solution for getting an overview of the data because it will cause all kinds of errors when sorting, counting etc.
The header row should only be one row (the topmost) and most spreadsheet programs have good methods for dealing with them.
If you want to keep an overview of the column names in large datasets, you can freese the column headers, so that they are visible at all times.  

Here is a recipe:

[Documentation on how to freeze column headers](https://support.office.com/en-ca/article/Freeze-column-headings-for-easy-scrolling-57ccce0c-cf85-4725-9579-c5d13106ca6a)


## Not filling in zeroes {#zeros}

It might be that when you're measuring something, it's
usually a zero, say the number of times an elephant
is observed in the object or the survey. Why bother
writing in the number zero in that column, when it's mostly zeros?

However, there's a difference between a zero and a blank cell in a spreadsheet. To the computer, a zero is actually data. You measured or counted it. A blank cell means that it wasn't measured and the computer will interpret it as a null value.

The spreadsheets or statistical programs will likely mis-interpret blank cells that are meant to be zero. This is equivalent to leaving out data. Zero observations are real data! Leaving zero data blank is not good in a written lab notebook, but NEVER okay when you move your data into a digital format.


## Using bad null values {#null}

**Example**: using -999 or other numerical values (or zero).

**Solution**: Many statistical programs will not recognize that numeric values of null are indeed null. It will depend on the final application of your data and how you intend to analyse it, but it is essential to use a clearly defined and CONSISTENT null indicator. Blanks (most applications) and NA (for R) are good choices.

From White et al, 2013, [Nine simple ways to make it easier to (re)use your data.](https://ojs.library.queensu.ca/index.php/IEE/article/view/4608) Ideas in Ecology and Evolution:

![White et al.](../fig/3_white_table_1.jpg)


## Using formatting to convey information  {#formatting}

**Example**: highlighting cells, rows or columns that should be excluded from an analysis, leaving blank rows to indicate separations in data.

![formatting](../fig/formatting.png)

**Solution**: create a new field to encode which data should be excluded.

![good formatting](../fig/good_formatting.png)


## Using formatting to make the data sheet look pretty {#formatting_pretty}

**Example**: merging cells.

**Solution**: If you’re not careful, formatting a worksheet to be more aesthetically pleasing can compromise your computer’s ability to see associations in the data. Merged cells are an absolute formatting NO-NO if you want to make your data readable by statistics software. Consider restructuring your data in such a way that you will not need to merge cells to organize your data.


## Placing comments or units in cells {#units}

**Example**: Your data was collected, in part, by a summer student who you later found out was mis-identifying some of your species, some of the time. You want a way to note these data are suspect.

**Solution**: Most statistical programs can’t see Excel’s comments, and would be confused by comments placed within your data cells. As described above for formatting, create another field if you need to add notes to cells. Similarly, don’t include units in cells: ideally, all the measurements you place in one column should be in the same unit, but if for some reason they aren’t, create another field and specify the units the cell is in.


## More than one piece of information in a cell {#info}

**Example**: You find one male, and one female of the same species. You enter this as 1M, 1F.

**Solution**: Never include more than one piece of information in a cell. If you need both these measurements, design your data sheet to include this information.


## Field name problems {#field_name}
Choose descriptive field names, but be careful not to include: spaces, numbers, or special characters of any kind. Spaces can be misinterpreted by parsers that use whitespace as delimiters and some programs don’t like field names that are text strings that start with numbers.
Underscores (`_`) are a good alternative to spaces and consider writing names in camel-case to improve readability. Remember that abbreviations that make sense at the moment may not be so obvious in 6 months but don't overdo it with names that are excessively long. Including the units in the field names avoids confusion and enables others to readily interpret your fields.

**Examples**  

| Good Name          | Good Alternative   | Avoid                |
|--------------------+--------------------+----------------------|
| Max\_temp\_C       | MaxTemp            | Maximum Temp (°C)    |
| Precipitation\_mm  | Precipitation      | precmm               |
| Mean\_year\_growth | MeanYearGrowth     | Mean growth/year	 |
| sex                | sex                | M/F                  |
| weight             | weight             | w.                   |
| cell\_type         | CellType           | Cell Type            |
| Observation\_01    | first\_observation | 1st Obs              |


## Special characters in data {#special}

**Example**: You treat Excel as a word processor when writing notes, even copying data directly from Word or other applications.

**Solution**: This is a common strategy. For example, when writing longer text in a cell, people often include line breaks, em-dashes, et al in their spreadsheet.  Worse yet, when copying data in from applications such as Word, formatting and fancy non-standard characters (such as left- and right-aligned quotation marks) are included.  When exporting this data into a coding/statistical environment or into a relational database, dangerous things may occur, such as lines being cut in half and encoding errors being thrown.

General best practice is to avoid adding characters such as newlines, tabs, and vertical tabs.  In other words, treat a text cell as if it were a simple web form that can only contain text and spaces.


## Inclusion of metadata in data table {#metadata}

**Example**: You add a legend at the top or bottom of your data table explaining column meaning, units, exceptions, etc.

**Solution**: While recording data about your data ("metadata") is essential, this information should not be contained in the data file itself. Unlike a table in a paper or a supplemental file, metadata (in the form of legends) should not be included in a data file since this information is not data, and including it can disrupt how computer programs interpret your data file. Rather, metadata should be stored as a separate file in the same directory as your data file, preferably in plain text format with a name that clearly associates it with your data file. Because metadata files are free text format, they also allow you to encode comments, units, information about how null values are encoded, etc. that are important to document but can disrupt the formatting of your data file.

