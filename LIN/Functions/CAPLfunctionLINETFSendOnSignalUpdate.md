# linETFSendOnSignalUpdate

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINETFSendOnSignalUpdate.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linETFSendOnSignalUpdate

## Function Syntax

```plaintext
long linETFSendOnSignalUpdate(long etfId, long active);
```

## Description

With this function, it is possible to activate/deactivate the automatic responses on a certain event-triggered frame request in the case of a signal update on its associated frame(s). This concerns all Slave tasks publishing the responses to the specified event-triggered frame.

## Parameters

- **etfId**: Identifier of event-triggered frame.  
  Value range: 0-59

- **active**:  
  1: Activate  
  0: Deactivate

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linActivateCollisionResolution](CAPLfunctionLINActivateCollisionResolution.md) • [linETFSetDirtyFlag](CAPLfunctionLINETFSetDirtyFlag.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)