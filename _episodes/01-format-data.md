---
title: Formatting data tables in Spreadsheets
teaching: 10
exercises: 15
questions:
  - "How should data tables be formatted in spreadsheets?"
objectives:
  - "Describe best practices for data entry and formatting in spreadsheets."
  - "Apply best practices to arrange variables and observations in a spreadsheet."
keypoints:
  - Use one column for one variable
  - Use one row for one observation
  - Use one cell for one value

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
  - Sebastian Kupny
---


The most common mistake made is treating the program like it is a notebook
- that is, relying on **context**, notes in the margin,
spatial layout of data and fields to convey information.
As humans,
we can (usually) interpret these things,
but computers are dumb,
and unless we explain to the computer what every single thing means
(and that can be hard!)
it will not be able to see how our data fit together.

Using the power of computers,
we can manage and analyze data in much more effective and faster ways,
but to use that power,
we have to set up our data for the computer to be able to understand it
(and computers are very literal).

This is why it’s extremely important to set up **well-formatted tables** from the outset
- before you even start collecting data to analyse.
**Data organization is the foundation of your data-related work.**
It can make it easier or harder to work with your data,
whatever the ultimate goal,
so it's worth thinking about when you're doing your data entry.
You can set things up in a different way in spreadsheets,
but it limits your ability to work with the data in other programs
or have the you-of-6-months-from-now or your collaborator work with the data.


### Keeping track of your analyses

When you're working with spreadsheets, during data clean up or analyses, it's
very easy to end up with a spreadsheet that looks very different from the one
you started with. In order to be able to reproduce your analyses or figure out
what you did when your leadership team ask for a different analysis,
**you must**

- **create a new file or tab with your cleaned or analyzed data.**  
  Do not modify that original dataset, or you will never know where you started!
- **keep track of the steps you took in your clean up or analysis.**  
  We recommend that you keep track of important things you did to the original  
  data in a separate sheet, for example noting if you used some great recipe  
  for tidying up data or if you reorganized the data in an complex or major way.

Put these principles in to practice today during your Exercises. 


### Structuring data in spreadsheets


The cardinal rules of using spreadsheet programs for data:

1. Put each **variable in a column** - ie. a descriptive field like  
   'first name', 'last name, 'birth date', etc.
2. Put each **observation in its own row**, i.e. a student.
3. **Don't combine multiple pieces of information in one cell**.  
   Sometimes it just seems like one thing, but think if that's
   the only way you'll want to be able to use or sort that data.
4. **Leave the raw data raw** - don't mess with it!
5. Export the cleaned data to a **text based format** like CSV. This
   ensures that anyone can use the data, and is the format required by
   most data repositories.


Here is an example of poorly structured table of books in a spreadsheet:

|Book                   |Callcode|Collection|Library               
|-----------------------|--------|----------|-------------------------------------------|
|Brave New World, 1931  |Hux:Bra |SciFiColl |University Library Oslo,Science Library    |
|War of the Worlds, 1898|Wel:War |SCifiColl |University Library Oslo,Informatics library|

The problem is that even though this table is readable for humans, they way the information is placed in the
columns makes it hard for a spreadsheet program to work with it.  
This is a better way of building up a table (notice that the information is exactly the same, only organized a bit differently):

|Title            |Year  |Callcode|Collection|Library                |Location           |
|-----------------|------|--------|----------|-----------------------|-------------------|
|Brave New World  |1931  |Hux:Bra |SciFiColl |University Library Oslo|Science Library    |
|War of the Worlds|1898  |Wel:War |SCifiColl |University Library Oslo|Informatics library|

This allows for more options in working with the data, such as ordering by year and filtering on location (i.e. only showing books located at the informatics library), and so on.


