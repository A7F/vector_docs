[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783getbusname.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783GetBusName

# Iso11783GetBusName

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword Iso11783GetBusName( dword busHandle, dword bufferSize, char buffer[] );
```

## Description

Gets a bus name.

## Parameters

- **busHandle**: Bus handle, see also [Iso11783GetBus](#)
- **bufferSize**: Size of buffer in Bytes
- **buffer**: Bus name is copied into this buffer

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```c
char busName[32];
Iso11783GetBusName( busHandle, elCount(busName), busName );
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
