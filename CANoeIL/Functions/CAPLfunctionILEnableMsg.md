[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANoeIL/Functions/CAPLfunctionILEnableMsg.md)

**CAPL Functions** » [CANoe IL](../CAPLfunctionsCANoeILOverview.md) » ILEnableMsg

# ILEnableMsg

**Valid for**: CANoe DE • CANoe4SW DE

### Note

- This function is not available for all OEM add-ons — depends on the CANoeIL.
- This function can be used in a global node outside the node context of the IL.

## Function Syntax

```
long ILEnableMsg (char msgName[])
```

## Description

Enables the sending of the message.

## Parameters

- **msgName**: Message that should be re-enabled after having disabled it with [ILFaultInjectionDisableMsg](CAPLfunctionILFaultInjectionDisableMsg.md) / [ILDisableMsg](CAPLfunctionILDisableMsg.md).

## Return Values

- **0**: No error
- **-1**: Momentary state of the IL does not permit this function.

## Example

—

[ILFaultInjectionDisableMsg](CAPLfunctionILFaultInjectionDisableMsg.md) • [ILDisableMsg](CAPLfunctionILDisableMsg.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)