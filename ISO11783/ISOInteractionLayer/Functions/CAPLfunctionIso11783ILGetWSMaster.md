[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILGetWSMaster.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_GetWSMaster

# Iso11783IL_GetWSMaster

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword Iso11783IL_GetWSMaster(dword ecuAddress);
```

## Description

This function returns the address of the Working Set Master, which is assigned to an ECU with the address ecuAddress.

## Parameters

- **ecuAddress**: address of an ECU

## Return Values

Address of the Working Set Master.

## Example

```c
wsmAddr = Iso11783IL_GetWSMaster(10);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)