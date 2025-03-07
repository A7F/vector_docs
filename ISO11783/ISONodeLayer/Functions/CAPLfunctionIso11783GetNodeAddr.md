[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783GetNodeAddr.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Node Layer** » Iso11783GetNodeAddr

# Iso11783GetNodeAddr

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword Iso11783GetNodeAddr( dword ecuHandle );
```

## Description

This function returns the current address of a logical ECU.

## Parameters

- **ecuHandle**: ECU handle

## Return Values

- Current ECU address
- `0xFE` if the address is the ISO11783 NULL address. If this function is called with an invalid handle, the function returns `0xFFFF`.

## Example

```c
addr = Iso11783GetNodeAddr(ecuHandle);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)