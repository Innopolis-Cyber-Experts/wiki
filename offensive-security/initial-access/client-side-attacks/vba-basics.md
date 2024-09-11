# VBA Basics

{% embed url="https://learn.microsoft.com/en-us/office/vba/api/overview/word" %}

## Tips

* Use `Ctrl+G` to show Debug console

## Procedure

Procedures do not return values

```visual-basic
Sub ProcName()
	...
End Sub
```

## Function

Functions return values

```vba
Function GetAgePhrase(ByVal age As Integer) As String
    If age > 60 Then Return "Senior"
    If age > 40 Then Return "Middle-aged"
    If age > 20 Then Return "Adult"
    If age > 12 Then Return "Teen-aged"
    If age > 4 Then Return "School-aged"
    If age > 1 Then Return "Toddler"
    Return "Infant"
End Function
```

## Conditions

```vba
If selection = "A1" Then
	Console.WriteLine("7up")
ElseIf selection = "A2" Then
	Console.WriteLine("fanta")
Else
	Console.WriteLine("Sorry, I don't have any " + selection)
End If
```

## String operations

### Search substring

Method 1:

```vba
If InStr(1, "Hello World", "Hello W") = 1 Then
    MsgBox "Yep, this string begins with Hello W!"
End If
```

Method 2:

```vbnet
If "Hello World" Like "Hello W*" Then
    MsgBox "Yep, this string begins with Hello W!"
End If
```

## Execute shell command

{% embed url="https://learn.microsoft.com/en-us/office/vba/language/reference/user-interface-help/shell-constants" %}

```vba
Shell("C:\WINDOWS\NOTEPAD.EXE", 1) 
```
