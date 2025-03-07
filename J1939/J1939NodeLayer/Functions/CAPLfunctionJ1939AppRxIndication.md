[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939AppRxIndication.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 NL](../CAPLfunctionsJ1939NLOverview.md) » J1939AppRxIndication

# J1939AppRxIndication (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
dword J1939AppRxIndication( long ecuHandle, long srcAddr, long dstAddr, long length, long pgnum );
```

## Description

The callback function indicates to the user that a parameter group has been received. It is not possible in CAPL to receive PG data through a callback function. For this reason, the data must be explicitly requested within the callback function with [J1939GetRxData()](CAPLfunctionJ1939GetRxData.md).

It should be noted that this function is only called once for each logical ECU within a node when global PGs are received.

## Parameters

- **ecuHandle**: ECU handle
- **srcAddr**: source address
- **dstAddr**: destination address
- **length**: number of received data
- **pgnum**: PGN of the received parameter group

## Return Values

—

## Example

```c
dword J1939AppRxIndication( LONG ecuHdl, LONG srcAddr, LONG dstAddr, LONG len, LONG pgNumber)
{
  char data[50];
  J1939GetRxData( elCount(data), data );
  /* user code */
  return 0;
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)