[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939AppNmtIndication.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 NL](../CAPLfunctionsJ1939NLOverview.md) » J1939AppNmtIndication

# J1939AppNmtIndication (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword J1939AppNmtIndication( long busHandle, long address, long flag );
```

## Description

This function is called when an ECU claims an address or an ECU loses its address. The function is also called if no ECU was created yet.

With [J1939GetRxData()](CAPLfunctionJ1939GetRxData.md) the device name can be copied to a buffer.

## Parameters

- **busHandle**: bus handle
- **address**: address of the ECU or Null-Address
- **flag**: reason for calling this function:
  - 1: an ECU starts claiming, Address Claim PG received
  - 2: successfully claimed, 250 ms after Address Claim PG
  - 3: Cannot Claim Address received

## Return Values

—

## Example

```c
dword J1939AppNmtIndication( LONG busHandle, LONG address, LONG flag )
{
  char deviceName[8];
  J1939GetRxData( elCount(deviceName), deviceName ); 
  /* user code */
  return 0; 
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
