# diagGetDescriptionInformation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long diagGetDescriptionInformation (char field[], char buffer[], dword bufferLen); // form 1`
- `long diagGetDescriptionInformation (char ecuQualifier[], char field[], char buffer[], dword bufferLen); // form 2`

## Description

Returns information on a diagnostic description, as stored in the database file itself.

## Parameters

- **ecuQualifier**: Retrieves information for this diagnostic description. If not given, the currently selected target or description assigned to the ECU simulation is used.
- **field**: Value to retrieve. [DiagGetDescriptionVersion](CAPLfunctionDiagGetDescriptionVersion.md) returns the value for **Version**. Other possible values are:
  - **" " (empty string)**: A short overview is returned
  - **DatabaseFormat**: Database file type, e.g., "CDL", "ODX", ...
  - **DatabaseVersion**: Database file format version, e.g., "8.0.1100", "2.0.1"
  - **Manufacturer**: As stored in database, e.g., "Vector"
  - **Version**: Document version, e.g., "1.2"
  - **LastHistoryChange**: Last change history entry, e.g., "2015-02-25 Abc"
  - **SaveNumber**: As stored in database, e.g., "123"
  - **TemplateLabel**: As stored in database, e.g., "V7.1 A"
  - **TemplateSaveNumber**: As stored in database, e.g., "43"
- **buffer**: The value is written into this array.
- **bufferLen**: Capacity of the array

## Return Values

Number of characters written into the array, or [error code](../CAPLfunctionsDiagnosticsErrorCode.md). If a value is not defined in the database, **0** and an empty string are returned.

## Example

```c
char buffer[300];
DiagGetDescriptionInformation("ECU1", "", buffer, elcount(buffer));
write(buffer);
/* Example output:
Qualifier: ECU1
Name: ABCD2015
File: C:\Projects\2015\R123\ABCD.cdd
Manufacturer: Vector
Last history change: 2014-07-11 08:32:23+02:00
File version: 1.3 #132
Template version: 14.20.19 #1
*/
DiagSetTarget("ECU1");
DiagGetDescriptionVersion(buffer, elcount(buffer));
// returns "1.3"
```
