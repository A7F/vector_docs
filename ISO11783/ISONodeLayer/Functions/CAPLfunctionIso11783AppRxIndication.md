[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783AppRxIndication.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783AppRxIndication

# Iso11783AppRxIndication (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
dword Iso11783AppRxIndication( long ecuHandle, long srcAddr, long dstAddr, long length, long pgnum );
```

## Description

The callback function indicates to the user that a parameter group has been received. It is not possible in CAPL to receive PG data through a callback function. For this reason, the data must be explicitly requested within the callback function with [Iso11783GetRxData()](CAPLfunctionIso11783GetRxData.md).

It should be noted that this function is only called once for each logical ECU within a node when global PGs are received.

## Parameters

- **ecuHandle**: ECU handle
- **srcAddr**: Source address
- **dstAddr**: Destination address
- **length**: Number of received data
- **pgnum**: PGN of the received parameter group

## Return Values

—

## Example

```c
dword Iso11783AppRxIndication( LONG ecuHdl, LONG srcAddr, LONG dstAddr, LONG len, LONG pgNumber)
{
  char data[50];
  Iso11783GetRxData( elCount(data), data );
  /* user code */
  return 0;
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)