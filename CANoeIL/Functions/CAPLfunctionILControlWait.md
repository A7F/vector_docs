[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANoeIL/Functions/CAPLfunctionILControlWait.md)

**CAPL Functions** » **CANoe IL** » **ILControlWait**

# ILControlWait

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
This function can only be used in the CAPL file that is attached to the appropriate node. The corresponding function [ILNodeControlWait](CAPLfunctionILNodeControlWait.md) can be used in a global node outside or in test modules.

## Function Syntax

`long ILControlWait()`

## Description

Cyclical sending is stopped; setting signals is possible.  
Cyclical sending is continued only after an [ILControlResume](CAPLfunctionILControlResume.md).

## Parameters

—

## Return Values

- **0**: No error.
- **1**: Momentary state of the IL does not permit this query.
- **50**: Node layer is inactive — possibly deactivated in the node's configuration dialog.

## Example

—

[ILControlInit](CAPLfunctionILControlInit.md) • [ILControlResume](CAPLfunctionILControlResume.md) • [ILControlStart](CAPLfunctionILControlStart.md) • [ILControlStop](CAPLfunctionILControlStop.md)

© Vector Informatik GmbH  
**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)