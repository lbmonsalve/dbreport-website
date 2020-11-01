# ChangeLog

1.4.7315

\* Add DBReport.RowSet (Api2 database support)

1.4.6820

\- Fix Align in MBSDynaPDF
\- Fix multiline preview
\- Chg DBReportPreview thumbnail

1.4.6611

\* Add RenderToPDFOnBackground to multiple PDF
\* Add RenderToPDFOnBackgroundCancel
\- Chg Threads.Priority to HighPriority
\- Fix DBReportPreview thumbnail blink

DBReportPreview, DBReportDesignerControl 1.4.6106

\- Disable DBReportPreview MouseWheel on MacOS.
\* Add DBReportPreview.PageMouseWheel event.
\* Add DBReportDesignerControl.PreviewPageMouseWheel event.

1.4.5612

\- Fix DBReport.PreferencesFile nil in xojoCloud

1.4.5511

\- Fix DarkMode issues

1.4.5308

\- Fix picture element when is parameter (#param)

1.4.5215

\* Add DBReport.WaterMark

1.4.5117

\- Fix mouseOver on element

1.4.5012

\- Fix picture.Backcolor, preview of roundRentangle

1.4.5003

\- Fix BackColor on label/field when align<> left.</br>
\- Fix AlignH, AlignV on picture element.

DBReportChart 0.0.4830

\- Fix JSONItem arrays error in 2018r1.

DBReportPreview 1.4.4829

\* Change showToolBar to False by default.

1.4.4618

\- Fix: unsupportedException in web apps</br>
\* Add: Web example

1.4.4407

\- Fix: band.PrintAgainWhenNewPage. in subgroups

1.4.4404

\* Add: band.PrintAgainWhenNewPage.

1.4.4201

\* Add: "64bit" to PDF producer info.

1.4.4115

\- Fix: Int32 cast for enum in 64-bit.

1.4.4001

\* Add: suport for print with SumatraPDF in Windows

1.4.3927

\- Fix: Scale when DPI<> 72 on r2017+.

1.4.3922

\- Fix: Picture field don't print in footer band.

1.4.3509

\* Add: DBReport.ParametersClear.</br>
\- Fix: copies on windows print dialog.</br>
\- Fix: Zoom control on mac works.

1.4.3316

\* Add: Preview HiDPI (test).</br>
\- Fix: drag'n drop on mac (recurrent v1.3.1122).

1.4.3227

\- Fix: Scanner don't read printed barcodes.

1.4.2916

\- Fix: KeyNotFoundException on average fn.

1.4.2913

\* Add: Element Average function.

1.4.2823

\* Add import for OnTargetReports on LoadXML(...).</br>
\* Add Changed Function.</br>
\* Add better encryption algorithm.</br>
\* Add support to CEF on formula editor, https://github.com/tempelmann/custom-editfield.

1.4.2819

\- Fixed: console issues.
\* Add SetForeColor, SetBackColor, SQLDateTime, TotalSeconds to formula.

1.4.2815

\- Fixed: Error on formula when element names has space.</br>
\* Add right-click on schema/parameters for deleted.</br>
\* Add drag&drop from schema to canvas.

1.4.2313

\- Fixed: Group delete.

1.4.2229

\* Generate subreports collections with SubReportAddInBand.

1.4.2226

\* Add MBSDynaPDF support.</br>
\* Constants kBarcodeEngine, kRenderEngineExcel, kRenderEnginePDF on DBReportShared module changed.

1.4.2201

\- Fixed "PM" string when fomat date between 12-13 hours.

1.4.1717

\* Add shared property DBReport.RecordSetEncoding.</br>
\- Fixed MSSQL double issue.

1.4.1428

\- Fixed values with EndOfLine in formula.

1.4.1427

\- Fixed multiline element cause bad behavior.</br>
\- Fixed subtotal on MacOS and Xojo 2014+ round problem.

1.4.1403

\- object exception when print with HotSpot element is enable; fixed.</br>
\- format of dates on GroupFooter fixed.</br>
\* Images resolution enhanced of PDF objs (barcode, rotateText, charts).

1.4.1211

\- "...more than one item with this name..." bug on 2014r3 fixed.</br>
\- Error on preview when the page # <> 1 fixed.</br>
\- Images on DBReportPDF preserve the resolution now.

1.4.1204

\* Add demo reports from sakila db.</br>
\* Add unit-test.</br>
\* Add BarcodeMBS support.</br>
\- Leyend on charts fixed

1.4.0917

\* Add order to print on columns.

1.4.0704

\* Add format on date field: ShortDate,LongDate,ShortTime,LongTime - thanks Wayne.</br>
\- Count issue fixed

1.4.0702

\- Calculation issue on formula in same band fixed.

1.4.0620

\* Add HotSpot areas to DBReportPreview control.</br>
\* Add Listbox property for using as recordset.</br>
\* Add support to barcode with Simbarcodes module.</br>
\* Change icons.</br>
\- Minor bugs fixed.

1.3.1804

\* Add FormatDateTime(stringDateSQLFormat, "format") function to Formula Editor.</br>
\* Calc height of element when change font size.</br>
\* Add new elements with last Font Size, height element.</br>
\- Fixed when fieldNumber of recordset are null.

1.3.1625

\- Calc function values when band is hide.

1.3.1616

\* Add format to Date/time values "[dmyhisDYHAwWzlF]" or "%+[dmyhisDYHAwWzlF]" Check http://php.net/manual/en/function.date.php.

1.3.1611

\* Add Field("fieldName"), TotalSeconds("FieldName") Parameter("ParamName") functions to Formula Editor.</br>
\* Add Sum, Subtotal Functions to labels elements.

1.3.1531

\* Add property DBReport.PictureQualityAllImagesPDF</br>
\- Show negative subtotals issue fixed.


1.3.1409

\- Some issues with subtotals on bands fixed.

1.3.1408

\* Edit property with 1 clic and use TAB, Shift-TAB, Up and Down arrows

1.3.1405

\- MemoryBlock error when Picture field is Nul, fixed.

1.3.1402

\- Some elements no show on designer, fixed.</br>
\- Weird scrollBars behavior when delete an element, fixed.

1.3.1311

\* Render to PDF with internal render.

1.3.1129

\* Label rotation implemented.</br>
\* Change DPI implemented.</br>
\- Now works secondary mouse button on Mac.

1.3.1125

\- Boolean mapping on RBScript fixed.

1.3.1122

\* New form to handle lines.</br>
\- Mac drag'n drop fixed.

1.3.1120

\- Delete band with subreports bug fixed.</br>
\- Copy and paste between subreports fixed.

1.3.1118

\* SubReports implemented.
\* New Constructors:DBReport(FolderItem, RecordSet), DBReport(String, RecordSet)</br>
\* Some methods on DBReportSubReport are deprecated, delete on future releases.</br>
\* Limits for elements implemented.</br>
\* Scale images now is proportional.</br>
\* Add Branding: DBReport.BrandName= "Your brand".

1.3.1017

\* Format date fields with user locale format.</br>
\- ODBC fixed bug.</br>
\- Print on thread disable on mac.</br>
\- Zoom with wheel on Mac disable.

1.3.1007

\* Register component implemented.</br>
\* Grid and SnapToGrid implemented.</br>
\* Print on thread implemented.</br>
\* Cache on preview +100 (settable) pages on disk.</br>
\* Propierties implemented.</br>
\* Translate to German thanks to Rolf Gengster (rgenster@genster.com).</br>
\- Changing size of element on MacOS fixed, others bugs fixed.

1.2.0907

\* Rename "DBReportDesingerControl.rbw" by "DBReportDesignerControl.rbw"</br>
\- Wrong Count function value fixed, fixed several bugs

1.2.0830:

\* Charts implemented, fixed several bugs.

1.2.0725:

\* SendBack implemented, fixed several bugs, new colors.</br>
\- Images deleted!, no more used.

1.2.0723:

\* Print group in new page, print element according to condition.

1.1.0115:

\* Parameters implemented; PrinterSettings and PrinterPOSDevice implemented.

1.1.0112:

\* Multiline in POS report implemented.</br>
\* Export/Import from designer implemented.</br>
\- Fix parcialy/ bug in Listbox 64+ columns.</br>
\* Show properties in Schema implemented.</br>
\* Save preferences implemented.

1.0.1220:

\* Measures units implemented.</br>
\* Columns implemented</br>
\* Select elements and move with arrows keys implemented.</br>
\* Show position in ruler implemented.

1.0.1130:

\* Formula editor implemented.</br>
\- Fixed bugs: Ctrl+C, Preview, goto N pag.

1.0.1128:

\* Dialog to print implemented.</br>
\* Print to POS implemented.</br>
\* Interface change: controls positions.

1.0.1123:

\- Fixed error preview control.</br>
\* Goto N page in Preview.

1.0.1112:

\* To set parameter don't need subreport reference, ej: rpt.Parameter("StartDate")= "01/01/2012"</br>
\* Color change on selected element, Repeat, Show 0, Ctrl+C y Ctrl+V.</br>
\* change preview buttons position.

\* Initial release