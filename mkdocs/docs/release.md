# Release notes

1.4.3509

\* Add: DBReport.ParametersClear.
\- Fix: copies on windows print dialog.
\- Fix: Zoom control on mac works.

1.4.3316

\* Add: Preview HiDPI (test).
\- Fix: drag'n drop on mac (recurrent v1.3.1122).

1.4.3227

\- Fix: Scanner don't read printed barcodes.

1.4.2916

\- Fix: KeyNotFoundException on average fn.

1.4.2913

\* Add: Element Average function.

1.4.2823

\* Add import for OnTargetReports on LoadXML(...).
\* Add Changed Function.
\* Add better encryption algorithm.
\* Add support to CEF on formula editor, https://github.com/tempelmann/custom-editfield.

1.4.2819

\- Fixed: console issues.
\* Add SetForeColor, SetBackColor, SQLDateTime, TotalSeconds to formula.

1.4.2815

\- Fixed: Error on formula when element names has space.
\* Add right-click on schema/parameters for deleted.
\* Add drag&drop from schema to canvas.

1.4.2313

\- Fixed: Group delete.

1.4.2229

\* Generate subreports collections with SubReportAddInBand.

1.4.2226

\* Add MBSDynaPDF support.
\* Constants kBarcodeEngine, kRenderEngineExcel, kRenderEnginePDF on DBReportShared module changed.

1.4.2201

\- Fixed "PM" string when fomat date between 12-13 hours.

1.4.1717

\* Add shared property DBReport.RecordSetEncoding.
\- Fixed MSSQL double issue.

1.4.1428

\- Fixed values with EndOfLine in formula.

1.4.1427

\- Fixed multiline element cause bad behavior.
\- Fixed subtotal on MacOS and Xojo 2014+ round problem.

1.4.1403

\- object exception when print with HotSpot element is enable; fixed.
\- format of dates on GroupFooter fixed.
\* Images resolution enhanced of PDF objs (barcode, rotateText, charts).

1.4.1211

\- "...more than one item with this name..." bug on 2014r3 fixed.
\- Error on preview when the page # <> 1 fixed.
\- Images on DBReportPDF preserve the resolution now.

1.4.1204

\* Add demo reports from sakila db.
\* Add unit-test.
\* Add BarcodeMBS support.
\- Leyend on charts fixed

1.4.0917

\* Add order to print on columns.

1.4.0704

\* Add format on date field: ShortDate,LongDate,ShortTime,LongTime - thanks Wayne.
\- Count issue fixed

1.4.0702

\- Calculation issue on formula in same band fixed.

1.4.0620

\* Add HotSpot areas to DBReportPreview control.
\* Add Listbox property for using as recordset.
\* Add support to barcode with Simbarcodes module.
\* Change icons.
\- Minor bugs fixed.

1.3.1804

\* Add FormatDateTime(stringDateSQLFormat, "format") function to Formula Editor.
\* Calc height of element when change font size.
\* Add new elements with last Font Size, height element.
\- Fixed when fieldNumber of recordset are null.

1.3.1625

\- Calc function values when band is hide.

1.3.1616

\* Add format to Date/time values "[dmyhisDYHAwWzlF]" or "%+[dmyhisDYHAwWzlF]" Check http://php.net/manual/en/function.date.php.

1.3.1611

\* Add Field("fieldName"), TotalSeconds("FieldName") Parameter("ParamName") functions to Formula Editor.
\* Add Sum, Subtotal Functions to labels elements.

1.3.1531

\* Add property DBReport.PictureQualityAllImagesPDF
\- Show negative subtotals issue fixed.


1.3.1409

\- Some issues with subtotals on bands fixed.

1.3.1408

\* Edit property with 1 clic and use TAB, Shift-TAB, Up and Down arrows

1.3.1405

\- MemoryBlock error when Picture field is Nul, fixed.

1.3.1402

\- Some elements no show on designer, fixed.
\- Weird scrollBars behavior when delete an element, fixed.

1.3.1311

\* Render to PDF with internal render.

1.3.1129

\* Label rotation implemented.
\* Change DPI implemented.
\- Now works secondary mouse button on Mac.

1.3.1125

\- Boolean mapping on RBScript fixed.

1.3.1122

\* New form to handle lines.
\- Mac drag'n drop fixed.

1.3.1120

\- Delete band with subreports bug fixed.
\- Copy and paste between subreports fixed.

1.3.1118

\* SubReports implemented.
\* New Constructors:DBReport(FolderItem, RecordSet), DBReport(String, RecordSet)
\* Some methods on DBReportSubReport are deprecated, delete on future releases.
\* Limits for elements implemented.
\* Scale images now is proportional.
\* Add Branding: DBReport.BrandName= "Your brand".

1.3.1017

\* Format date fields with user locale format.
\- ODBC fixed bug.
\- Print on thread disable on mac.
\- Zoom with wheel on Mac disable.

1.3.1007

\* Register component implemented.
\* Grid and SnapToGrid implemented.
\* Print on thread implemented.
\* Cache on preview +100 (settable) pages on disk.
\* Propierties implemented.
\* Translate to German thanks to Rolf Gengster (rgenster@genster.com).
\- Changing size of element on MacOS fixed, others bugs fixed.

1.2.0907

\* Rename "DBReportDesingerControl.rbw" by "DBReportDesignerControl.rbw"
\- Wrong Count function value fixed, fixed several bugs

1.2.0830:

\* Charts implemented, fixed several bugs.

1.2.0725:

\* SendBack implemented, fixed several bugs, new colors.
\- Images deleted!, no more used.

1.2.0723:

\* Print group in new page, print element according to condition.

1.1.0115:

\* Parameters implemented; PrinterSettings and PrinterPOSDevice implemented.

1.1.0112:

\* Multiline in POS report implemented.
\* Export/Import from designer implemented.
\- Fix parcialy/ bug in Listbox 64+ columns.
\* Show properties in Schema implemented.
\* Save preferences implemented.

1.0.1220:

\* Measures units implemented.
\* Columns implemented
\* Select elements and move with arrows keys implemented.
\* Show position in ruler implemented.

1.0.1130:

\* Formula editor implemented.
\- Fixed bugs: Ctrl+C, Preview, goto N pag.

1.0.1128:

\* Dialog to print implemented.
\* Print to POS implemented.
\* Interface change: controls positions.

1.0.1123:

\- Fixed error preview control.
\* Goto N page in Preview.

1.0.1112:

\* To set parameter don't need subreport reference, ej: rpt.Parameter("StartDate")= "01/01/2012"
\* Color change on selected element, Repeat, Show 0, Ctrl+C y Ctrl+V.
\* change preview buttons position.

\* Initial release