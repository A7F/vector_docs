# ILDisableMsg

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Note**

- This function is not available for all OEM add-ons — depends on the CANoeIL.
- Please check the help of the relevant Interaction layer:  
  [Overview - Modeling Libraries / Add-ons](../../../CANoeCANalyzer/LibrariesPackages/OEMPackages.md)
- This function can be used in a global node outside the node context of the IL.

## Function Syntax

`long ILDisableMsg (char msgName[])`

## Description

Disables the sending of the message except by calling the function [ILSetMsgEvent](CAPLfunctionILSetMsgEvent.md).

## Parameters

- **msgName**: Message that should be disabled.

## Return Values

- **0**: No error
- **-1**: Momentary state of the IL does not permit this function.

## Example

—

[ILFaultInjectionEnableMsg](CAPLfunctionILFaultInjectionEnableMsg.md) • [ILEnableMsg](CAPLfunctionILEnableMsg.md)
