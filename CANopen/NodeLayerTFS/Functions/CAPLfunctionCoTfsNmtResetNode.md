# coTfsNmtResetNode (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsNmtResetNode( void );
long coTfsNmtResetNode( dword broadcastFlag );
```

## Description

This call triggers a NMT message that resets the DUT (Device Under Test). After sending out the message, the boot-up message of the DUT is awaited. The reliable wait time corresponds to the general wait time, which is set with [coTfsSetTimeoutValue](CAPLfunctionCoTfsSetTimeOutValue.md).

**Note:** If the heartbeat producer is already active, it will be restored at the end.

## Parameters

- **broadcastFlag**: `!=0`: NMT message is sent to all nodes (broadcast)

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
if (coTfsNmtResetNode() != 1) {
  write("reset node failed");
}
```
