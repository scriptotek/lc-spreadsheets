---
title: Dates as data
teaching: 20
exercises: 0
questions:
  - "How are dates handled by computers?"
objectives:
  - Describe how dates are stored and formatted in spreadsheets.
  - Describe the advantages of alternative date formatting in spreadsheets.
  - Demonstrate best practices for entering dates in spreadsheets.
keypoints:
  - Excel is notoriously bad at handling dates.
  - Dates can be stored more robustly as YEAR, MONTH, DAY or YEAR, DAY-OF-YEAR in separate columns.

authors:
  - Jez Cope
  - Christie Bahlai
  - Aleksandra Pawlik
contributors:
  - Jennifer Bryan
  - Angel Corpuz
  - Alexander Duryee
  - Jeffrey Hollister
  - Daisie Huang
  - Owen Jones
  - Ben Marwick
---

Dates can be written in numerous ways, both with or without letters, punctuation, dashes, slashes, abbreviations, space etc.
Of course, although modern spreadsheet programs are quite clever at understanding different ways of writing dates, not all of these formats will be interpreded correctly.

## Data formats in spreadsheets

Spreadsheet programs have numerous “useful features” which allow them to “handle” dates in a variety of ways.

![Many formats, many ambiguities](../fig/5_excel_dates_1.jpg)

But these ‘features’ often allow ambiguity to creep into your data. Ideally, data should be as unambiguous as possible. 

### Properly formatting dates

It is important to make sure that the dates you enter are understood by the spreadsheet program. A nice approach is to format the column in the date format you want before you start entering dates. In Excel you can do this by selecting the entire column (click on the "letter" header of the column i.e. "A"), then right click and choose "Format cells". Chose "Date", and find the format you want from the list, for example "dd.mm.yyyy". Now, even if you write "14. jul", "14-jul", etc, if Excel understands what you write as a date it will convert it into the format you've chosen. If Excel doesn't understand what you write, it will not format your date and you immediately see that it is poorly written.

### Several columns for dates

Most spreadsheets have dates stored in one column. Ususally spreadsheet programs offer ways of extracting parts from a date as long as it is formatted properly. But, please remember that functions that are valid for a given spreadsheet program (be it LibreOffice, Microsoft Excel, OpenOffice.org, Gnumeric, etc.) are usually guaranteed to be compatible only within the same
family of products. 

Let's try with a simple challenge.

> ## Challenge: pulling month, day and year out of dates ##
> 
> - Go back to the 'training_attendance.xlsx' file and go to the '2016'-sheet.
> - Let’s extract month and year from the dates to new columns. For this we can use the built in Excel functions
> 
> ```
> =MONTH(B3)
> =DAY(B3)
> =YEAR(B3)
> ```
> 
> (Make sure the new column is formatted as a number and not as a date.)
{: .challenge}

Note that you *don't need to do this unless you have to*, for example that you need to export a csv-file that requires dates split, or other requirements such as the ones listed below.

## Advantages of Alternative Date Formatting ##

> ## Note
> 
> Excel is unable to parse dates from before 1899-12-31, and will thus leave these untouched.  If you’re mixing historic data from before and after this date, Excel will translate only the post-1900 dates into its internal format, thus resulting in mixed data.  If you’re working with historic data, be extremely careful with your dates!
> If you make sure to properly format your date column, you will see when Excel fails at interpreting the date yoy write.  
  For example, if you format the date `dd.mm.yyyy` and write 2. jul 1968, Excel will translate this to 02.07.1968, but if you
  try writing `2. jul 1899` it will not be translated and Excel will only see it as plain text.
> Excel also entertains a second date system, the 1904 date system, as the default in Excel for Macintosh. This system will assign a different serial number than the [1900 date system](https://support.microsoft.com/kb/180162). Because of this, [dates must be checked for accuracy when exporting data from Excel](http://datapub.cdlib.org/2014/04/10/abandon-all-hope-ye-who-enter-dates-in-excel/) (look for dates that are ~4 years off). 
{: .callout}

### Storing dates as YEAR, MONTH, DAY {#day}

Here is an example of someone entering dates in a column **without having formatted it for dates first**:

![So, so ambiguous, it's even confusing Excel](../fig/6_excel_dates_2.jpg)

Clearly, the person logging the data intended the numbers to be the day of month instead of year!

Had this person first formatted the date column, these errors would not have been so easy to let slip by.
Storing dates in YEAR, MONTH, DAY is also an alternative, although a bit more cumbersome alternative to writing dates in one nicely formatted column.

### Storing dates as YEAR, DAY-OF-YEAR {#doy}

You can also store dates as year, and day of year (DOY). Why? Because depending on your
question, this might be what's useful to you, and there is practically no possibility for ambiguity creeping in.

Statistical models often incorporate year as a factor, to account for year-to-year variation, and DOY can be used to measure the passage of time within a year. 

So, can you convert all your dates into DOY format? Well, in Excel, here’s a handy dandy guide:

![Kill that ambiguity before it bites you!](../fig/7_excel_dates_3.jpg)

### Storing dates as a single string {#str}

Another alternative could be to convert the date string
into a single string using the `YYYYMMDDhhmmss` format.
For example the date `March 24, 2015 17:25:35` would
become `20150324172535`, where:

```
YYYY:   the full year, i.e. 2015
MM:     the month, i.e. 03
DD:     the day of month, i.e. 24
hh:     hour of day, i.e. 17
mm:     minutes, i.e. 25
ss:     seconds, i.e. 35
```

Such strings will be correctly sorted in ascendng or descending order, and by
knowing the format they can then be correctly processed by the receiving
software.
