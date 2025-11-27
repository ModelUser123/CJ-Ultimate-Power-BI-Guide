# 🏆 The Ultimate Power BI Guide - The Greatest Database of All Time

> **The Complete, Simplified Guide to Microsoft Power BI**  
> From absolute beginner to advanced user - with click-by-click instructions, real examples, and common mistakes to avoid.

---

## 📖 Table of Contents

1. [What is Power BI?](#-what-is-power-bi)
2. [Getting Started](#-getting-started)
3. [Data Connections](#-data-connections)
4. [Power Query - Transform Your Data](#-power-query---transform-your-data)
5. [Data Modeling](#-data-modeling)
6. [Relationships](#-relationships)
7. [DAX - From Basics to Advanced](#-dax---from-basics-to-advanced)
8. [Measures vs Calculated Columns](#-measures-vs-calculated-columns)
9. [Visualizations](#-visualizations)
10. [Slicers and Filters](#-slicers-and-filters)
11. [Bookmarks](#-bookmarks)
12. [Drill-Throughs](#-drill-throughs)
13. [Row-Level Security (RLS)](#-row-level-security-rls)
14. [Publishing to Power BI Service](#-publishing-to-power-bi-service)
15. [Scheduled Refresh](#-scheduled-refresh)
16. [Best Practices](#-best-practices)
17. [Common Mistakes and How to Avoid Them](#-common-mistakes-and-how-to-avoid-them)
18. [Quick Reference Cheat Sheet](#-quick-reference-cheat-sheet)

---

## 🎯 What is Power BI?

**Power BI** is Microsoft's business intelligence tool that transforms your raw data into beautiful, interactive reports and dashboards. Think of it as Excel on steroids - but way more powerful and easier to share.

### Power BI Family

| Component | What It Does | Who Uses It |
|-----------|--------------|-------------|
| **Power BI Desktop** | Free application to create reports | Report creators, analysts |
| **Power BI Service** | Cloud platform to share and collaborate | Everyone in the organization |
| **Power BI Mobile** | View reports on phones/tablets | Users on the go |
| **Power BI Report Server** | On-premises report hosting | Organizations requiring local storage |

### Why Use Power BI?

✅ **Free to download** - Power BI Desktop costs $0  
✅ **Connects to 100+ data sources** - Excel, SQL, Web, APIs, and more  
✅ **No coding required** - Drag and drop interface  
✅ **Real-time dashboards** - Data updates automatically  
✅ **Beautiful visualizations** - Professional charts in seconds  
✅ **Share anywhere** - Web, mobile, embedded in apps  

---

## 🚀 Getting Started

### Step 1: Download Power BI Desktop

**Click-by-Click Instructions:**
1. Open your web browser
2. Go to [powerbi.microsoft.com](https://powerbi.microsoft.com)
3. Click **"Download free"** button
4. Click **"Download"** under Power BI Desktop
5. Run the installer (.exe file)
6. Follow the installation wizard (Next → Next → Install)
7. Launch Power BI Desktop

### Step 2: Understanding the Interface

```
┌─────────────────────────────────────────────────────────────────────┐
│  File  Home  Insert  Modeling  View  Optimize  Help                │
├──────────┬─────────────────────────────────────────────┬────────────┤
│          │                                              │            │
│  FIELDS  │              REPORT CANVAS                   │   FILTERS  │
│  PANE    │                                              │   PANE     │
│          │   (Where your visualizations go)             │            │
│  List of │                                              │            │
│  tables  │                                              │            │
│  and     │                                              │            │
│  columns │                                              │            │
│          │                                              │            │
├──────────┴─────────────────────────────────────────────┴────────────┤
│  Report View  │  Table View  │  Model View                          │
└─────────────────────────────────────────────────────────────────────┘
```

**Three Views Explained:**

| View | Icon | Purpose |
|------|------|---------|
| **Report View** | 📊 | Create visualizations and reports |
| **Table View** | 📋 | View and inspect your data in table format |
| **Model View** | 🔗 | See and manage relationships between tables |

---

## 🔌 Data Connections

Power BI connects to over 100 data sources. Here are the most common ones with step-by-step instructions.

### Connecting to Excel

**Click-by-Click Instructions:**
1. Open Power BI Desktop
2. Click **Home** tab
3. Click **Get Data** → **Excel Workbook**
4. Navigate to your Excel file
5. Click **Open**
6. In Navigator window, check the boxes next to sheets/tables you want
7. Click **Transform Data** (recommended) or **Load**

**Real Example:**
```
Your Excel file: Sales_2024.xlsx
Contains sheets: [✓] January  [✓] February  [✓] March
Click Transform Data to clean the data first
```

**⚠️ Common Mistakes:**
- ❌ Selecting "Load" without reviewing data first
- ❌ Not converting data to Excel Tables before importing
- ❌ Having merged cells in Excel (Power BI hates these!)

**✅ Best Practice:** Always convert your Excel ranges to Tables (Ctrl+T in Excel) before importing.

---

### Connecting to SQL Server

**Click-by-Click Instructions:**
1. Click **Home** → **Get Data** → **SQL Server**
2. Enter Server name: `your-server-name.database.windows.net`
3. Enter Database name: `YourDatabaseName`
4. Choose Data Connectivity mode:
   - **Import** (recommended for most cases)
   - **DirectQuery** (for real-time, large datasets)
5. Click **OK**
6. Enter credentials (Windows/Database/Microsoft Account)
7. Select tables in Navigator
8. Click **Transform Data** or **Load**

**Real Example:**
```
Server: salesdb.database.windows.net
Database: AdventureWorks
Mode: Import
Tables selected: [✓] DimProduct  [✓] DimCustomer  [✓] FactSales
```

**⚠️ Common Mistakes:**
- ❌ Using DirectQuery when Import would be better (slower reports)
- ❌ Not specifying the database name
- ❌ Importing entire tables when you only need specific columns

---

### Connecting to Web/API

**Click-by-Click Instructions:**
1. Click **Home** → **Get Data** → **Web**
2. Choose **Basic** or **Advanced**
3. Enter URL: `https://api.example.com/data`
4. Click **OK**
5. If authentication required, enter credentials
6. Power BI will detect the data format (JSON, HTML tables, etc.)
7. Select data and **Transform Data**

**Real Example - Getting Currency Exchange Rates:**
```
URL: https://api.exchangerate-api.com/v4/latest/USD
Result: JSON data with exchange rates
Transform: Expand the "rates" record to get individual currencies
```

---

### Connecting to SharePoint

**Click-by-Click Instructions:**
1. Click **Home** → **Get Data** → **More...**
2. Search for "SharePoint"
3. Choose **SharePoint Online List** or **SharePoint Folder**
4. Enter SharePoint site URL: `https://yourcompany.sharepoint.com/sites/YourSite`
5. Click **OK**
6. Sign in with Microsoft account
7. Select lists or files
8. Click **Transform Data**

---

### All Data Source Categories

| Category | Examples |
|----------|----------|
| **File** | Excel, CSV, XML, JSON, PDF, Parquet |
| **Database** | SQL Server, Oracle, MySQL, PostgreSQL, Access |
| **Power Platform** | Dataverse, Dataflows |
| **Azure** | Azure SQL, Blob Storage, Data Lake, Synapse |
| **Online Services** | SharePoint, Dynamics 365, Salesforce, Google Analytics |
| **Other** | Web, OData, ODBC, R Script, Python Script |

---

## 🔄 Power Query - Transform Your Data

Power Query is where the magic happens. It's your data cleaning and transformation engine.

### Opening Power Query Editor

**Click-by-Click:**
1. Click **Home** → **Transform Data**
2. Power Query Editor opens in new window

### The Power Query Interface

```
┌─────────────────────────────────────────────────────────────────────┐
│  File  Home  Transform  Add Column  View  Tools  Help              │
├───────────┬─────────────────────────────────────┬───────────────────┤
│  QUERIES  │         DATA PREVIEW                │  QUERY SETTINGS   │
│           │                                     │                   │
│  • Sales  │  ID | Name    | Sales  | Date      │  Name: Sales      │
│  • Products│  1  | Widget  | 1000   | 1/1/24   │                   │
│  • Customers│ 2  | Gadget  | 1500   | 1/2/24   │  APPLIED STEPS    │
│           │  3  | Tool    | 800    | 1/3/24    │  • Source         │
│           │                                     │  • Navigation     │
│           │                                     │  • Changed Type   │
│           │                                     │  • Removed Cols   │
└───────────┴─────────────────────────────────────┴───────────────────┘
```

### Essential Transformations

#### 1. Remove Columns

**Why:** Get rid of data you don't need (makes report faster)

**Click-by-Click:**
1. Right-click column header
2. Click **Remove**

Or select multiple columns:
1. Ctrl+Click columns to remove
2. Right-click → **Remove Columns**

**M Code Generated:**
```m
= Table.RemoveColumns(PreviousStep, {"Column1", "Column2"})
```

---

#### 2. Change Data Types

**Why:** Ensure numbers are numbers, dates are dates, text is text

**Click-by-Click:**
1. Click the icon in column header (ABC, 123, etc.)
2. Select correct type: **Whole Number**, **Decimal Number**, **Date**, **Text**, etc.

**Data Type Icons:**
| Icon | Type | Example |
|------|------|---------|
| ABC | Text | "Hello World" |
| 123 | Whole Number | 42 |
| 1.2 | Decimal Number | 3.14159 |
| 📅 | Date | 1/15/2024 |
| 🕐 | Date/Time | 1/15/2024 2:30 PM |
| ✓/✗ | True/False | TRUE |

**⚠️ Common Mistake:** Leaving numbers as text - causes calculation errors!

---

#### 3. Filter Rows

**Why:** Remove unwanted data (blanks, errors, old records)

**Click-by-Click:**
1. Click dropdown arrow in column header
2. Uncheck values to exclude
3. Or use filters: **Number Filters**, **Text Filters**, **Date Filters**

**Real Example - Remove Blank Rows:**
1. Click dropdown on ID column
2. Uncheck **(blank)**
3. Click **OK**

**Real Example - Keep Only 2024 Data:**
1. Click dropdown on Date column
2. Click **Date Filters** → **After...**
3. Enter: 12/31/2023
4. Click **OK**

---

#### 4. Split Columns

**Why:** Separate combined data (like "FirstName LastName" into two columns)

**Click-by-Click:**
1. Select the column
2. Click **Transform** → **Split Column** → **By Delimiter**
3. Choose delimiter (Space, Comma, Custom)
4. Click **OK**

**Real Example:**
```
Before: "John Smith"
After:  "John" | "Smith"
```

---

#### 5. Merge Columns

**Why:** Combine multiple columns into one

**Click-by-Click:**
1. Ctrl+Click columns to merge
2. Click **Transform** → **Merge Columns**
3. Choose separator (Space, Comma, etc.)
4. Name new column
5. Click **OK**

**Real Example:**
```
Before: "123" | "Main St" | "New York"
After:  "123 Main St, New York"
```

---

#### 6. Replace Values

**Why:** Fix typos, standardize data

**Click-by-Click:**
1. Select column
2. Click **Transform** → **Replace Values**
3. Value to find: `NY`
4. Replace with: `New York`
5. Click **OK**

---

#### 7. Add Custom Column

**Why:** Create new calculated columns

**Click-by-Click:**
1. Click **Add Column** → **Custom Column**
2. Name your column
3. Enter formula

**Real Examples:**

**Profit Calculation:**
```m
= [Sales] - [Cost]
```

**Full Name:**
```m
= [FirstName] & " " & [LastName]
```

**Sales Category:**
```m
= if [Sales] > 10000 then "High" else if [Sales] > 5000 then "Medium" else "Low"
```

---

#### 8. Pivot and Unpivot

**Unpivot** - Turn columns into rows (wide to long format)

**Real Example:**
```
BEFORE (Wide):
Product | Jan | Feb | Mar
Widget  | 100 | 150 | 200

AFTER (Long - Unpivoted):
Product | Month | Sales
Widget  | Jan   | 100
Widget  | Feb   | 150
Widget  | Mar   | 200
```

**Click-by-Click to Unpivot:**
1. Select columns to unpivot (Jan, Feb, Mar)
2. Click **Transform** → **Unpivot Columns**

---

#### 9. Group By

**Why:** Aggregate data (sum, count, average)

**Click-by-Click:**
1. Click **Transform** → **Group By**
2. Group by: Select column(s)
3. New column name: `TotalSales`
4. Operation: **Sum**
5. Column: **Sales**
6. Click **OK**

**Real Example:**
```
Group by: [Region]
New column: TotalSales = Sum of [Sales]
New column: OrderCount = Count of [OrderID]
```

---

#### 10. Merge Queries (JOIN)

**Why:** Combine data from different tables

**Click-by-Click:**
1. Click **Home** → **Merge Queries**
2. Select matching columns from both tables
3. Choose Join Kind:

| Join Type | What It Returns |
|-----------|-----------------|
| **Left Outer** | All rows from first table + matches from second |
| **Right Outer** | All rows from second table + matches from first |
| **Full Outer** | All rows from both tables |
| **Inner** | Only matching rows |
| **Left Anti** | Rows from first table with NO match |
| **Right Anti** | Rows from second table with NO match |

4. Click **OK**
5. Expand the new column to see merged data

---

#### 11. Append Queries

**Why:** Stack tables on top of each other (UNION)

**Click-by-Click:**
1. Click **Home** → **Append Queries**
2. Choose **Two tables** or **Three or more tables**
3. Select tables to append
4. Click **OK**

**Real Example:**
```
Table1: January Sales (1000 rows)
Table2: February Sales (1200 rows)
Result: All Sales (2200 rows)
```

---

### Power Query M Language Basics

Every step you do creates M code behind the scenes.

**View M Code:**
1. Click **View** → **Advanced Editor**

**Basic M Syntax:**
```m
let
    // Step 1: Connect to data
    Source = Excel.Workbook(File.Contents("C:\Data\Sales.xlsx")),
    
    // Step 2: Navigate to sheet
    Sales_Sheet = Source{[Item="Sales",Kind="Sheet"]}[Data],
    
    // Step 3: Promote headers
    #"Promoted Headers" = Table.PromoteHeaders(Sales_Sheet),
    
    // Step 4: Change types
    #"Changed Type" = Table.TransformColumnTypes(#"Promoted Headers",{
        {"Sales", type number},
        {"Date", type date}
    }),
    
    // Step 5: Filter rows
    #"Filtered Rows" = Table.SelectRows(#"Changed Type", each [Sales] > 0)
in
    #"Filtered Rows"
```

**Useful M Functions:**
| Function | What It Does | Example |
|----------|--------------|---------|
| `Text.Upper` | Convert to uppercase | `Text.Upper("hello")` → "HELLO" |
| `Text.Lower` | Convert to lowercase | `Text.Lower("HELLO")` → "hello" |
| `Text.Trim` | Remove extra spaces | `Text.Trim(" hello ")` → "hello" |
| `Date.Year` | Extract year | `Date.Year(#date(2024,1,15))` → 2024 |
| `Date.Month` | Extract month | `Date.Month(#date(2024,1,15))` → 1 |
| `Number.Round` | Round number | `Number.Round(3.7)` → 4 |

---

### Applying Changes

**Click-by-Click:**
1. Click **Home** → **Close & Apply**
2. Wait for data to load
3. You're back in Power BI Desktop!

---

## 📐 Data Modeling

Data modeling is how you structure your data for optimal performance and analysis.

### Star Schema - The Gold Standard

```
                    ┌─────────────┐
                    │ DimDate     │
                    │ DateKey     │
                    │ Year        │
                    │ Month       │
                    │ Day         │
                    └──────┬──────┘
                           │
     ┌─────────────┐       │       ┌─────────────┐
     │ DimProduct  │       │       │ DimCustomer │
     │ ProductKey  │       │       │ CustomerKey │
     │ ProductName │       │       │ CustomerName│
     │ Category    │       │       │ Region      │
     └──────┬──────┘       │       └──────┬──────┘
            │              │              │
            │    ┌─────────┴─────────┐    │
            └────┤   FactSales       ├────┘
                 │ SalesKey          │
                 │ DateKey (FK)      │
                 │ ProductKey (FK)   │
                 │ CustomerKey (FK)  │
                 │ Quantity          │
                 │ Amount            │
                 └───────────────────┘
```

### Key Concepts

| Term | Plain English | Example |
|------|--------------|---------|
| **Fact Table** | Contains measurements/numbers you analyze | Sales amounts, quantities, counts |
| **Dimension Table** | Contains descriptive attributes | Product names, customer info, dates |
| **Primary Key** | Unique identifier in a table | CustomerID (each customer has unique ID) |
| **Foreign Key** | Links to another table's primary key | CustomerID in Sales table |
| **Cardinality** | How records relate between tables | One-to-Many, Many-to-One |

### Building Your Model

**Click-by-Click:**
1. Click **Model View** (icon on left side)
2. Drag tables to arrange them
3. Drag field from one table to matching field in another to create relationship
4. Or double-click relationship line to edit

### Table Properties

**Hide Tables/Columns from Report View:**
1. In Model view, right-click table or column
2. Click **Hide in report view**

**Why hide?** Cleaner field list, hide keys and technical columns users don't need

---

## 🔗 Relationships

Relationships connect your tables so data flows correctly in your reports.

### Creating Relationships

**Method 1: Drag and Drop**
1. Go to **Model View**
2. Drag a field from one table to matching field in another

**Method 2: Manage Relationships**
1. Click **Home** → **Manage Relationships**
2. Click **New**
3. Select tables and matching columns
4. Configure settings
5. Click **OK**

### Relationship Properties

**Cardinality:**
| Type | Meaning | Example |
|------|---------|---------|
| **One-to-Many (1:*)** | One record matches many | 1 Customer → Many Orders |
| **Many-to-One (*:1)** | Many records match one | Many Orders → 1 Customer |
| **One-to-One (1:1)** | One record matches one | 1 Employee → 1 Badge |
| **Many-to-Many (*:*)** | Many match many (avoid if possible!) | Students ↔ Classes |

**Cross-Filter Direction:**
| Setting | How Filters Flow |
|---------|------------------|
| **Single** | Filter flows one direction only |
| **Both** | Filter flows both directions (use carefully!) |

**⚠️ Common Mistakes:**
- ❌ Creating Many-to-Many relationships unnecessarily
- ❌ Using bi-directional filters everywhere (causes ambiguity)
- ❌ Not having a proper Date table

---

### Creating a Date Table

Every good Power BI model needs a Date table for time intelligence.

**Click-by-Click to Create Date Table:**
1. Click **Modeling** tab
2. Click **New Table**
3. Enter this DAX formula:

```dax
DateTable = 
ADDCOLUMNS(
    CALENDAR(DATE(2020,1,1), DATE(2030,12,31)),
    "Year", YEAR([Date]),
    "Month", MONTH([Date]),
    "MonthName", FORMAT([Date], "MMMM"),
    "Quarter", "Q" & QUARTER([Date]),
    "WeekDay", WEEKDAY([Date]),
    "DayName", FORMAT([Date], "dddd"),
    "YearMonth", FORMAT([Date], "YYYY-MM")
)
```

4. Press Enter

**Mark as Date Table:**
1. Click on DateTable in Fields pane
2. Click **Table Tools** → **Mark as date table**
3. Select the Date column
4. Click **OK**

---

## 📊 DAX - From Basics to Advanced

DAX (Data Analysis Expressions) is the formula language of Power BI. It's what makes your reports dynamic and powerful.

### DAX Basics

#### Syntax Rules
- Column references: `TableName[ColumnName]` or just `[ColumnName]`
- Measure references: `[MeasureName]`
- Text values: `"text in quotes"`
- Numbers: Just type them `100`, `3.14`
- Dates: `DATE(2024, 1, 15)` or `"1/15/2024"`

#### Creating Your First Measure

**Click-by-Click:**
1. Click on a table in Fields pane
2. Click **Home** → **New Measure**
3. Type your formula in the formula bar
4. Press Enter

---

### Essential DAX Functions

#### Aggregation Functions

```dax
// SUM - Add up all values
Total Sales = SUM(Sales[Amount])

// AVERAGE - Calculate average
Avg Sales = AVERAGE(Sales[Amount])

// COUNT - Count rows with values
Transaction Count = COUNT(Sales[TransactionID])

// COUNTROWS - Count all rows in a table
Total Orders = COUNTROWS(Sales)

// DISTINCTCOUNT - Count unique values
Unique Customers = DISTINCTCOUNT(Sales[CustomerID])

// MIN and MAX
Lowest Sale = MIN(Sales[Amount])
Highest Sale = MAX(Sales[Amount])
```

---

#### CALCULATE - The Most Important Function

`CALCULATE` changes the filter context. It's the foundation of advanced DAX.

**Syntax:**
```dax
CALCULATE(expression, filter1, filter2, ...)
```

**Real Examples:**

```dax
// Sales for a specific year
Sales 2024 = CALCULATE(SUM(Sales[Amount]), YEAR(Sales[Date]) = 2024)

// Sales for a specific category
Electronics Sales = CALCULATE(
    SUM(Sales[Amount]), 
    Products[Category] = "Electronics"
)

// Sales excluding a region
Sales Excl West = CALCULATE(
    SUM(Sales[Amount]), 
    NOT(Customers[Region] = "West")
)

// Remove all filters on a column
All Product Sales = CALCULATE(
    SUM(Sales[Amount]), 
    ALL(Products[Category])
)
```

---

#### Filter Functions

```dax
// FILTER - Returns a filtered table
High Value Sales = CALCULATE(
    SUM(Sales[Amount]),
    FILTER(Sales, Sales[Amount] > 1000)
)

// ALL - Removes filters
Total All Sales = CALCULATE(SUM(Sales[Amount]), ALL(Sales))

// ALLEXCEPT - Removes all filters except specified
Sales by Category Only = CALCULATE(
    SUM(Sales[Amount]),
    ALLEXCEPT(Sales, Products[Category])
)

// REMOVEFILTERS - Clearer way to remove filters (same as ALL)
Total Sales No Filter = CALCULATE(
    SUM(Sales[Amount]),
    REMOVEFILTERS()
)
```

---

#### Time Intelligence Functions

**Requires a proper Date table marked as date table!**

```dax
// Year-to-Date
YTD Sales = TOTALYTD(SUM(Sales[Amount]), DateTable[Date])

// Month-to-Date
MTD Sales = TOTALMTD(SUM(Sales[Amount]), DateTable[Date])

// Quarter-to-Date
QTD Sales = TOTALQTD(SUM(Sales[Amount]), DateTable[Date])

// Previous Year
PY Sales = CALCULATE(
    SUM(Sales[Amount]), 
    SAMEPERIODLASTYEAR(DateTable[Date])
)

// Year-over-Year Growth
YoY Growth = 
VAR CurrentYear = SUM(Sales[Amount])
VAR PreviousYear = CALCULATE(SUM(Sales[Amount]), SAMEPERIODLASTYEAR(DateTable[Date]))
RETURN
DIVIDE(CurrentYear - PreviousYear, PreviousYear, 0)

// YoY Growth %
YoY Growth % = [YoY Growth] * 100

// Previous Month
PM Sales = CALCULATE(
    SUM(Sales[Amount]),
    PREVIOUSMONTH(DateTable[Date])
)

// Rolling 12 Months
Rolling 12M Sales = CALCULATE(
    SUM(Sales[Amount]),
    DATESINPERIOD(DateTable[Date], MAX(DateTable[Date]), -12, MONTH)
)

// Moving Average (3 months)
3M Moving Avg = AVERAGEX(
    DATESINPERIOD(DateTable[Date], MAX(DateTable[Date]), -3, MONTH),
    CALCULATE(SUM(Sales[Amount]))
)
```

---

#### Logical Functions

```dax
// IF - Simple condition
Sales Status = IF([Total Sales] > 10000, "High", "Low")

// Nested IF
Sales Category = 
IF([Total Sales] > 100000, "Excellent",
    IF([Total Sales] > 50000, "Good",
        IF([Total Sales] > 10000, "Average", "Poor")
    )
)

// SWITCH - Cleaner than nested IFs
Sales Category = SWITCH(TRUE(),
    [Total Sales] > 100000, "Excellent",
    [Total Sales] > 50000, "Good",
    [Total Sales] > 10000, "Average",
    "Poor"
)

// AND / OR
Complex Filter = CALCULATE(
    SUM(Sales[Amount]),
    AND(
        Products[Category] = "Electronics",
        Customers[Region] = "East"
    )
)

// IFERROR - Handle errors gracefully
Safe Division = IFERROR(DIVIDE([Numerator], [Denominator]), 0)

// ISBLANK - Check for blanks
Has Value = IF(ISBLANK([Total Sales]), "No Data", "Has Data")
```

---

#### Text Functions

```dax
// CONCATENATE / & operator
Full Name = [FirstName] & " " & [LastName]

// LEFT, RIGHT, MID
First 3 Chars = LEFT(Products[ProductCode], 3)
Last 4 Chars = RIGHT(Products[ProductCode], 4)
Middle Chars = MID(Products[ProductCode], 2, 4)

// LEN - Length of text
Code Length = LEN(Products[ProductCode])

// UPPER, LOWER, PROPER
Upper Name = UPPER(Customers[CustomerName])
Lower Name = LOWER(Customers[CustomerName])
Proper Name = PROPER(Customers[CustomerName])

// TRIM - Remove extra spaces
Clean Name = TRIM(Customers[CustomerName])

// SUBSTITUTE - Replace text
Clean Phone = SUBSTITUTE(Customers[Phone], "-", "")

// FORMAT - Format dates/numbers as text
Month Name = FORMAT(DateTable[Date], "MMMM")
Year = FORMAT(DateTable[Date], "YYYY")
```

---

#### Table Functions

```dax
// SUMMARIZE - Group and aggregate
SalesSummary = SUMMARIZE(
    Sales,
    Products[Category],
    "Total", SUM(Sales[Amount]),
    "Count", COUNTROWS(Sales)
)

// ADDCOLUMNS - Add columns to a table
EnhancedProducts = ADDCOLUMNS(
    Products,
    "Total Sales", CALCULATE(SUM(Sales[Amount]))
)

// DISTINCT - Get unique values
UniqueCategories = DISTINCT(Products[Category])

// VALUES - Similar to DISTINCT but handles blank
AllCategories = VALUES(Products[Category])

// TOPN - Top N rows
Top5Products = TOPN(5, Products, [Total Sales], DESC)
```

---

### Advanced DAX Patterns

#### Running Total

```dax
Running Total = 
CALCULATE(
    SUM(Sales[Amount]),
    FILTER(
        ALL(DateTable),
        DateTable[Date] <= MAX(DateTable[Date])
    )
)
```

#### Rank

```dax
Product Rank = 
RANKX(
    ALL(Products[ProductName]),
    [Total Sales],
    ,
    DESC,
    Dense
)
```

#### Percentage of Total

```dax
% of Total = 
DIVIDE(
    SUM(Sales[Amount]),
    CALCULATE(SUM(Sales[Amount]), ALL(Sales))
)

% of Category = 
DIVIDE(
    SUM(Sales[Amount]),
    CALCULATE(SUM(Sales[Amount]), ALLEXCEPT(Sales, Products[Category]))
)
```

#### Parent-Child Hierarchy

```dax
// PATH function for hierarchies
Employee Path = PATH(Employee[EmployeeID], Employee[ManagerID])

// Get level in hierarchy
Hierarchy Level = PATHLENGTH([Employee Path])
```

#### Dynamic Measure Selection

```dax
// Create a "Measure" table with options
Selected Measure = 
SWITCH(
    SELECTEDVALUE(MeasureSelector[Measure]),
    "Sales", [Total Sales],
    "Quantity", [Total Quantity],
    "Profit", [Total Profit],
    [Total Sales]  // Default
)
```

---

### Variables in DAX

Variables make DAX more readable and efficient.

```dax
Profit Margin % = 
VAR TotalSales = SUM(Sales[Amount])
VAR TotalCost = SUM(Sales[Cost])
VAR Profit = TotalSales - TotalCost
RETURN
DIVIDE(Profit, TotalSales, 0)
```

**Benefits:**
- ✅ Code is easier to read
- ✅ Calculate value once, use multiple times (better performance)
- ✅ Easier debugging

---

## ⚖️ Measures vs Calculated Columns

This is one of the most important concepts in Power BI!

### Comparison Table

| Aspect | Measure | Calculated Column |
|--------|---------|-------------------|
| **When calculated** | At query time (when visual renders) | At refresh time (loaded into memory) |
| **Storage** | Not stored in model | Stored in model (uses memory) |
| **Aggregation** | Responds to filter context | Fixed value per row |
| **Use in slicers** | ❌ No | ✅ Yes |
| **Use in relationships** | ❌ No | ✅ Yes |
| **Performance** | Generally better | Uses more memory |
| **Created with** | DAX only | DAX or Power Query |

### When to Use Each

**Use CALCULATED COLUMN when:**
- ✅ You need to slicer/filter by the value
- ✅ You need to use it in a relationship
- ✅ Value doesn't change with filter context
- ✅ You're categorizing data (High/Medium/Low)

**Use MEASURE when:**
- ✅ You're doing aggregations (SUM, AVG, COUNT)
- ✅ Value should change based on filters
- ✅ You want to optimize model size
- ✅ You need time intelligence

### Real Examples

**Calculated Column Example:**
```dax
// Add to Products table
Price Category = 
IF(Products[UnitPrice] > 100, "Premium",
    IF(Products[UnitPrice] > 50, "Standard", "Budget")
)
```
→ Creates one value per product, can be used in slicer

**Measure Example:**
```dax
Total Sales = SUM(Sales[Amount])
```
→ Changes based on what's filtered in report

**⚠️ Common Mistake:**
```dax
// DON'T do this as a calculated column!
Sales Total = SUM(Sales[Amount])  // This won't work as expected!
```

---

## 📈 Visualizations

### Available Chart Types

| Category | Charts | Best For |
|----------|--------|----------|
| **Comparison** | Bar, Column, Clustered | Comparing values across categories |
| **Trend** | Line, Area | Showing change over time |
| **Part-to-Whole** | Pie, Donut, Treemap | Showing proportions |
| **Distribution** | Histogram, Box Plot | Showing data spread |
| **Relationship** | Scatter, Bubble | Showing correlations |
| **Geographic** | Map, Filled Map, Shape Map | Location-based data |
| **KPI** | Card, Multi-row Card, KPI | Single metrics |
| **Tables** | Table, Matrix | Detailed data views |
| **Other** | Gauge, Waterfall, Funnel | Specific use cases |

---

### Creating Visualizations

**Click-by-Click:**
1. Click on blank area of canvas
2. Select chart type from Visualizations pane
3. Drag fields to appropriate wells:
   - **Axis** / **X-Axis**: Categories/Dates
   - **Values** / **Y-Axis**: Numbers to show
   - **Legend**: Grouping/color coding
   - **Tooltips**: Additional info on hover
   - **Filters**: Visual-level filters

### Bar/Column Chart

**Best for:** Comparing values across categories

**Click-by-Click:**
1. Click **Clustered Bar Chart** icon
2. Drag `Category` to **Y-axis**
3. Drag `Sales` to **X-axis**

**Pro Tips:**
- Use bar (horizontal) when you have many categories
- Use column (vertical) for fewer categories
- Sort by value for easier reading

---

### Line Chart

**Best for:** Trends over time

**Click-by-Click:**
1. Click **Line Chart** icon
2. Drag `Date` to **X-axis**
3. Drag `Sales` to **Y-axis**
4. Optional: Drag `Category` to **Legend**

**Pro Tips:**
- Always use a continuous date axis
- Add markers for specific data points
- Use forecast feature for predictions

---

### Pie/Donut Chart

**Best for:** Part-to-whole comparisons (5 or fewer categories)

**Click-by-Click:**
1. Click **Pie Chart** or **Donut Chart** icon
2. Drag `Category` to **Legend**
3. Drag `Sales` to **Values**

**⚠️ Warning:** Don't use pie charts with more than 5 slices - use bar chart instead!

---

### Table and Matrix

**Table - Click-by-Click:**
1. Click **Table** icon
2. Drag fields to **Values** (each becomes a column)

**Matrix - Click-by-Click:**
1. Click **Matrix** icon
2. Drag fields to **Rows** (row headers)
3. Drag fields to **Columns** (column headers)
4. Drag measures to **Values**

**Real Example Matrix:**
```
Rows: Product[Category]
Columns: DateTable[Year]
Values: [Total Sales]

Result:
Category    | 2022    | 2023    | 2024
Electronics | $50,000 | $60,000 | $75,000
Clothing    | $30,000 | $35,000 | $40,000
```

---

### Card and Multi-Row Card

**Card** - Single big number
1. Click **Card** icon
2. Drag measure to **Fields**

**Multi-Row Card** - Multiple metrics
1. Click **Multi-row Card** icon
2. Drag multiple fields/measures to **Fields**

---

### Maps

**Map Visual - Click-by-Click:**
1. Click **Map** icon
2. Drag location field to **Location** (City, State, Country, or Lat/Long)
3. Drag measure to **Size** (bubble size)
4. Optional: Drag category to **Legend** (colors)

**Filled Map:**
1. Click **Filled Map** icon
2. Drag geographic field to **Location**
3. Drag measure to **Color saturation**

**⚠️ Common Mistake:** Location data must be recognized by Bing Maps. Use full names ("New York" not "NY").

---

### Formatting Visualizations

**Click-by-Click:**
1. Select visualization
2. Click **Format** icon (paint roller) in Visualizations pane
3. Expand sections to customize:

**Key Formatting Options:**

| Section | What You Can Change |
|---------|---------------------|
| **General** | Size, position, alt text |
| **Title** | Text, font, color, alignment |
| **Legend** | Position, font, colors |
| **Data labels** | Show values on chart |
| **Colors** | Change colors of bars/lines |
| **X-axis / Y-axis** | Labels, gridlines, range |
| **Data colors** | Conditional formatting |
| **Background** | Visual background color |
| **Border** | Add border around visual |

---

### Conditional Formatting

**Add Color Scales to Tables:**
1. Select table/matrix visual
2. Click dropdown on a measure
3. Click **Conditional formatting**
4. Choose: **Background color**, **Font color**, **Data bars**, or **Icons**

**Real Example - Color Scale:**
1. Click dropdown on `Sales` measure
2. **Conditional formatting** → **Background color**
3. Format style: **Gradient**
4. Minimum: Light Green, Maximum: Dark Green
5. Click **OK**

---

## 🎚️ Slicers and Filters

### Slicers

Slicers are visual filters that users can interact with.

**Creating a Slicer:**
1. Click **Slicer** icon in Visualizations pane
2. Drag a field to **Field** well

**Slicer Types:**

| Style | Best For | Setting |
|-------|----------|---------|
| **List** | Few options | Format → Slicer settings → Options → Style: Vertical list |
| **Dropdown** | Many options | Format → Slicer settings → Options → Style: Dropdown |
| **Between** | Date/Number ranges | (Automatic for numeric) |
| **Tile** | Visual buttons | Format → Slicer settings → Options → Style: Tile |

**Pro Tips:**
- Use **Sync slicers** to apply same slicer across pages
- Add **Select All** option: Format → Slicer settings → Selection → Show "Select all"
- Enable **Single select** or **Multi-select**

---

### Filter Types

| Filter Level | What It Affects | Where to Set |
|--------------|-----------------|--------------|
| **Visual filter** | One visualization | Filters pane → Filters on this visual |
| **Page filter** | All visuals on one page | Filters pane → Filters on this page |
| **Report filter** | All pages in report | Filters pane → Filters on all pages |
| **Drillthrough filter** | Target page | Drillthrough page setup |

**Click-by-Click to Add Filter:**
1. Click on Filters pane (right side)
2. Drag field to appropriate filter area
3. Configure filter type:
   - **Basic filtering**: Check/uncheck values
   - **Advanced filtering**: Contains, Starts with, etc.
   - **Top N**: Top/Bottom N values
   - **Relative date**: Last X days/months/years

---

### Interactions Between Visuals

By default, clicking one visual filters others. You can customize this.

**Click-by-Click:**
1. Select a visualization
2. Click **Format** tab (in ribbon)
3. Click **Edit interactions**
4. For each other visual, choose:
   - **Filter** (funnel icon) - Default
   - **Highlight** (highlight icon)
   - **None** (circle with line)
5. Click **Edit interactions** again to exit

---

## 🔖 Bookmarks

Bookmarks save the current state of a report page - including filters, slicer selections, and visual visibility.

### Creating Bookmarks

**Click-by-Click:**
1. Set up your page exactly how you want it
   - Apply filters/slicers
   - Hide/show visuals as needed
2. Click **View** tab
3. Click **Bookmarks** (checkmark it on)
4. In Bookmarks pane, click **Add**
5. Rename the bookmark (double-click)

### Bookmark Options

Right-click a bookmark to set:
- **Data**: Include current filters/slicers
- **Display**: Include visual show/hide states
- **Current page**: Save only current page
- **All visuals**: Include all visual properties
- **Selected visuals**: Capture only selected visuals

### Using Bookmarks for Navigation

**Create a navigation button:**
1. Click **Insert** → **Buttons** → **Navigator** → **Bookmark navigator**
2. Or use **Insert** → **Buttons** → **Blank**
3. Select button, Format pane → **Action** → **On**
4. Type: **Bookmark**
5. Bookmark: Select your bookmark

**Real Example - Toggle between views:**
1. Create "Sales View" bookmark (show sales chart)
2. Create "Profit View" bookmark (show profit chart)
3. Add two buttons
4. Link each button to respective bookmark
5. Users click buttons to switch views!

---

## 🔍 Drill-Throughs

Drill-through lets users right-click on a data point and navigate to a detailed page.

### Creating a Drill-Through Page

**Click-by-Click:**
1. Create a new page for details
2. Name it (e.g., "Product Details")
3. In Filters pane, find **Drill through** section
4. Drag the field to drill through by (e.g., `ProductName`)
5. Build your detail visuals on this page

**Using Drill-Through:**
1. Go back to main report page
2. Right-click on any data point with that field
3. Click **Drill through** → **Product Details**
4. Page shows filtered to that specific product!

**Add a Back Button:**
1. On drill-through page, note the auto-created back button
2. Or: **Insert** → **Buttons** → **Back**

---

### Drill-Down vs Drill-Through

| Feature | Drill-Down | Drill-Through |
|---------|------------|---------------|
| **What** | Explore hierarchy levels | Navigate to detail page |
| **How** | Click +/- icons on visual | Right-click → Drill through |
| **Example** | Year → Quarter → Month | Click product → See product details page |

---

### Creating Hierarchies for Drill-Down

**Click-by-Click:**
1. In Fields pane, right-click a field (e.g., Year)
2. Click **New hierarchy**
3. Drag other fields INTO the hierarchy (Quarter, Month, Day)
4. Use hierarchy in visual
5. Use drill icons on visual to navigate levels

**Drill Icons on Visuals:**
- ⬇️ **Drill down** - Go one level deeper
- ⬆️ **Drill up** - Go one level higher
- ⊕ **Expand all** - Show next level for all data points
- **🔻** **Show next level** - Go to next level

---

## 🔐 Row-Level Security (RLS)

RLS restricts data access based on who's viewing the report.

### Creating Roles

**Click-by-Click:**
1. Click **Modeling** tab
2. Click **Manage roles**
3. Click **Create**
4. Name the role (e.g., "East Region")
5. Select a table
6. Click **Add filter** → Write DAX filter expression
7. Click **Save**

**Real Example - Regional Access:**
```dax
// Role: East Region
// Table: Sales
// Filter: 
[Region] = "East"

// Now users with this role only see East region data
```

**Real Example - User-Based Access:**
```dax
// Role: Sales Reps
// Table: Sales
// Filter:
[SalesRepEmail] = USERPRINCIPALNAME()

// Users only see their own sales
```

### Testing RLS

**Click-by-Click:**
1. Click **Modeling** → **View as**
2. Check the role to test
3. Optionally enter email to test USERPRINCIPALNAME()
4. Click **OK**
5. View report as that role
6. Click **Stop viewing** when done

### Applying RLS in Power BI Service

1. Publish report to Power BI Service
2. Go to workspace
3. Click **...** (more options) on dataset
4. Click **Security**
5. Add users/groups to roles
6. Click **Save**

---

## ☁️ Publishing to Power BI Service

### Publishing Your Report

**Click-by-Click:**
1. Save your .pbix file
2. Click **Home** → **Publish**
3. Sign in with work/school account
4. Select workspace destination
5. Click **Select**
6. Wait for publishing to complete
7. Click link to open in browser

### Workspaces

| Workspace Type | Who Can Access | Best For |
|----------------|----------------|----------|
| **My Workspace** | Only you | Personal reports, testing |
| **Shared Workspace** | Workspace members | Team collaboration |
| **App Workspace** | App users | Distributing to organization |

**Creating a Workspace:**
1. In Power BI Service, click **Workspaces**
2. Click **Create a workspace**
3. Enter name and description
4. Configure access (optional)
5. Click **Save**

### Creating an App

Apps package reports and dashboards for easy distribution.

**Click-by-Click:**
1. Go to your workspace
2. Click **Create app**
3. Fill in **Setup**: Name, description, logo
4. **Navigation**: Choose which reports to include, set order
5. **Permissions**: Who can access the app
6. Click **Publish app**

---

## ⏰ Scheduled Refresh

### Prerequisites

For on-premises data (Excel on your computer, local SQL Server):
1. Install **Power BI Gateway**
2. Configure gateway in Power BI Service

For cloud data (SharePoint, Azure SQL):
- Just need credentials configured

### Setting Up Scheduled Refresh

**Click-by-Click:**
1. Go to Power BI Service
2. Navigate to your workspace
3. Click **...** on your dataset
4. Click **Settings**
5. Expand **Scheduled refresh**
6. Toggle **Keep your data up to date** ON
7. Set refresh frequency:
   - **Daily** at specific times
   - **Weekly** on specific days
8. Click **Apply**

### Refresh Frequency Limits

| License | Max Refreshes per Day |
|---------|----------------------|
| **Pro** | 8 |
| **Premium Per User** | 48 |
| **Premium Capacity** | 48 |

### Configuring Data Source Credentials

**Click-by-Click:**
1. In dataset settings, expand **Data source credentials**
2. Click **Edit credentials** for each source
3. Enter username and password
4. Set **Privacy level**
5. Click **Sign in**

### Gateway Configuration

**For On-Premises Data:**
1. Download and install Power BI Gateway
2. Sign in with Power BI account
3. Register the gateway
4. Add data sources to gateway
5. In Power BI Service, map dataset to gateway

---

## ✨ Best Practices

### Data Modeling

✅ **DO:**
- Use star schema design
- Create a proper date table
- Use surrogate keys (integers) for relationships
- Keep dimension tables narrow (few columns)
- Remove unnecessary columns before loading

❌ **DON'T:**
- Create unnecessary Many-to-Many relationships
- Use bi-directional filters everywhere
- Import more data than you need
- Store calculated columns that could be measures

### DAX

✅ **DO:**
- Use variables for readability and performance
- Use DIVIDE() instead of /
- Use ISBLANK() to handle missing data
- Keep measures simple and focused
- Document complex measures with comments

❌ **DON'T:**
- Use calculated columns for aggregations
- Nest too many IF statements (use SWITCH)
- Create circular dependencies
- Use FILTER when CALCULATE is sufficient

### Visualizations

✅ **DO:**
- Use appropriate chart types for your data
- Keep visualizations clean and uncluttered
- Use consistent colors throughout report
- Add titles and labels
- Design for the user, not for yourself

❌ **DON'T:**
- Use pie charts with more than 5 slices
- Overcrowd pages with too many visuals
- Use 3D charts (hard to read)
- Rely solely on color to convey meaning

### Performance

✅ **DO:**
- Use Import mode when possible
- Create aggregations for large datasets
- Optimize DAX calculations
- Remove unused columns and tables
- Use Performance Analyzer to identify bottlenecks

**Using Performance Analyzer:**
1. Click **View** → **Performance Analyzer**
2. Click **Start recording**
3. Click **Refresh visuals**
4. Review times for each visual
5. Identify slow visuals and optimize

---

## ⚠️ Common Mistakes and How to Avoid Them

### Mistake 1: Not Using a Date Table

**Problem:** Time intelligence functions don't work, inconsistent date handling.

**Solution:**
```dax
DateTable = 
ADDCOLUMNS(
    CALENDAR(DATE(2020,1,1), DATE(2030,12,31)),
    "Year", YEAR([Date]),
    "Month", MONTH([Date]),
    "MonthName", FORMAT([Date], "MMMM")
)
```
Mark it as a date table!

---

### Mistake 2: Calculated Columns for Aggregations

**Problem:** Creates a value for every row, wastes memory, doesn't filter correctly.

**Wrong:**
```dax
// As calculated column
Sales Total = SUM(Sales[Amount])  // Same value in every row!
```

**Right:**
```dax
// As measure
Total Sales = SUM(Sales[Amount])  // Responds to filters!
```

---

### Mistake 3: Dividing by Zero

**Problem:** Error values appear in your report.

**Wrong:**
```dax
Profit Margin = [Profit] / [Sales]
```

**Right:**
```dax
Profit Margin = DIVIDE([Profit], [Sales], 0)
```

---

### Mistake 4: Many-to-Many Relationships

**Problem:** Ambiguous results, poor performance.

**Solution:**
- Create a bridge table
- Or use bi-directional filtering carefully
- Or redesign your data model

---

### Mistake 5: Importing Unnecessary Data

**Problem:** Slow performance, large file sizes.

**Solution:**
- Remove unnecessary columns in Power Query
- Filter rows you don't need
- Use query folding when possible

---

### Mistake 6: Not Testing RLS

**Problem:** Users see data they shouldn't.

**Solution:**
- Always use "View as" to test each role
- Test with actual user emails
- Verify filters are correctly applied

---

### Mistake 7: Using Wrong Aggregation

**Problem:** Averages of averages, double-counting, etc.

**Wrong:**
```dax
// If Sales table already has daily totals
Avg Sales = AVERAGE(Sales[DailyTotal])  // Average of totals ≠ True average
```

**Right:**
```dax
Avg Sales = AVERAGEX(Sales, [Amount])  // Row-level average
```

---

### Mistake 8: Circular Dependencies

**Problem:** "Circular dependency" error.

**Solution:**
- Calculated columns can only reference columns loaded from source
- Measures should reference other measures, not calculated columns that reference the measure
- Redesign your calculations

---

### Mistake 9: Hardcoding Values

**Problem:** Report breaks when data changes.

**Wrong:**
```dax
Sales 2024 = CALCULATE([Total Sales], Sales[Year] = 2024)
```

**Right:**
```dax
Sales Current Year = CALCULATE([Total Sales], YEAR(TODAY()) = DateTable[Year])
```

Or better - use proper time intelligence!

---

### Mistake 10: Not Using Parameters

**Problem:** Hard to maintain connection strings, thresholds, etc.

**Solution:**
- Use Power Query parameters for connection strings
- Use What-If parameters for threshold values
- Makes maintenance easier!

---

## 📋 Quick Reference Cheat Sheet

### Essential DAX Functions

| Function | Purpose | Example |
|----------|---------|---------|
| `SUM` | Add values | `SUM(Sales[Amount])` |
| `AVERAGE` | Average | `AVERAGE(Sales[Amount])` |
| `COUNT` | Count values | `COUNT(Sales[ID])` |
| `COUNTROWS` | Count rows | `COUNTROWS(Sales)` |
| `DISTINCTCOUNT` | Unique count | `DISTINCTCOUNT(Sales[CustomerID])` |
| `CALCULATE` | Change context | `CALCULATE(SUM(Sales[Amount]), Filter)` |
| `FILTER` | Filter table | `FILTER(Sales, Sales[Amount]>100)` |
| `ALL` | Remove filters | `ALL(Sales)` |
| `RELATED` | Get related value | `RELATED(Products[Category])` |
| `DIVIDE` | Safe division | `DIVIDE([A], [B], 0)` |
| `IF` | Condition | `IF([Sales]>100, "High", "Low")` |
| `SWITCH` | Multiple conditions | `SWITCH([Value], 1, "A", 2, "B", "Other")` |

### Time Intelligence

| Function | Purpose |
|----------|---------|
| `TOTALYTD` | Year-to-date total |
| `TOTALMTD` | Month-to-date total |
| `TOTALQTD` | Quarter-to-date total |
| `SAMEPERIODLASTYEAR` | Same period last year |
| `PREVIOUSMONTH` | Previous month |
| `PREVIOUSYEAR` | Previous year |
| `DATESINPERIOD` | Rolling period |
| `PARALLELPERIOD` | Shifted period |

### Power Query M Functions

| Function | Purpose | Example |
|----------|---------|---------|
| `Table.RemoveColumns` | Remove columns | `Table.RemoveColumns(Source,{"Col1"})` |
| `Table.SelectRows` | Filter rows | `Table.SelectRows(Source, each [Amount]>0)` |
| `Table.AddColumn` | Add column | `Table.AddColumn(Source, "New", each [A]+[B])` |
| `Table.TransformColumnTypes` | Change types | `Table.TransformColumnTypes(Source,{{"Col",type number}})` |
| `Text.Upper` | Uppercase | `Text.Upper([Name])` |
| `Text.Trim` | Remove spaces | `Text.Trim([Name])` |
| `Date.Year` | Extract year | `Date.Year([Date])` |

### Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl + S` | Save |
| `Ctrl + Z` | Undo |
| `Ctrl + Y` | Redo |
| `Ctrl + C` | Copy |
| `Ctrl + V` | Paste |
| `Ctrl + A` | Select all visuals |
| `Ctrl + Click` | Multi-select visuals |
| `Ctrl + Enter` | Execute DAX formula |
| `F5` | Presentation mode |
| `Alt + F4` | Close Power BI Desktop |

---

## 🎓 Learning Path Progression

### Beginner (Week 1-2)
- [ ] Install Power BI Desktop
- [ ] Connect to Excel file
- [ ] Create basic visualizations
- [ ] Add slicers
- [ ] Publish first report

### Intermediate (Week 3-4)
- [ ] Master Power Query transformations
- [ ] Understand star schema
- [ ] Create relationships
- [ ] Write basic measures (SUM, AVERAGE, COUNT)
- [ ] Use CALCULATE function
- [ ] Apply formatting and themes

### Advanced (Month 2+)
- [ ] Master time intelligence
- [ ] Create complex DAX calculations
- [ ] Implement Row-Level Security
- [ ] Optimize performance
- [ ] Build dynamic reports with bookmarks
- [ ] Create custom visuals

---

## 📚 Additional Resources

- **Microsoft Learn:** [Power BI Documentation](https://docs.microsoft.com/power-bi/)
- **SQLBI:** Advanced DAX patterns - [sqlbi.com](https://sqlbi.com)
- **DAX Guide:** Function reference - [dax.guide](https://dax.guide)
- **Power BI Community:** Forums and discussions - [community.powerbi.com](https://community.powerbi.com)

---

## 🏆 Congratulations!

You now have the knowledge to build amazing Power BI reports! Remember:

1. **Start simple** - Build basic reports first
2. **Learn DAX gradually** - Master basics before advanced
3. **Practice regularly** - Try new techniques on real data
4. **Ask for help** - Community forums are friendly!
5. **Keep learning** - Power BI is constantly improving

---

**Made with ❤️ for the Power BI community**

*This guide is maintained and updated regularly. Contributions welcome!*