# Power BI note

### Study notes used when strengthening Power BI skills

## Part 1: Visualising data. 

### <1> Customisation
#### 1.1.1 Grid font size change the size for an entire visual. 

#### 1.1.2 matrix has drill through, whereas table just summary

#### 1.1.3 View -> sync slicers, when deleting a slicer remeber to reset it (use view -> selection to see underlying active slicer). 

#### 1.1.4 column tool -> sort by a column
#### 1.1.5 only categorical can be sorted, not continuous. 
#### 1.1.6 button text for hover over style for a text. 

### <2> Visualisation
#### 1.2.1 ribbon chart shows the rank of a group in the total.
#### 1.2.2 waterfall chart shows the cumulative of values.
#### 1.2.3 scatter plot shows the relationship, comparison between two numbers. 
#### 1.2.4 pie charts and donut charts, how categories made up to the total. 
#### 1.2.5 tree map is an alternative.
#### 1.2.6 funnel chart, sequential data, trend going by series and stages. 
#### 1.2.7 you cannot change format for a column if it's in a hierarchy, you have to format it when it's not in a hierarchy then added to hierarchy after formatted. 

#### 1.2.8 arcmap for power bi does not have all country, you can add the data, then zoom to country of interest, then search the country specific map from reference layer list on arcgis online. 

#### 1.2.9 Gauge charts shows the progress towards a certain target.
#### 1.2.10 function colouring -> whichever ones come in the latter, takes the higher priority when conditional formatting has overlap figure. 

#### 1.2.11 KPI charts compare something over time against a target. 
#### 1.2.12 quick measure may not work with some special cases, such as comma as digit separators instead of dot. 

#### 1.2.13 reference line can be added via the analytics pane, can't be used in all visualisation such as combined charts. 

#### 1.2.14 numerical grouping = binning (bucketing)
#### 1.2.15 key influencer shows the main contributer for something; top segements shows  the main semgents for something.

#### 1.2.16 tree decomposition shows how a measure breaks down at different levels. high values, low values. 
#### 1.2.17 PBIDS (power bi desktop source) pointer to a data source. PBIDS is a json object. (just double click to open, instead of adding data within power bi).
#### 1.2.18 paginate report created by power bi report builder. (used for pixel wise perfect), it's an additional licensing. row groups expand vertically, column group expand horizontally (i.e. row level total). 
#### 1.2.19 anomaly detection only works for line chart, only works for one measure and does not work for forecasting. Sensitivity -> how far a line chart can drift from the central line.
#### 1.2.20 identify outliers in powerbi: https://datacornering.com/how-to-identify-outliers-in-microsoft-power-bi/
#### 1.2.21 Smart narrative vs summarize: smart narrative gives narratives for all visuals on a page, summarize only gives narratives for one particular visual. Does not work for other than line visuals so far.  

## Part 2: Get and Transform data.

### <1> Get Data

#### 2.1.1 Workflow: Get data (Mashup(M) formulas) -> Add modeling (DAX formulas) -> Visualise data -> Share data

#### 2.1.2 Key M queries: 
#### Date.Day, Date.DayOfWeek, Date.DayOfWeekName, Date.DayOfYear, Date.DayInMonth, Date.EndOfDay, Date.EndOfMonth, Date.EndOfQuarter, Date.EndOfWeek, Date.Month, Date.MonthName, Date.QuarterOfYear, Date.StartOfDay, Date.StartOfMonth, Date.StartOfWeek, Date.StartOfYear, Date.WeekOfMonth, Date.WeekOfYear
____________________________________________________________________
#### DateTime.Date, DateTime.LocalNow, DateTime.Time, DateTime.From, DateTime.To
____________________________________________________________________

#### DateTimeZone.FixedLocalNow, DateTimeZone.FixedUtcNow, DateTimeZone.LocalNow
____________________________________________________________________

#### Day.Friday, Day.Monday, Day.Saturday, Day.Sunday, Day.Thursday, Day.Tuesday, Day.Wednesday
____________________________________________________________________

#### Duration.TotalDays, Duration.TotalHours, Duration.TotalMinutes, Duration.TotalSeconds
____________________________________________________________________

#### Json.Document, Xml.Tables
____________________________________________________________________
#### List.Average, List.Distinct, List.Max, List.Min, List.Median, List.NonNullCount, List.Sum
____________________________________________________________________
#### Number.Abs, Number.IntegerDivide, Number.Mod, Number.Round, Number.RoundAwayFromZero, Number.RoundDown, Number.RoundTowardZero, Number.RoundUp, Number.Sign, Number.Power
____________________________________________________________________
#### Table.AddIndexColumn, Table.AlternateRows, Table.Combine, Table.CombineColumns, Table.DemoteHeaders, Table.ExpandTableColumn, Table.FillDown, Table.FillUp, Table.FirstN, Table.Group, Table.LastN, Table.NestedJoin, Table.Pivot, Table.PromoteHeaders, Table.Range, Table.RemoveColumns, Table.RemoveLastN, Table.RemoveRowsWithErrors, Table.RenameColumns, Table.ReorderColumns, Table.ReplaceErrorValue, Table.ReplaceValue, Table.ReverseRows, Table.RowCount, Table.SelectColumns, Table.SelectRows, Table.SelectRowsWithError, Table.Skip, Table.Sort, Table.SplitColumn, Table.TransformColumn, Table.TransformColumnType, Table.Transpose, Table.Unpivot, Table.UnpivotOtherColumns
____________________________________________________________________
#### Text.Clean, Text.End, Text.Length, Text.Lower, Text.Middle, Text.Proper (captalising every first letter), Text.Start, Text.Trim, Text.Upper


### <2> Transform Data
#### 2.2.1 duplicate query in power query, only creates a reference to the first data query.

     


#### 2.2.2 default filter applies step by step transformation. Therefore, after moved away from a previously applied filter step, cannot unfilter what had been filtered. 
#### 2.2.3 M function splitter start with 0 index. 
#### 2.2.4 unpivot selected column will be affected if the data model is changed, whereas unpivot column and unpivot other column will not be affected. 
#### 2.2.5 unpivioting nest column, transpose to fill down missing value, then unpivot.
#### 2.2.6 transform merge column remove original columns, add column merge column creates a new column.

#### 2.2.7.trim -> removing leading and trailing spaces, replace -> useful for removing double spaces. 

#### 2.2.8 date function in power query -> #date(yyyy,mm,dd), duration function #duration(day,hour,minute,second), time function #time(hour,minute,second)

#### 2.2.9 List.Numbers(), List.Dates(), List.Times()

#### 2.2.10 Date.From(), DateTime.LocalNow(), DateTime.FixedLocalNow()

### <3> Get Data from other sources

#### 2.3.1 reading data from sql server -> Include relationship column will also query related tables. 

#### 2.3.2 Import vs DirectQuery pros and cons: https://docs.microsoft.com/en-us/power-bi/connect-data/desktop-use-directquery, DirectQuery better for large query and ensures up-to-date data,cannot change from Import to DirectQuery mode, but can change from DirectQuery to Import mode.

#### 2.3.3 PowerBI auto page refresh for ever  interval and change detection -> check changes for every X interval (seconds in premium Power BI service).

#### 2.3.4 Dataverse -> new name for CDS (common data service), data service used in Power platform.
#### 2.3.5 choose the appropriate query type  (https://www.pbiusergroup.com/communities/community-home/digestviewer/viewthread?MessageKey=2296a913-4b3e-4489-94b0-016b0d1f44ec&CommunityKey=b53b454c-0560-4600-a098-9b1887af0d85&tab=digestviewer)
#### 2.3.6 diagnostics 

#### 2.3.7 Text Analytics (requires power bi premium), Vision (requires power bi premium) and Azure Machine learning (Azure machine learning workspace)


## Part 3: Model data. 

### <1> DAX Function
#### 3.1.1 Relationship direction in relation diagram matters. Cross filter direction is single is more efficient in most case (not degrading performance), however, relationship is not measured from the pointee to pointer.   
#### 3.1.2 DAX needs to use BLANK() if want to set cell to no value.
#### 3.1.3 instead of using the new measure button on modelling, it's better to select the query first, and then choose create new query. 
#### 3.1.4 INT function in DAX rounding down to the nearest integer, hence -3.6 = -4 whereas 3.6 = 3
#### 3.1.5 TRUNC function simply removes the decimal part. 
#### 3.1.6 always provide 'not found' action in search() function. search() is case insensitive, find() is case sensitive. 
#### 3.1.7 DAX is base 1, index start from 1 instead of 0. 
#### 3.1.8 Replace() uses position, Substitute uses known text. 
#### 3.1.9 related() is useful the go from downstream tables to against the relationship arrow and pull information from other tables (from many to one). 
#### 3.1.10 relatedtable() return a filtered table (aka context, not a single column), then can use table operations such as sumx() to perform aggregation. it's provide better performance when using in visuals. 
#### 3.1.11 all() removes the context from a related table.
#### 3.1.12 filter() goes further down the granular detail. (can be replace with a if(sumx()) chain). 
#### 3.1.13 calculate() acting as a wrapper which has the context build in as a parameter then a regular calculation. function as another parameter. sumx(all()) = calculate(sumx(),all()).
#### 3.1.14 min/max() return a value, first/last() return a table/column.
#### 3.1.15 be aware of the context of date when using nextday and previousday, do not use hierarchy.
#### 3.1.16 TOTALMTD and OPENINGBALANCEMONTH do not use CALCULATE() wrapper.
#### 3.1.17 time based measures are usually is semi additive measure. you can only sum up measures during a specific period. 
#### 3.1.18 NATURALINNERJOIN() = MERGE Query
#### 3.2.19 'Make the relation active', in power bi, you can only have one active relationship on columns between two  tables.

#### 3.2.20 role playing model, more than one relationship between two tables. 
#### 3.2.21 userelationship() to choose different relationship between two tables. 
#### 3.2.22 if no relationship between tables is defined, the <b>maximum</b> amount will be used in measurements. 
#### 3.2.23 when dealing with mismatched m-to-m relationship, can create a 'bridge' table uses only the mismatched column that union the common factor columns together from two tables. 
#### 3.2.24 another way dealing with m-to-m relationship is to define the cardinality in relationship property window. 
#### 3.2.25 last way to deal with m-to-m relationship is to create an aggregation of the measure using 'group by'. 
#### 3.2.26 View -> Performance analyzer
#### 3.2.27 Power Query -> Tools -> diagnostics