---
title: Using spreadsheet programs for data wrangling
teaching: 10
exercises: 20
questions:
  - What are good data practices?
objectives:
  - 
keypoints:
  - We will discuss good practices for data entry and formatting
  - We will not discuss analysis or visualisation

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
  - Clare Sloggett
  - Harriet Dashnow
  - Ben Marwick
---


Spreadsheet usage is often useful and neccessary for librarians. We can use them for:

- Viewing data
- Storing data
- Organizing data (categorizing and sorting)
- Visualizing data (charts and graphs)
- Importing and exporting data

---

### Spreadsheet outline

In this lesson, we will look at:

-¤¤FYLL INN HER NÅR OPPLEGGET ER FERDIG



---

### What this lesson will not teach you

- How to do *plotting* i.e. charts and graphs in a spreadsheet
- How to *write code* i.e. formulas and macros in spreadsheet programs
- How to do *statistics* in a spreadsheet

These topics are outside of the scope of this lesson, if you're looking to do this, a good reference is
[Head First Excel by O'Reilly Media](https://www.amazon.com/Head-First-Excel-learners-spreadsheets/dp/0596807694).

---


### Spreadsheet programs

Commands may differ a bit between programs, but the general idea
is the same.

- LibreOffice
- Microsoft Excel
- Gnumeric
- OpenOffice.org

In this lesson, we will assume that you are most likely using Excel as
your primary spreadsheet program - there are others (gnumeric, Calc
from OpenOffice), and their functionality is similar, but Excel is the
package you're most likely to have available on your work computer.
A few of the menu commands we use are excel specific, so bear that in mind if you aim
to use another spreadsheet program. We will indicate these in the lesson 
material as far as we are aware of them.

---

> ## Questions:
>
> Discuss with your neighbour:
>
> - What kind of work do you do in spreadsheets?
>   Try to discuss some practical examples where you structure data (sorting, filtering etc) in your work.
> - Have there been any smart discoveries you have made to save work time with spreadsheets?
> - What do you find frustating and what do want to get done better or faster?
> - Do you find it easy or hard to reverse something you did wrong?
> - Is it easy for you to find good information about your spreadsheet program where you work?
> - Where do you go to find help? Internet, colleague, IT-department, niece? 
{: .challenge}

---

## Some problems with Spreadsheets

Spreadsheets are **good for data entry**, and **viewing and visualizing data** but in reality we **tend to
use spreadsheet programs for much more** than data entry. We use them
to create data tables for publications, to generate summary
statistics, and make figures.

Generating **tables for reports** in a spreadsheet is not optimal -
often, when formatting a data table for publication, we’re reporting
key summary statistics in a way that is **not really meant to be read
as data**, and often involves **special formatting** (merging cells,
creating borders, making it pretty). We advise you to do this sort of
operation within your document editing software.

The latter two applications, **generating statistics and figures**, should 
be used with caution: because of the graphical, drag and drop nature of 
spreadsheet programs, it can be very difficult, if not impossible, to 
replicate your steps (much less retrace anyone else's), particularly if your 
stats or figures require you to do more complex calculations. Furthermore, 
in doing calculations in a spreadsheet, it’s easy to accidentally apply a 
slightly different formula to multiple adjacent cells. When using a 
command-line based statistics program like R or SAS, it’s practically 
impossible to accidentally apply a calculation to one observation in your 
dataset but not another unless you’re doing it on purpose. 

### Using Spreadsheets for Data Entry and Cleaning

**HOWEVER**, there are circumstances where you might want to use a
spreadsheet program to produce “quick and dirty” calculations or
figures, and some of these features can be used in **data cleaning**,
prior to importation into a statistical analysis program. We will show
you how to use some features of spreadsheet programs to check your
data quality along the way and produce preliminary summary statistics.


In this lesson, we're going to talk about:

1. [Formatting data tables in spreadsheets](../01-format-data)
2. [Formatting problems](../02-common-mistakes)
3. [Dates as data](../03-dates-as-data)
4. [Basic quality control and data manipulation in spreadsheets](../04-quality-control)
5. [Exporting data from spreadsheets](../05-exporting-data)
6. [Data export formats caveats](../06-data-formats-caveats)
