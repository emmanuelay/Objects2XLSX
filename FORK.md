# Objects2XLSX, Block21 fork

A fork of [fatbobman/Objects2XLSX](https://github.com/fatbobman/Objects2XLSX) 1.3.2, used by My Wallet for its Excel export. It corrects what the export found wrong in the files 1.3.2 writes. Each fix is a separate commit on the `mywallet` branch, offered upstream as its own pull request.

| Change | Commit subject |
|---|---|
| Dates are converted by calendar date and clock time in the given time zone. 1.3.2 subtracted a constant that is only right in China, and ignored daylight saving. | fix: convert dates to Excel serials by calendar date and clock time |
| General is Excel's built-in format 0, rather than an undefined custom format 164. | fix: write General as Excel's built-in number format 0 |
| `CellStyle(numberFormat:)` and `NumberFormat.custom(_:)`, as the documentation already describes, so a column can be a date without a time or `#,##0.00`. | feat: let a cell style choose its number format |
| A missing number, date, percentage or boolean is a blank cell rather than an empty `<v></v>`. | fix: leave missing numbers, dates and booleans without a value |
| `docProps/app.xml` names the document properties' application and company, not the library. | fix: write the document properties' application and company to app.xml |

Releases are tagged `<upstream version>-mywallet.<n>`, e.g. `1.3.2-mywallet.1`. Modified files carry a notice, as the Apache License 2.0 requires; the license and NOTICE are unchanged.
