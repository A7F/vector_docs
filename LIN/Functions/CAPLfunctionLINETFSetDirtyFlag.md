# linETFSetDirtyFlag

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINETFSetDirtyFlag.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linETFSetDirtyFlag

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long linETFSetDirtyFlag(long assocId, long dirty);
```

## Description

With this function it is possible to set/clear the dirty flag of an associated frame. If the dirty flag of an associated frame is set when the corresponding event-triggered frame is being requested, then the LIN hardware will try to transmit the associated frame's data. The dirty flag gets reset automatically when the associated frame has been sent successfully – either via the event-triggered frame or unconditionally.

## Parameters

- **assocId**: Identifier of unconditional frame. LIN frame identifier of associated (unconditional) frame whose dirty flag should be set or cleared. Value range: 0 .. 63
- **dirty**:
  - 1: Set the dirty flag.
  - 0: Clear the **dirty** flag.

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linActivateCollisionResolution](CAPLfunctionLINActivateCollisionResolution.md) • [linETFSendOnSignalUpdate](CAPLfunctionLINETFSendOnSignalUpdate.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
