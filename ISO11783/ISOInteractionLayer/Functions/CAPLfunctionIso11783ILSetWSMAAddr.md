[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILSetWSMAAddr.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_SetWSMAddr

# Iso11783IL_SetWSMAddr

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
dword Iso11783IL_SetWSMAddr(dword wsmAddress);
```

## Description

Use this function to set the address of the Working Set Master, if this ECU is a member of a working set. All parameter groups which are addressed to the Working Set Master are also received by an ECU which calls this function.

## Parameters

- **wsmAddress**: Address of the Working Set Master for this ECU.

## Return Values

0 on success or [error code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```c
Iso11783IL_SetWSMAddr(0x06);
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
