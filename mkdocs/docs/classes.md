# Classes

## DBReport

Used to print or render reports. 

### Properties 

||||
||||
|[CacheInRecords](#CacheInRecords)|[ListBox](#ListBox)|[Name](#Name)|
|[PictureQualityAllImagesPDF](#PictureQualityAllImagesPDF)|[PrinterDialog](#PrinterDialog)|[PrinterSettings](#PrinterSettings)|
|[RecordSet](#RecordSet)|[SearchHighlightColor](#SearchHighlightColor)|[UID](#UID)|

#### CacheInRecords
```vb
rpt.CacheInRecords= 500
```
**Integer** - Records cached in memory, default= 1000. 

DBReport cached pictures of pages in memory for CacheInRecords number, after that, pictures are saved in temporary files. 

</br>
#### ListBox
```vb
rpt.ListBox= myListbox
' or
myListbox= rpt.Listbox
```
**ListBox** - Set or get the listbox, use as recordset, the columns heading is used as field name. 

</br>
#### Name
```vb
rpt.Name= "Customers list"
' or
StringVariable= rpt.Name
```
**String** - Used for set or get the name of report, appears on title of window designer. 

</br>
#### PictureQualityAllImagesPDF
```vb
rpt.PictureQualityAllImagesPDF= Picture.QualityMedium
' Or
rpt.PictureQualityAllImagesPDF= 25 // low quality
```
**Integer** - Set the quality for all images on PDF file, see [JPEG quality](http://docs.xojo.com/index.php/Picture).

</br>
#### PrinterDialog
```vb
rpt.PrinterDialog= False
```
**Boolean** - If shows printer dialog before print. by default is true.

</br>
#### PrinterSettings
```vb
rpt.PrinterSettings= PageSetup.SetupString
```
**String** - populate PrinterSetup options. see [SetupString](http://docs.xojo.com/index.php/PrinterSetup.SetupString)

</br>
#### RecordSet
```vb
rpt.RecordSet= db.SQLSelect("SELECT * FROM sqlite_master")
' or
Dim rs As Recordset= rpt.RecordSet
```
**Recordset** - Set or get recordset object. 

</br>
#### SearchHighlightColor
```vb
rpt.SearchHighlightColor= &cFFDFDF7F
```
**Color** - Set the color for Highlight when search on Preview. Default= &cFFFF007F 

</br>
#### UID
```vb
StringVariable= rpt.UID
```
**String** - Get the unique identification of report. 

### Methods

||||
||||
|[Changed](#Changed)|[Designer](#Designer)|[GetXML](#GetXML)|
|[LoadXML](#LoadXML)|[Page](#Page)|[Parameter](#Parameter)|
|[Print](#Print)|[PrintQuick](#PrintQuick)|[Prop](#Prop)|
|[PropCount](#PropCount)|[RenderToPDF](#RenderToPDF)|[SaveXML](#SaveXML)|
|[SubReport](#SubReport)|[SubReportAdd](#SubReportAdd)|[SubReportDel](#SubReportDel)|
|[SubReportsClear](#SubReportsClear)|||

#### Changed
```vb
If rpt.Changed Then
	MsgBox "Changed!"
End If
```
**Boolean** - If report has changed (after use Designer).

</br>
#### Designer
```vb
rpt.Designer(showModal As Boolean = True)
```

```vb
rpt.Designer(settings As String)
```
Shows DBReportDesignerWindow window aka **Designer** window.

**Example:**
```vb
rpt.Designer("{""ShowExpImpBtn"": True, ""ShowUpdateBtn"": True}")
```
The settings parameter is a JSON string eg. **ShowExpImpBtn:** shows ExportImport button, **ShowUpdateBtn:** shows Update button 

</br>
#### GetXML
```vb
StringVariable= rpt.GetXML
```
**String** - Get XML definition as string. 

</br>
#### LoadXML
```vb
rpt.LoadXML(f As FolderItem)
```

```vb
rpt.LoadXML(str As String)
```
Load report definition. 

</br>
#### Page
```vb
rpt.Page(ByRef PageNum As Integer, Scale As Double = 1, Optional Search As String = "", _
    Optional CachePages As Boolean = False, Optional PageBackColor As Color = &cFCFCFC00)
```
**Picture** - Returns a Picture of page.

PageNum is a number of page rendered, if the number is greater PageNum is changed to last page. Scale is the scale of picture. Search is a string to search and highlighted. CachePages cached pictures if you need get the picture again. PageBackColor is the backColor of picture. 

</br>
#### Parameter
```vb
rpt.Parameter(Name As String, Assigns Value As Variant)
```

```vb
rpt.Parameter(Name As String) As Variant
```
Set or get parameters to use in report. Must be setting before Print or Design.

**Example:**
```vb
rpt.Parameter("CompanyName")= "Acme Inc."
rpt.Parameter("CompanyLogo")= pictureVariable
```

</br>
#### Print
```vb
rpt.Print
```
Print report. 

</br>
#### PrintQuick
```vb
rpt.PrintQuick(ShowDialog As Boolean = False)
```
Print without definition. Print low numbers of columns.

**Example:**
```vb
Dim rpt As New DBReport
rpt.RecordSet= rs
rpt.PrintQuick
```

</br>
#### Prop
```vb
rpt.Prop(Idx As Integer) As String
```

```vb
rpt.Prop(Name As String) As String
```

```vb
rpt.Prop(Name As String, Assigns Value As String)
```
Set or get properties of report. 

</br>
#### PropCount
```vb
rpt.PropCount() As Integer
```
Get the numbers or properties. 

</br>
#### RenderToPDF
```vb
rpt.RenderToPDF(f As FolderItem)
```
Create a PDF file of report.

</br>
#### SaveXML
```vb
rpt.SaveXML(f As FolderItem, pretty As Boolean = False)
```
Create a XML file of definition. 

</br>
#### SubReport
```vb
rpt.SubReport(Idx As Integer) As DBReportSubReport
```

```vb
rpt.SubReport(Name As String) As DBReportSubReport
```
Get subreport. Idx start in zero. 

</br>
#### SubReportAdd
```vb
rpt.SubReportAdd(Rpt As DBReportSubReport)
```
Add subreport to report. 

</br>
#### SubReportDel
```vb
rpt.SubReportDel(Name As String)
```
Delete subreport by name.

</br>
#### SubReportsClear
```vb
rpt.SubReportsClear
```
Delete all subreports. 

### Shared Properties

||||
||||
|[BrandName](#BrandName)|[Errors](#Errors)|[ErrorsCount](#ErrorsCount)|
|[PassCode](#PassCode)|[PDFObj](#PDFObj)|[PDFOptions](#PDFOptions)|
|[PictureSaveInDefinition](#PictureSaveInDefinition)|[PreferencesFile](#PreferencesFile)|[RecordSetEncoding](#RecordSetEncoding)|
|[Register](#Register)|||

#### BrandName
```vb
DBReport.BrandName= "Your_Brand"
```
**String** - Change DBReport brand for you wish.

</br>
#### Errors
```vb
StringVariable= DBReport.Errors
```
**String** - Gets a string with all errors (if any) of report. 

</br>
#### ErrorsCount
```vb
IntegerVariable= DBReport.ErrorsCount
```
**Integer** - Gets the numbers of errors of report. 

</br>
#### PassCode
```vb
DBReport.PassCode= "your pass code"
```
**String** - Pass code used for encrypt DataExplorer data

</br>
#### PDFObj
```vb
Dim pdf As New DynaPDFMBS // your code
pdf.SetLicenseKey "Starter" // your code
' set other pdf options like AddFontSearchPath

' add this code 
DBReport.PDFObj= pdf // to reuse this object 
```
**DynaPDFMBS** - Used for store MBSDynaPDF plugin object.

</br>
#### PDFOptions
```vb
DBReport.PDFOptions.Value("Codepage")= DynaPDFMBS.kcpUnicode // change codepage 
```
**Dictionary** - Used for PDF settings.

</br>
#### PictureSaveInDefinition
```vb
DBReport.PictureSaveInDefinition= False
```
**Boolean** - Save picture data **in** definition File (default: True).

</br>
#### PreferencesFile
```vb
DBReport.PreferencesFile= SpecialFolder.ApplicationData.Child("yourfile")
```
**FolderItem** - Set preferences folderItem file.

</br>
#### RecordSetEncoding
```vb
DBReport.RecordSetEncoding= Encodings.ASCII
```
**TextEncoding** - Set encodings for recordSet.

</br>
#### Register
```vb
DBReport.Register= "Your_register_code"
```
**String** - Set register code.

### Shared Methods 

||||
||||
|[DecryptString](#DecryptString)|[EncryptString](#EncryptString)|[PrintOnBackground](#PrintOnBackground)|
|[PrintOnBackgroundCurrentPageNumber](#PrintOnBackgroundCurrentPageNumber)|[Registered](#Registered)|[RenderToPDFOnBackground](#RenderToPDFOnBackground)|
|[RenderToPDFOnBackgroundCurrentPageNumber](#RenderToPDFOnBackgroundCurrentPageNumber)|||

#### DecryptString
```vb
DBReport.DecryptString(Str As String) As String
```
**String** - Get a string "decripted", well is more like obfuscate. You can use for gets sensitive properties in report definition. 

**Example:**
```vb
username= DBReport.DecryptString(rpt.Prop("username"))
```

</br>
#### EncryptString
```vb
DBReport.EncryptString(Str As String) As String
```
**String** - Get a string "encripted", well is more like obfuscate. You can use for save sensitive properties in report definition. 

**Example:**
```vb
rpt.Prop("username")= DBReport.EncryptString(username)
```

</br>
#### PrintOnBackground
```vb
DBReport.PrintOnBackground() As Boolean
```
Gets True if are printing the report in background. Used for not close app before print thread is finished. 

**Example:**
```vb
Function CancelClose(appQuitting as Boolean) As Boolean
  If DBReport.PrintOnBackground Then
    MsgBox "Printing..."
    Return True
  End
End Function
```

```vb
DBReport.PrintOnBackground(Rpt As DBReport, Priority As Integer = Thread.LowestPriority)
```
Print a report on background.

**Example:**
```vb
Dim rpt As New DBReport(f, rs)
 
DBReport.PrintOnBackground rpt
```

</br>
#### PrintOnBackgroundCurrentPageNumber
```vb
DBReport.PrintOnBackgroundCurrentPageNumber() As Integer
```
Gets current page number printed in background. Used for feedback.

**Example:**
```vb
System.DebugLog Str(DBReport.PrintOnBackgroundCurrentPageNumber)
```

</br>
#### Registered
```vb
DBReport.Registered() As Boolean
```
Gets True if DBReport is registered. 

</br>
#### RenderToPDFOnBackground
```vb
DBReport.RenderToPDFOnBackground() As Boolean
```
Gets True if are render the report in background. Used for not close app before print thread is finished. 

**Example:**
```vb
Function CancelClose(appQuitting as Boolean) As Boolean
  If DBReport.RenderToPDFOnBackground Then
    MsgBox "REnder to PDF..."
    Return True
  End
End Function
```

```vb
DBReport.RenderToPDFOnBackground(Rpt As DBReport, f As FolderItem, title As String = "", author As String = "", _
subject As String = "", keywords As String = "", Priority As Integer = Thread.LowestPriority)
```
Render to PDF a report on background. 

**Example:**
```vb
Dim rpt As New DBReport(f, rs)
Dim f As FolderItem= SpecialFolder.Documents.Child("DBReport.xml")
 
DBReport.RenderToPDFOnBackground rpt, f, "My title", "My author", "My subject", "My keywords"
```

</br>
#### RenderToPDFOnBackgroundCurrentPageNumber
```vb
DBReport.RenderToPDFOnBackgroundCurrentPageNumber() As Integer
```
Gets current page number rendered in background. Used for feedback. 

**Example:**
```vb
System.DebugLog Str(DBReport.RenderToPDFOnBackgroundCurrentPageNumber)
```

### Constructors

#### DBReport.Constructor(rpt As DBReport)
```vb
DBReport.Constructor(rpt As DBReport)
```
Create a new report based in other (Copy constructor). 

**Example:**
```vb
Dim rpt As DBReport
'...
Dim rpt1 As New DBReport(rpt)
```

</br>
#### DBReport.Constructor(f As FolderItem)
```vb
DBReport.Constructor(f As FolderItem)
```
Create a report with a file definition.  

**Example:**
```vb
Dim rpt As New DBReport(SpecialFolder.Documents.Child("Template.xml"))
```

</br>
#### DBReport.Constructor(f As FolderItem, rs As RecordSet)
```vb
DBReport.Constructor(f As FolderItem, rs As RecordSet)
```
Create a report with file definition and recordset.  

**Example:**
```vb
Dim f As FolderItem= SpecialFolder.Documents.Child("MyReport.xml")
Dim rs As RecordSet= App.Db.SQLSelect("SELECT * FROM users")
 
Dim rpt As DBReport(f, rs)
```

</br>
#### DBReport.Constructor(str As String)
```vb
DBReport.Constructor(str As String)
```
Create a report with a string as definition. 

**Example:**
```vb
Dim rpt As New DBReport(kReportConstant)
```

</br>
#### DBReport.Constructor(str As String, rs As RecordSet)
```vb
DBReport.Constructor(str As String, rs As RecordSet)
```
Create a report with string as definition and recordset. 

**Example:**
```vb
Dim rs As RecordSet= App.Db.SQLSelect("SELECT * FROM users")
 
Dim rpt As DBReport(kReportDef, rs)
```

### Class Constants

|Name|Type|Values|
||||
|Version|String|ie. 1.4.4407|
|ReportColumnsOrder|Integer|LeftToRightThenDown=1</br>DownThenLeftToRight=2|
|ReportUnits|Integer|Pixels=1</br>Milimeters=2</br>Inches=3|

### Examples

Modify report:

```vb
Dim f as FolderItem= SpecialFolder.Documents.Child("DBReport1.xml")

Dim rpt As New DBReport
rpt.LoadXML f
rpt.RecordSet= rs // rs RecordSet must be exist
rpt.Designer
rpt.SaveXML(f)
``` 

or

```vb
Dim rpt As New DBReport
 
rpt.LoadXML(StringVariable)
rpt.RecordSet= rs // rs RecordSet must be exist
rpt.Designer
StringVariable= rpt.GetXML()
```

Printe report:

```vb
Dim f as FolderItem= SpecialFolder.Documents.Child("DBReport1.xml")
 
Dim rpt As New DBReport(f, rs) // rs RecordSet must be exist
rpt.Print
```

---
## DBReportDesignerControl

Used to embed in a Window or in another control. 

### Events

|||
|||
|[NameChange](#NameChange)|[Update](#Update)|

#### NameChange
```vb
DBReportDesignerControl1.NameChange()
```
Fires when the name of the report property has changed.

</br>
#### Update 
```vb
DBReportDesignerControl.Update()
```
Fires when click on **Update** button. 

### Methods

||||
||||
|[GetReport](#GetReport)|[PreferencesLoad](#PreferencesLoad)|[PreferencesSave](#PreferencesSave)|
|[Report](#Report)|||

#### GetReport 
```vb
DBReportDesignerControl.GetReport() As DBReport
```
Gets the report object. 

</br>
#### PreferencesLoad 
```vb
DBReportDesignerControl.PreferencesLoad(Win As DBReportDesignerWindow)
```
Load preferences and apply to window. 

</br>
#### PreferencesSave 
```vb
DBReportDesignerControl.PreferencesSave()
```
Save preferences.

</br>
#### Report 
```vb
DBReportDesignerControl.Report(rpt As DBReport)
```
Set report to control.

### Constants

|Name|Type|Values|
||||
|Version|String|1.4.4407|

---
## DBReportPreview

Used to embed in a Window or in another control. 

### Events

||||
||||
|[Action](#Action)|[PageFinished](#PageFinished)||

#### Action
```vb
DBReportPreview.Action(element As String, value As String, reportName As String, subReportName As String)
```
Fires when HotSpot is clicked. You can handle inspecting string variables. 

</br>
#### PageFinished
```vb
DBReportPreview.PageFinished()
```
Fires when the page is shows. 

### Properties

||||
||||
|[HotSpotEnable](#HotSpotEnable )|[ShowToolBar](#ShowToolBar)||

#### HotSpotEnable
```vb
DBReportPreview1.HotSpotEnable= True
```
**Boolean** - Set if hotSpots are enabled, default= False. 

</br>
#### ShowToolBar
```vb
DBReportPreview1.ShowToolBar= False
```
**Boolean** - Set if toolBar are shows, default= True.

### Methods

||||
||||
|[CurrentPage](#CurrentPage)|[MoveFirstPage](#MoveFirstPage)|[MoveLastPage](#MoveLastPage)|
|[MoveNextPage](#MoveNextPage)|[MovePreviousPage](#MovePreviousPage)|[MoveToPage](#MoveToPage)|
|[Print](#Print_1)|[Report](#Report)|[ShowSearchPanel](#ShowSearchPanel)|

#### CurrentPage
```vb
DBReportPreview.CurrentPage() As Integer
```
Return current page number. 

</br>
#### MoveFirstPage
```vb
DBReportPreview.MoveFirstPage()
```
Move to first page and shows it. 

</br>
#### MoveLastPage
```vb
DBReportPreview.MoveLastPage()
```
Move to last page and shows it.

</br>
#### MoveNextPage
```vb
DBReportPreview.MoveNextPage()
```
Move to next page and shows it. 

</br>
#### MovePreviousPage
```vb
DBReportPreview.MovePreviousPage()
```
Move to previous page and shows it. 

</br>
#### MoveToPage
```vb
DBReportPreview.MoveToPage(nPage As Integer)
```
Move to nPage number and shows it. 

</br>
#### Print
```vb
DBReportPreview.Print()
```
Print report.

</br>
#### Report
```vb
DBReportPreview.Report(rpt As DBReport, SearchPanel As Boolean = False, CacheInRecords As Integer = 1000)
```
Set report to preview. 

</br>
#### ShowSearchPanel
```vb
DBReportPreview.ShowSearchPanel()
```
Shows/hide the searchPanel.

### Constants

|Name|Type|Values|
||||
|Version|String|1.4.4407|

---
## DBReportShared

Used for setting third-party products.

### Constants

|Name|Type|Notes|
||||
|kBarcodeEngine|String|Set to "MBSBarcode" to use plugin, default= "Simbarcodes"|
|kConnectionMBSSQL|Boolean|Use MBSQL plugin in DataExplorer, default= False|
|kConnectionMSSQL|Boolean|Use MSSQL plugin in DataExplorer, default= False|
|kConnectionMySQL|Boolean|Use MySQL plugin in DataExplorer, default= True|
|kConnectionODBC|Boolean|Use ODBC plugin in DataExplorer, default= False|
|kConnectionOracle|Boolean|Use Oracle plugin in DataExplorer, default= False|
|kConnectionPostgres|Boolean|Use Postgres plugin in DataExplorer, default= True|
|kConnectionSQLite|Boolean|Use SQLite plugin in DataExplorer, default= True|
|kConnectionWeb|Boolean|Use HTTP in DataExplorer, default= True|
|kEditSyntaxHighlightEngine|String|Use CEF (custom-editfield) set "CEF", default=""|
|kEncryptionEngine|String|Use MBSEncryption plugin set "MBS", default= ""|
|kForceEncryptBefore2014|Boolean|Used REalStudio encryption, default= False|
|kRenderEnginePDF|String|Set to "MBSDynaPDF" to use plugin, default= "DBReportPDF"|
|kScreenShotEngine|String|Use MBSPicture set "ScreenshotMBS", default="ScreenShot"|
|kzlibPath|String|Set the path for zlib shared library|

### Notes

If you use MBSBarcode plugin, You can delete the Simbarcodes file.

To use MBSDynaPDF plugin:

1. Change DBReportShared.kRenderEnginePDF constant to "MBSDynaPDF".
2. Add next code after SetLicense, ie:

```vb
Dim pdf As New DynaPDFMBS // your code
pdf.SetLicenseKey "Starter" // your code
' set other pdf options like AddFontSearchPath
 
' add this code 
DBReport.PDFObj= pdf // to reuse this object 
 
' JUST IF YOU NEED CHANGE default options, add next code: 
'DBReport.PDFOptions.Value("Codepage")= DynaPDFMBS.kcpUnicode // change codepage 
'DBReport.PDFOptions.Value("EmbedFonts")= False // not embed fonts
```
You can delete DBReportPDF* files and zlib1.dll from the project. 