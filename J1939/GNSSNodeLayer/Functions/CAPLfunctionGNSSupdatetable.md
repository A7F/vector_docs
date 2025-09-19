[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSupdatetable.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [GNSS NL](../CAPLfunctionsGNSSNLOverview.md) » GNSSUpdateTable

# GNSSUpdateTable

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
dword GNSSUpdateTable();
```

## Description

Updates the network table.

The function deletes the content of the current table and initiates the Request PGN that was used to request Address Claiming. After that, the table is restructured. If a node is forced off the network by another node with the same address, it remains intact in the network table with a NULL address. The content of the table is not deleted until this function is called. It also initiates an update of the table. Nodes reporting with the NULL address are not accepted in this process.

## Parameters

—

## Return Values

[Error code](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

## Example

```c
GNSSUpdateTable();
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
