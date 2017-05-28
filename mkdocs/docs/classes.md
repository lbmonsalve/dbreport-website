# Classes

## DBReport

### Properties 

### Methods

### Shared Properties

### Shared Methods 

### Constructors

### Class Constants

### Examples

Modify report:

```vb
Dim rpt As New DBReport
 
Dim f as FolderItem= SpecialFolder.Documents.Child("DBReport1.xml")
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

---
## DBReportPreview

---
## DBReportShared

