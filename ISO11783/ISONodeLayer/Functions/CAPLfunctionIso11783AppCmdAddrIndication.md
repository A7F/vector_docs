[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783AppCmdAddrIndication.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783AppCmdAddrIndication

# Iso11783AppCmdAddrIndication (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
dword Iso11783AppCmdAddrIndication( long ecuHandle, long length );
```

## Description

This function indicates that a new address has been assigned to the control device by the "CommandedAddress". The ECU must log on to the bus with the assigned address (see [Iso11783ECUGoOnline()](CAPLfunctionIso11783ECUGoOnline.md)).

Since the PG also returns the name of the ECU, the data must be requested within this callback with [Iso11783GetRxData()](CAPLfunctionIso11783GetRxData.md). This function is only called if the ECU can change its address (‘Self Configuring Address’-Bit of the device name must be set).

## Parameters

- **ecuHandle**: ECU handle
- **length**: Number of received data bytes

## Return Values

—

## Example

```c
dword Iso11783AppCmdAddrIndication( LONG ecuHandle, LONG length)
{
  /* user code */
  return 0;
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)