# coTfsNmtEnterPreOperational (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```
long coTfsNmtEnterPreOperational
```

```
long coTfsNmtEnterPreOperational(dword broadcastFlag);
```

## Description

This call triggers a NMT message that sets the DUT (Device Under Test) into the pre-operational state.

The set state is checked with heartbeat and guarding mechanisms. 

For this, there is first an attempt to configure a heartbeat producer in the DUT (object 0x1017). The heartbeat message contains the current device status. If the DUT should not make a heartbeat producer available, a remote guarding frame is sent to the DUT which responses with the corresponding guarding response. The procedure is repeated again. The second response is evaluated and contains the device status. The CANopen® specification provides that a CANopen® device supports at least one of the two modes.

**Note**: If the heartbeat producer is already active, it will be restored at the end.

## Parameters

- **broadcastFlag**: `!=0`: NMT message is sent to all nodes (broadcast)

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```c
if (coTfsNmtEnterPreOperational() != 1) {
  write(" coTfsEnterPreOperational failed, the node is in an unknown state");
}
```
