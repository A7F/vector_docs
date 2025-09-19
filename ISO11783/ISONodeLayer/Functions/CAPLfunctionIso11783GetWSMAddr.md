[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783GetWSMAddr.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Node Layer** » Iso11783GetWSMAddr

# Iso11783GetWSMAddr

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword Iso11783GetWSMAddr( dword ecuHandle );
```

## Description

This function returns the address of the Working Set Master, which is assigned to this ECU.

## Parameters

- **ecuHandle**: ECU handle

## Return Values

Address of the Working Set Master for this ECU or the Null-Address (0xFE)

## Example

```c
addr = Iso11783GetWSMAddr( ecuHdl );
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
