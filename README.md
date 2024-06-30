
Sub cal ()
    Dim wsl, ws2, ws3, ws4, ws5, ws6, ws7, ws8, ws9, ws10, ws11, ws12, ws13 As Worksheet
    Dim lastColumn, lastRow, BBGCol, SharesCol As Long 

    Set wsl = ThisWorkbook.Worksheets("Orders")
    ' Set ws2 = ThisWorkbook.Worksheets("New Zealand") 
    ' Set ws3 = ThisWorkbook.Worksheets("Australia") 
    Set ws4 = ThisWorkbook.Worksheets("Korea")
    Set ws5 = ThisWorkbook.Worksheets("Hong Kong") 
    set ws6 = ThisWorkbook.Worksheets("China") 
    ' Set ws7 = ThisWorkbook.Worksheets("Taiwan") 
    ' Set ws8 = ThisWorkbook.Worksheets("Singapore") 
    ' Set ws9 = ThisWorkbook.Worksheets("Malaysia")
    ' Set ws10 = ThisWorkbook.Worksheets("Philippines") 
    ' Set ws11 - ThisWorkbook.Worksheets("Thailand") 
    ' Set ws12 = ThisWorkbook.Worksheets("Indonesia") 
    ' Set ws13 = ThisWorkbook.Worksheets("India")

    windowLen = ws1.Cells(3, "B") 
    volCap =ws1.Cells(2, "B")
    SharesCol = Application.Match("Shares", ws1.Rows(5),0) 
    BBGCol = Application.Match("BBCode", ws1.Rows(5), 0)
    lastColumn = ws1.Cells(5, ws1.Columns.Count).End(xlToLeft).Column 
    lastRow = ws1.Cells(ws1.Rows.Count,5) .End(xUp).Row

    For i =5 To lastRow
        BBGCode = ws1.Cells(i, BBGCol).Value 
        If Right(BBGCode, 5)= "/F TB" Then
            ws1.Cells(i,BBGCol).Value = Left(BBGCode, Len (BBGCode) - 5) & Right (BBGCode,3) 
        End If 
    Next i

    ' wsl.Cells(5,BBGCol).AutoFilter Field:=BBGCol, Criterial:="=*NZ"
    ' ws1.Range (Cells(6,BBGCol), Cells(10000,BBGCol)).SpecialCells(xlCellTypeVisible).Copy
    ' ws2.Range("A3").PasteSpecial xlPasteValuesAndNumberFormats
    ' ws1.Range (Cells(6,SharesCol), Cells(10000,SharesCol)).SpecialCells(xlCellTypeVisible).Copy
    ' ws2.Range("E3").PasteSpecial xlPasteValuesAndNumberFormats
    ' ws1.Cells.AutoFilter

    ' wsl.Cells(5,BBGCol).AutoFilter Field:=BBGCol, Criterial:="=*AU"
    ' ws1.Range (Cells(6,BBGCol), Cells(10000,BBGCol)).SpecialCells(xlCellTypeVisible).Copy
    ' ws3.Range("A3").PasteSpecial xlPasteValuesAndNumberFormats
    ' ws1.Range (Cells(6,SharesCol), Cells(10000,SharesCol)).SpecialCells(xlCellTypeVisible).Copy
    ' ws3.Range("E3").PasteSpecial xlPasteValuesAndNumberFormats
    ' ws1.Cells.AutoFilter

    wsl.Cells(5,BBGCol).AutoFilter Field:=BBGCol, Criterial:="=*KS"
    ws1.Range (Cells(6,BBGCol), Cells(10000,BBGCol)).SpecialCells(xlCellTypeVisible).Copy
    ws4.Range("A3").PasteSpecial xlPasteValuesAndNumberFormats
    ws1.Range (Cells(6,SharesCol), Cells(10000,SharesCol)).SpecialCells(xlCellTypeVisible).Copy
    ws4.Range("E3").PasteSpecial xlPasteValuesAndNumberFormats
    ws1.Cells.AutoFilter

    wsl.Cells(5,BBGCol).AutoFilter Field:=BBGCol, Criterial:="=*HK"
    ws1.Range (Cells (6,BBGCol), cells (10000, BBGCol)).SpecialCells(xlCellTypeVisible).Copy 
    ws5.Range("A3").PasteSpecial xlPasteValuesAndNumberFormats
    ws1.Range (Cells(6,SharesCol),Cells(10000,SharesCol)).SpecialCells(xlCe11TypeVisible).Copy 
    ws5.Range("E3").PasteSpecial xlPasteValuesAndNumberFormats
    ws1.Cells.AutoFilter

    wsl.Cells(5, BBGCol).AutoFilter Field:=BBGCol, Criteria1:="=*C1", Operator:=xlOr, Criteria2:="=*C2"
    ws1.Range(Cells(6, BBGCol), Cells(10000, BBGCol)).SpecialCells(xlCellTypeVisible).Copy
    ws6.Range("A3").PasteSpecial xlPasteValuesAndNumberFormats
    ws1.Range(Cells(6, SharesCol), Cells(10000, SharesCol)).SpecialCells(xlCellTypeVisible).Copy
    ws6.Range("E3").PasteSpecial xlPasteValuesAndNumberFormats
    ws1.Cells.AutoFilter

    'wsl.Cells(5, BBGCol).AutoFilter Field:=BBGCol, Criteria1:="=*TW"


End Sub
