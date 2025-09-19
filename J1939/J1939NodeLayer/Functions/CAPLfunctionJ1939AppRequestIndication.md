[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939AppRequestIndication.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 NL](../CAPLfunctionsJ1939NLOverview.md) » J1939AppRequestIndication

# J1939AppRequestIndication (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
dword J1939AppRequestIndication( long ecuHandle, long source, long dest, long page, long pgNum );
```

## Description

This function indicates to the ECU that the "OnRequest" parameter group has been received. The application must respond appropriately (see specification).

It should be noted that this function is only called once for each logical ECU within a node when global PGs are received.

## Parameters

- **ecuHandle**: ECU handle
- **source**: source address
- **dest**: destination address
- **page**: data page bit
- **pgNum**: requested PGN

## Return Values

—

## Example

```c
dword J1939AppRequestIndication( LONG ecuHdl, LONG source, LONG dest, LONG page, LONG pgNum)
{
  /* user code */
  return 0;
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
