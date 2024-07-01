Sub CalculateEntireWorkbook()
    Dim wb As Workbook
    Set wb = ThisWorkbook ' 当前工作簿
    
    Application.Calculation = xlCalculationManual ' 将计算模式设置为手动
    
    ' 循环计算工作簿中的每个工作表
    Dim ws As Worksheet
    For Each ws In wb.Worksheets
        ws.Calculate
    Next ws
    
    Application.Calculation = xlCalculationAutomatic ' 将计算模式恢复为自动
End Sub