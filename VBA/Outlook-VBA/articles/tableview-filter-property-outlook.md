---
title: TableView.Filter Property (Outlook)
keywords: vbaol11.chm2516
f1_keywords:
- vbaol11.chm2516
ms.prod: outlook
api_name:
- Outlook.TableView.Filter
ms.assetid: 7e65e578-5f0c-d875-608c-cefe9bc1b55b
ms.date: 06/08/2017
---


# TableView.Filter Property (Outlook)

Returns or sets a  **String** value that represents the filter for a view. Read/write.


## Syntax

 _expression_ . **Filter**

 _expression_ A variable that represents a **TableView** object.


## Remarks

The value of this property is a string, in DAV Searching and Locating (DASL) syntax, that represents the current filter for the view. For more information about using DASL syntax to filter items in a view, see [Filtering Items](http://msdn.microsoft.com/library/4038e042-1b07-5d18-18b0-c2b58c9c42da%28Office.15%29.aspx).


## Example

The following Visual Basic for Applications (VBA) example obtains a  **[View](view-object-outlook.md)** object by using the **[CurrentView](explorer-currentview-property-outlook.md)** property of the **[Explorer](explorer-object-outlook.md)** object, then sets the **[Filter](view-filter-property-outlook.md)** property of the **View** object to display only those Outlook items that were received last week.


```vb
Private Sub FilterViewToLastWeek() 
 
 Dim objView As View 
 
 
 
 ' Obtain a View object reference to the current view. 
 
 Set objView = Application.ActiveExplorer.CurrentView 
 
 
 
 ' Set a DASL filter string, using a DASL macro, to show 
 
 ' only those items that were received last week. 
 
 objView.Filter = "%lastweek(""urn:schemas:httpmail:datereceived"")%" 
 
 
 
 ' Save and apply the view. 
 
 objView.Save 
 
 objView.Apply 
 
End Sub
```


## See also


#### Concepts


[TableView Object](tableview-object-outlook.md)

