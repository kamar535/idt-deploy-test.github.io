---
title: Introduction
weight: 20
---

On this page you find a short introduction to the most important parts of how to
work with spreadsheets in Microsoft Excel

## Cells

In all spreadsheets software, data is kept in a grid. Each box in the grid is
called a **cell**. The grid is divided into columns (identified by by letters)
and rows (identified by numbers).

### Rows

The rows are numbered. The column number indicates the vertical position of the
row. Row 1 is the top row. In the below example, all the cells in
row three has been selected.

{{< figure src="/images/excel/row-3.png" title="Row 3 in the grid" >}}

### Columns

The columns are enumerated using letters. The column letter indicates the
horizontal position of the column. Column A is the left most column. 
In the below example, all cells in column C has been selected.

{{< figure src="/images/excel/column-c.png" title="Column C in the grid" >}}

## Cell references

To refer to a specific cell in the grid, a combination of the column letter(s)
and row number is used. In the below example, `C3` refers to the cell in column
`C` and row `3` in the grid. 

{{< figure src="/images/excel/cell-position-example.png"
    title="In the grid, cell C3 is located in column C, row 3" >}}

## Rectangular ranges

A rectangle of connected cells is called a (rectangular) range. A range is
identified by the top left cell and the bottom right cell. The two cell
references used to identify a range are separated by a `:` (colon).
In the below example, the range `A1:C3` has been selected.

{{< figure src="/images/excel/range-example.png" title="The range A1:C3" >}}

## Get started

Microsoft excel should be installed on the computers in the computer rooms at
the university. You may also use your free [Microsoft Live][live] account to run
excel in your web browser. Note that the online version of Excel does not
support trendlines in graphs.

[live]: https://office.live.com/start/Excel.aspx

When you start Exel, choose **blank page** to start a new document. You should
now see something similar to this. 

{{< figure src="/images/excel/start.png" title="A new Excel document" >}}

You can now start entering numbers and text in the cells. Go to the **File** tab
to save the document. 


## Entering numbers

Excel has many smart functions that helps you entering numbers efficiently. You
can test this by typing some numbers (pressing ***Enter*** takes you to the next row),
highlighting them and clicking and dragging the mouse down from the lower right
corner to create a series of numbers based on the selected numbers.

{{< figure src="/images/excel/quicknum.gif" title="Creating number series" >}}


## Formulas

In Excel, formulas are a way to perform calculations. For example, you can use
the box just above the grid, where it says \\(f_x\\) on the left, to enter a
formula. 

You can test this by selecting an empty cell and typing `3 + 5` in the \\(f_x\\)
box.

Formulas can use functions, which behave in much the same way as
mathematical functions: they have arguments (input) and calculates a result
(output). Excel has a large number of built-in functions.

By using formulas and functions, you can perform complex calculations in your
spreadsheets.

### Entering formulas as text

To demonstrate how to manually entering formulas, we use the `SUM` function. As the name implies, this
function calculates the sum of a number of values.

Before proceeding, make sure you have some values in the range `A1:B11`.

In order for Excel to understand that you want to enter a formula in a cell
you must start the formula with `=` (equal sign), followed by
formula. Arguments to functions must be inside parentheses.

In the following example, we choose to place a formula in cell  `A12`. Click on
the cell `A12` and enter the following inside the cell, then press `Enter`.

``` text
=SUM(A1:B11)
```

In this example, we have entered a formula. The formula uses the `SUM` function.
The argument (input) to the `SUM` function is the range `A1:B11`. 

{{< figure src="/images/excel/sum.png" title="Beräkna summa" >}}

The result (output) of the formula automatically shows in the cell `A12`. The
result is the sum of the numbers in the range `A1:B11`.
Change a few numbers in the range `A1:B11` and see how the sum in cell `A12`
automatically is updated. 


### Entering formulas with the mouse.

You can also entering formulas using the mouse. 

1. Click on a cell.
2. Click on **Insert** -> **Function**.
3. Choose the function you wish to use from the menu. 
4. Select the range to use as input to the function. 
5. Finnish the formula by pressing on **Enter**. 

{{< figure src="/images/excel/stddev.gif" title="Applying the STDEVS function to the range `A1:A11`" >}}


### Advanced formulas

You can construct more advanced formulas by combining arithmetic and functions. 

+ Arithmetic calculation are done using the usual symbols `+` (addition), `-` (subtraction), `*` (multiplication) and `/` (division). The symbol `^` is used for exponentiation. 
+ Parentheses are used for grouping.
+ You can combine functions and arithmetic.
+ Cell and range references can be us as input to functins. 

Let's look at an example. 

{{< figure src="/images/excel/advfunc.png" title="A more advanced formula" >}}

In the above example, the formula `=SUM(B1:B11) + A11 * 3 + LOG(16,2)` has been
entered in the cell `C12`.

- The sum of the range `B1:B11` is added to the value in cell `A11` multiplied
  by `3`, finally the `2-log` of `16` is added.

- The formula calculates \\(11 + 11 \cdot 3 + 4\\) and the result `48` is shown
  in cell `C12`.

## Generate charts

One of the most important features in a spreadsheet is the ability to generate
graphical charts. Select the range with data you want to use to create a
chart. From the **Insert** tab, select the kind of chart you want to create.

In the following example, a **pie chart** is created from the data in the range
`A1:B11`.

{{< figure src="/images/excel/chart.gif" title="A pie chart of the data in the range `A1:B11`" >}}


### Editing charts

Once you created a chart the chart the be edited.

- Click on the `Chart Title` in the chart to  change the title. 

- To edit the chart type and other parameters, double click anywhere on the chart. Now a menu with chart settings will appear. 


### trendlines and regression analysis

The goal of regression analysis is to, based on observed data, create a function
that describes it. One way to illustrate this is to use trendlines.

{{< notice style="warning" title="Microsoft Live" >}}

The Microsoft Live version of Excel does not support trendlines. 

{{< /notice >}}


To add a trendline to a chart, first click on the chart. Now the tabs
**Design**, **Layout** and **Format** appears to the to upper right (1). 

{{< figure src="/images/excel/eng-chart-settings.png" title="Accessing chart trendline options" >}}

From the **Layout** tab (2), choose **Trendline** (3) to access the options for adding a trend
line to the chart.

You can also click on an already added trendline to access the trendline settings. 

{{< figure src="/images/excel/trendline-2.PNG" title="Trendline settings" >}}

Graphs are used to present data as clearly as possible. Use colors and other settings to make your graphs as easy as possible to understand. 

In the following example, three different data series are represented with different colors and different symbols. Three trendlines with the same colors as the data series have been added. 

{{< figure src="/images/excel/trendline-3.PNG" title="An example showing three different trendlines" >}}

In the following example, a trendline has been added to a bar chart. 

{{< figure src="/images/excel/chart-alt.PNG" title="Trendline added to a bar chart" >}}


\\(R^2\\) is a measure of the goodness of fit of a model. In regression, the
\\(R^2\\) coefficient of determination is a statistical measure of how well the
regression predictions approximate the real data points. An \\(R^2\\) of 1
indicates that the regression predictions perfectly fit the data.

In the above example, random values have been used in the spreadsheet. The
\\(R^2\\) value for the Johanna trendline is `0.0533`, i.e, the trendline is not
a very good fit to the data.
