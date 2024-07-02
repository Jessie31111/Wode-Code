Sub ProcessData()
    Dim ws As Worksheet
    Set ws = ThisWorkbook.Worksheets("Sheet1") '替换为您的工作表名称
    
    Dim lastRow As Long
    lastRow = ws.Cells(ws.Rows.Count, "A").End(xlUp).Row '假设数据在第一列
    
    Dim dict As Object
    Set dict = CreateObject("Scripting.Dictionary")
    
    Dim i As Long
    For i = lastRow To 2 Step -1 '从最后一行往上遍历，忽略标题行
        Dim bbCode As String
        Dim side As String
        Dim sharesVol As Double
        
        bbCode = ws.Cells(i, 1).Value '假设BBCode在第一列
        side = ws.Cells(i, 2).Value '假设Side在第二列
        sharesVol = ws.Cells(i, 3).Value '假设Shares Vol在第三列
        
        If Not dict.Exists(bbCode) Then
            dict.Add bbCode, Array(side, sharesVol)
        Else
            Dim existingData As Variant
            existingData = dict(bbCode)
            
            Dim existingSide As String
            existingSide = existingData(0)
            
            Dim existingSharesVol As Double
            existingSharesVol = existingData(1)
            
            If existingSide = side Then
                dict(bbCode) = Array(existingSide, existingSharesVol + sharesVol)
            Else
                dict(bbCode) = Array(existingSide, existingSharesVol - sharesVol)
            End If
        End If
    Next i
    
    '清空原来的数据
    ws.Range("A2:C" & lastRow).ClearContents
    
    '将处理后的数据写回原始位置
    Dim outputRow As Long
    outputRow = 2
    For Each bbCode In dict.keys
        Dim data As Variant
        data = dict(bbCode)
        
        ws.Cells(outputRow, 1).Value = bbCode
        ws.Cells(outputRow, 2).Value = data(0)
        ws.Cells(outputRow, 3).Value = data(1)
        
        outputRow = outputRow + 1
    Next bbCode
    
    Set dict = Nothing
End Sub