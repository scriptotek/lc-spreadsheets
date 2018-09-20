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
   'first name', 'last name, 'callcode', 'collection', etc.
2. Put each **observation in its own row**, i.e.  
    a book, a student, a journal, etc.
3. **Don't combine multiple pieces of information in one cell**.  
   Sometimes it just seems like one thing, but think if that's
   the only way you'll want to be able to use or sort that data.
4. **Leave the raw data raw** - don't mess with it!
5. Export the cleaned data to a **text based format** like CSV. This
   ensures that anyone can use the data, and is the format required by
   most data repositories.

|Last Name|FirstName|Position  ||Title          |Callcode|Collection|
|---------|---------|----------||---------------|--------|----------|
|Olsen    |Mark     |Undergrad ||Brave New World|45a/45  |SciFiColl |
|Jamestown|Donna    |Ph        ||Utopia         |45a/46  |SCifiColl |

For instance, we have data from a survey of small mammals in a desert
ecosystem. Different people have gone to the field and entered data in
to a spreadsheet. They keep track of things like species, plot,
weight, sex and date collected.

If they were to keep track of the data like this:

![multiple-info example](../fig/multiple-info.png)

the problem is that species and sex are in the same field. So, if they wanted to 
look at all of one species or look at different weight distributions by sex, 
it would be hard to set up the data to do this. If instead we put sex and species 
in different columns, you can see that it would be much easier. 

### Columns for variables and rows for observations

The rule of thumb, when setting up a datasheet, is **columns =
variables**, **rows = observations**, **cells = data** (values).

So, instead we should have:

![single-info example](../fig/single-info.png)

> ## Exercise
>
> We're going to take a messy version of some library training data and clean it up
>
> 1. First [download the data](../data/training_attendance.xlsx)
> 2. Open up the data in a spreadsheet program
> 1. You can see that there are three tabs. Various people have recorded
  training attendance statistics over 2016 and 2017, and they have
  kept track of the data in their own way. Now you're being asked to
  evaluate the training programme and you want to be able to start
  doing statistics with the data.
> 1. With the person next to you, work on the messy data so that a
  computer will be able to understand it. Clean up the 2016 and 2017
  tabs, and put them all together in one spreadsheet.
> 1. After you go through this exercise, we'll discuss as a group what you think was wrong
with this data and how you fixed it. 
{: .challenge}


> ## Important ##
>
> Do not forget of our first piece of advice:
> **create a new file (or tab)** for the cleaned data, **never
> modify the original (raw) data**.
{: .callout}


An excellent reference, in particular with regard to R scripting is

> Hadley Wickham, *Tidy Data*, Vol. 59, Issue 10, Sep 2014, Journal of
> Statistical Software. [http://www.jstatsoft.org/v59/i10](http://www.jstatsoft.org/v59/i10).

<!-- *Instructors see notes in 'instructors_notes.md' on this exercise.* -->
