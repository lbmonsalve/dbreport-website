# DBReport

---

Is a [Xojo/RealBasic](http://www.xojo.com) component for reports. Download [here](https://goo.gl/w6kUcw). Bernardo Monsalve: lbmonsalve at outlook . com

**PURCHASES BY PAYPAL:**

Encrypted: [US$70](https://www.paypal.com/cgi-bin/webscr?cmd=_xclick&business=SAJSKXXB68ENL&lc=CO&item_name=DBReport%20component%20for%20Xojo%20%28RB%29&item_number=1020&amount=70%2e00&currency_code=USD&button_subtype=services&bn=PP%2dBuyNowBF%3abtn_buynowCC_LG%2egif%3aNonHosted) </br>
Source code: [US$140](https://www.paypal.com/cgi-bin/webscr?cmd=_xclick&business=SAJSKXXB68ENL&lc=AL&item_name=DBReport%20with%20source%20code&item_number=1030&amount=140%2e00&currency_code=USD&button_subtype=services&bn=PP%2dBuyNowBF%3abtn_buynowCC_LG%2egif%3aNonHosted)

## Introduction

DBReport is a Xojo (formerly known as Realbasic) component to create, edit and print reports in runtime; unlike Xojo Report which is good enough for simple reporting from databases, however don’t have an editor in runtime, formulas, parameters and other features. 

## Main features

* Edit report in runtime. 
* Report definition to .xml or String (to save in a DB field). 
* Preview of report. 
* View dataset of records. 
* Width, height, margins set or import from printer. 
* Report Header, Report Footer, Page Header, Pager Footer and group bands. 
* Labels, fields, lines, rectangles, images, charts (bar, line,pie), barcodes. 
* Sum, count and subtotal functions. 
* Formulas. 
* Parameters. 
* SubReports. 

## Requirements

DBReport is pure Xojo (RealBasic) code, don't need plug-ins (however can use [BarcodeMBS](http://www.monkeybreadsoftware.net/class-barcodegeneratormbs.shtml) and [DynaPDFMBS](http://www.monkeybreadsoftware.de/xojo/plugin-dynapdf.shtml)), tested from RealStudio 2011r4 to Xojo 2017r3. Cocoa framework on MacOS is required. You need a registration code which is obtained (for free or open-source projects) by sending an email to lbmonsalve at outlook.com, otherwise works in DEMO mode.

## Adding the component

### Adding Component

1. Download the zip file, extract files. 
2. Open Xojo (RealStudio) project or create one. 
3. Add DBReport* files from DBReport folder. You can add one-by-one using File→Import or drag'n drop folder or files to project's tab. 

### Register the component

While the component is not registered works in DEMO mode, which meaning when print it, shows "\*demo\*" randomly. To register the component, add the next code just one time (perhaps on App.Open event) before use: 

```vb
DBReport.Register= "YOUR REGISTER CODE..."
```

---

## Report structure

A report consists of bands that have elements which are stored in a definition file or a text string. The report is usually assigned a recordset from database and is printed or displayed on screen. 

### Bands

To understand how the DBReport works we need to understand the concept of bands. 

A band is a box where we put objects, the most important band is **Detail** which is the only one who can not erase. This (Detail) is printed for each row or record of the RecordSet, eg. if we have 10 rows or records we have 10 bands Detail. 

The band **Page header** is printed first in the top of the page for each page in the report generated. 

The band **Page footer** is printed on the bottom of the page for each page in the report generated. 

The band **Report header** is printed after the band page header on the first page of the report. 

The band **Report footer** is printed just after the last band printed on the final page of the report. 

Group bands are bands that are printed before the band **Detail** like **Group Header** and then like **Group Footer**. They print to change the group (field of a recordset) or at the beginning of the report in the case of Group Header or end of the report in case of Group Footer. You can have as many group bands as needed. 

### Elements

The objects that can be placed in the bands are: 

* __Labels__: are texts like “Title Report” or the system date as “#date” or page number like “#pag” or parameters or formulas. 
* __Fields__: field of Recordset like “name” or “id”. 
* __Lines__: horizontal, vertical or oblique. 
* __Rectangles__ boxes or rounded rectangles. 
* __Barcodes__. 
* __Images__: Can be an image file, parameter or a RecordSet field. 
* __Charts__: Bar, lines, pie. 
* __SubReports__. 

Note: Use XojoScript (RBScript) in formulas with “SetValue EXPRESSION” like: 

```vb
SetValue (10+5)* RecNum+ (2* .1* RecNum)
' or
SetValue "String"
' or
SetValue ElementName* ParameterName
' or
SetValue Left(FieldName1, 10)+ " "+ FieldName2
' or
If FieldName1.InStr("cad")= 0 Then
    SetValue "No Contains cad"
Else
    SetValue "Contains cad"
End
```

### Parameters

A parameter is assigned before calling the Designer or Print (“Logo” is an example, may be called as you want):

```vb
rpt.Parameter("Logo")= PictureObject
rpt.Parameter("CompanyName")= "My Company Name"
```

### Properties

A property in DBReport is a special data used outside of report for whatever you want, example: save the database name or SQL string. Is used as metadata of report, but not in report itself. 

```vb
rpt.Prop("sqlString")= "SELECT * FROM table"
rpt.Prop("databaseName")= "MyDB"
```

### XML Definition file

The definition of report is in XML structure, you can change the extension of file whatever you like. This is an example: 

```xml
<?xml version="1.0" encoding="UTF-8"?>
<DBReport Version="1.4.4407">
  <SubReport>
    <Band id="1" Name="ReporHeader1" Type="30"/>
    <Band id="2" Name="Detail" Height="20"/>
    <Band id="3" Name="ReportFooter1" Type="40" Height="58"/>
    <Element id="4" Name="Element1" BandId="1" Left="2" Top="7" Value="Title of report" OrderToShow="0"/>
    <Element id="5" Name="Element2" DataField="name" BandId="2" Left="4" Top="3" Type="20" OrderToShow="0"/>
    <Element id="6" Name="Element3" BandId="1" Left="455" Top="11" Value="#pag" OrderToShow="1"/>
    <Element id="7" Name="Element4" BandId="3" Left="235" Top="3" Value="#date" AlignH="1" OrderToShow="0"/>
  </SubReport>
</DBReport>
```

### XML Preferences file

DBReport saves preferences like position of Designer window or zoom in a preferences.xml file in: SpecialFolder.ApplicationData.Child("DBReport").

---

## Examples

### Modify report

RecordSet variable "rs" must be exist.

```vb
Dim f as FolderItem= SpecialFolder.Documents.Child("DBReport1.xml")

Dim rpt As New DBReport
rpt.LoadXML(f)
rpt.RecordSet= rs
rpt.Designer
rpt.SaveXML(f)
```

If you want store the definition of report on string variable:

```vb
Dim rpt As New DBReport
 
rpt.LoadXML(StringVariable)
rpt.RecordSet= rs
rpt.Designer
StringVariable= rpt.GetXML()
```

### Print report

```vb
Dim f as FolderItem= SpecialFolder.Documents.Child("DBReport1.xml")
 
Dim rpt As New DBReport(f, rs)

rpt.Print
```

### Preview report

The report and RecordSet must be exist and assign RecordSet to report. Add "DBReportPreview" controlContainer to a window, assign report to controlContainer: 

```vb
DBReportPreview1.Report(rptVariable)
```

### Other form to use

DBReportDesignerControl and DBReportPreview are ControlContainers, you can place on a Window, set it and used like another control eg. TextField or TextArea. 

You can add DBReportDesignerControl to a window and set report with: `DBReportDesignerControl1.Report(rpt)`, you need save the changes with a button with action like: `rpt.SaveXML(f)`. Maybe another button for print. 

Also you can create reports by coding:

```vb
Dim sRpt As New DBReportSubReport
 
Dim bnd As New DBReportBand
bnd.Name= "PageHeader"
bnd.Type= Int32(DBReportBand.BandType.PageHeader)
sRpt.BandAdd(bnd)
 
Dim ele As New DBReportElement
ele.BandId= bnd.Id
ele.Type= Int32(DBReportElement.ElementType.Label)
ele.Value= "Title"
sRpt.ElementAdd(ele)
 
bnd= New DBReportBand
bnd.Name= "Detail1"
bnd.Type= Int32(DBReportBand.BandType.Detail)
bnd.Height= 20
sRpt.BandAdd(bnd)
 
ele= New DBReportElement
ele.BandId= bnd.Id
ele.Type= Int32(DBReportElement.ElementType.Field)
ele.DataField= "name"
ele.Left= 30
ele.Top= 1
ele.Width= 300
ele.HeightExpand= True
sRpt.ElementAdd(ele)
 
bnd= New DBReportBand
bnd.Name= "PageFooter"
bnd.Type= Int32(DBReportBand.BandType.PageFooter)
bnd.Height= 58
sRpt.BandAdd(bnd)
 
ele= New DBReportElement
ele.BandId= bnd.Id
ele.Type= Int32(DBReportElement.ElementType.Label)
ele.Value= "#pag"
sRpt.ElementAdd(ele)
 
Dim rpt As New DBReport
rpt.SubReportAdd(sRpt)
```

---

## Tutorial: Basic

This tutorial is basic use of DBReport. The goal is create two buttons, one for designer and other for print a report. 

### Requirements

* DBReport component. 
* A sample SQLite database (sakila database is used for this tutorial, is found in [downloaded](http://goo.gl/xhUoeb) file). 

### Walkthrough

1. Create a project. 
2. Add DBReport component. 
3. Add SQLite database. 
4. Add a button, change caption to "Designer". 
5. Add code for Designer to Action event. 
6. Add a button, change caption to "Print". 
7. Add code for Print to Action event. 
8. Run app. 
9. Click on Designer button. 
10. Add labels and fields to report. 
11. Close designer window. 
12. Click on Print button. 

A video show an example [here](http://youtu.be/dA81VKjqq38).

### Code for Designer button

```vb
Dim f As FolderItem= SpecialFolder.Desktop.Child("DBReportTut01.xml")
Dim r As Recordset= sakila.SQLSelect("SELECT * FROM customer")
 
Dim rpt As New DBReport(f, r)
rpt.Designer
rpt.SaveXML(f)
```

### Code for Print button

```vb
Dim f As FolderItem= SpecialFolder.Desktop.Child("DBReportTut01.xml")
Dim r As Recordset= sakila.SQLSelect("SELECT * FROM customer")
 
Dim rpt As New DBReport(f, r)
 
rpt.Print
```

## Tutorial: Add reports

This tutorial adds a report to existing app. The goal is create a menuItem for design and print. Use the EddiesElectronics desktop app, On "Project chooser" window select Examples, "Sample Applications"/EddiesElectronics/Desktop folder and open EEDesktop.xojo_binary_project file. 

### Requirements

* DBReport component. 
* EEDesktop example app.

### Walkthrough

1. Open EEDesktop app from "Project chooser" window. 
2. Add DBReport component. 
3. Add menuItem to File menu on MainMenuBar. 
4. Change Name to "FilePrintCustomers". 
5. Change Text to "Print customers". 
6. Navigate to "Menu Handlers" from CustomerDetailWindow. 
7. Add "Menu Handler" event. 
8. Choose FilePrintCustomers from MenuItem name. 
9. Add code for Designer. 
10. Run App. 
11. Click on "Print customers" from File menu. 
12. Add labels and fields to report. 
13. Close Designer window. 
14. Close App. 
15. Add rpt.Print to FilePrintCustomers event. 
16. Run App. 
17. Click on "Print customers" from File menu.

A video show an example [here](http://youtu.be/haNjPzOcc6Q). 

### Code for Designer

```vb
Dim f As FolderItem= SpecialFolder.Desktop.Child("DBReportTut02.xml")
Dim r As Recordset= App.Orders.FindCustomersByName
 
Dim rpt As New DBReport(f, r)
rpt.Designer
rpt.SaveXML(f)
```

## Tutorial: Using templates

This is a tutorial about how use templates in DBReport. The goal is create a report based on previous saved report. 

A template is just a report definition previously saved witch is imported in designer. Is useful for save time with similar reports. 

### Requirements

* Basic usage tutorial.

### Walkthrough

1. Rename "DBReportTut01.xml" file to "Template.xml". 
2. Open Tutorial01 project. 
3. Open Action event of Designer button. 
4. Change rpt.Designer line. 
5. Save project as Tutorial03. 
6. Run App. 
7. Click on Designer button. 
8. Click on Export button. 
9. Choose "Import" from popup menu. 
10. Select "Template.xml" from desktop. 

A video show an example [here](http://youtu.be/xZh28r1KipU). 

### Code for Designer

```vb
rpt.Designer "{""ShowExpImpBtn"": True}"
```

## Tutorial: Store in database

In this tutorial a database is used for store report definition. The goal is save and retrieve a report definition from a column table of database.

### Requirements

* Basic usage tutorial. 
* A sakila_rpts SQLite database (is found in [downloaded](http://goo.gl/xhUoeb) file). 

### Walkthrough

1. Open Tutorial01 project. 
2. Add sakila_rpts database. 
3. Add a button, change caption to "Desig. db". 
4. Add code for Desig. db to Action event. 
5. Add a button, change caption to "Print db". 
6. Add code for Print db to Action event. 
7. Save project as Tutorial04 
8. Run app. 
9. Click on Desig. db button. 
10. Click on Export button. 
11. Choose "Import" from popup menu. 
12. Select "Template.xml" from desktop. 

A video show an example [here](http://youtu.be/rPVVFGQiXCA).

### Code for "Desig. db" button

```vb
Dim s As String
Dim i As Boolean
Dim r As RecordSet= sakila_rpts.SQLSelect("SELECT * FROM  reports WHERE name= 'Tutorial04';")
 
If r<> Nil Then
  If Not r.EOF Then
    s= r.Field("definition").StringValue
  Else
    i= True //INSERT
  End If
End If
 
r= sakila.SQLSelect("SELECT * FROM customer")
 
Dim rpt As New DBReport(s, r)
rpt.Designer "{""ShowExpImpBtn"": True}"
 
// Prepare statement
Dim p As PreparedSQLStatement
 
If i Then
  p= sakila_rpts.Prepare("INSERT INTO reports (group_name, name, definition) VALUES ('Tutorials', ?, ?)")
Else
  p= sakila_rpts.Prepare("UPDATE reports SET name= ? WHERE definition= ?")
End If
p.BindType(0, SQLitePreparedStatement.SQLITE_TEXT)
p.BindType(1, SQLitePreparedStatement.SQLITE_TEXT)
 
p.SQLExecute("Tutorial04", rpt.GetXML)
```

### Code for "Printer db" button

```vb
Dim s As String
Dim r As RecordSet= sakila_rpts.SQLSelect("SELECT * FROM  reports WHERE name= 'Tutorial04';")
 
If r<> Nil Then
  s= r.Field("definition").StringValue
End If
 
r= sakila.SQLSelect("SELECT * FROM customer")
 
Dim rpt As New DBReport(s, r)
 
rpt.Print
```

---

## Community

* [Blog](http://lbmonsalve.wordpress.com/)

## Support

* [Issue tracker](https://github.com/lbmonsalve/dbreport/issues)

## Credits

Many people helped me in this project: Rodrigo Erazo, Carlos Hernán Muñoz, Andy Marshman, Wayne Golding, Peter Fargo, Andre Kuiper, Rolf Genster (German corrections), the rhCharts guy, Alwaysbusy's corner (gradient and other stuff), and all of request a demo.