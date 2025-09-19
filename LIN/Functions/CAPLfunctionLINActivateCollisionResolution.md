[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINActivateCollisionResolution.md)

## linActivateCollisionResolution

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linActivateCollisionResolution

**Valid for**: CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
long linActivateCollisionResolution(long etfId, long activate);
```

### Description

Activates or deactivates the Master node's automatic collision resolution of an event-triggered frame.

By default, the automatic collision resolution is active. If a collision occurs for any event-triggered frame, the Master resolves this collision by sending headers for all associated frames using the event-triggered frame slot. After all associated frames have sent new data, the Master sends the event-triggered frame header until the next collision occurs.

If the automatic collision resolution is deactivated, the Master always sends the event-triggered frame's header.

**Note**: If the Master node is not simulated or no schedule tables are defined, then this function will have no effect.

### Parameters

- **etfId**: Identifier of event-triggered frame. Value range: 0-59
- **activate**:
  - 0: Disable
  - 1: Enable

### Return Values

On success, a value unequal to zero, otherwise zero.

### Example

—

[linETFSendOnSignalUpdate](CAPLfunctionLINETFSendOnSignalUpdate.md) • [linETFSetDirtyFlag](CAPLfunctionLINETFSetDirtyFlag.md) • [linSetRespLength](CAPLfunctionLINSetRespLength.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
