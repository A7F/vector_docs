[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetDescriptionVersion.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagGetDescriptionVersion

# diagGetDescriptionVersion

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `long diagGetDescriptionVersion (char buffer[], dword bufferLen);` // form 1
- `long diagGetDescriptionVersion (char ecuQualifier[], char buffer[], dword bufferLen);` // form 2

## Description

Returns information on a diagnostic description, as stored in the database file itself.

## Parameters

- **ecuQualifier**: Retrieves information for this diagnostic description. If not given, the currently selected target or description assigned to the ECU simulation is used.
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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)