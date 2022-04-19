# Python Excel

## xlrd

```python
import xlrd

workbook = xlrd.open_workbook(filename="./<filename>.xlsx")
worksheet = workbook.sheet_by_index(0)
```

* Number of rows - ` worksheet.nrows`
* Cell value - `worksheet.cell_value(<row_i>, <col_j>)`

## xlwt

```python
import xlwt

destWb = xlwt.Workbook()
destWs = destWb.add_sheet('<sheetname>')
```

## xlutils

```python
import xlutils.copy insert copy

workbook = xlrd.open_workbook(filename="./<filename>.xlsx")
worksheet = workbook.sheet_by_index(0)

destWb = copy(workbook)
destWs = destWb.get_sheet(0)
```

* Write value - `destWs.write(<row_i>, <col_j>, <value>)`
* Save Excel - `destWb.save(<filename>)`

## Excel日期按String读取

```python
def dateToStr(excelDate):
	datetimeDate = xlrd.xldate_as_datetime(excelDate, 0)
	dateObj = datetimeDate.date()
	return dateObj.isoformat()
```