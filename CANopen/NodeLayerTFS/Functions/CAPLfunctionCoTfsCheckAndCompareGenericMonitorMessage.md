# coTfsCheckAndCompareGenericMonitorMessage (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsCheckAndCompareGenericMonitorMessage( dword canId, dword dlc, qword msgData, qword msgMask, dword order );
```

## Description

This function checks if the expected message data are received.

After monitoring is started with [coTfsConfigureGenericMonitor](CAPLfunctionCoTfsConfigureGenericMonitor.md) the received messages can be checked with this function. The parameter **order** defines to which message the comparison is executed. The check is successfully passed if the message with the expected message number and the expected data is received.

The function can be used during a monitoring started with [coTfsConfigureGenericMonitor](CAPLfunctionCoTfsConfigureGenericMonitor.md) as well as after [coTfsDeactivateGenericMonitor](CAPLfunctionCoTfsDeactivateGenericMonitor.md). The internal list of received messages is reset not before the monitoring is restarted with [coTfsConfigureGenericMonitor](CAPLfunctionCoTfsConfigureGenericMonitor.md).

## Parameters

- **canId**: CAN-ID of the monitored message.
- **dlc**: Message length in byte, [0..8].
- **msgData**: Expected message data.
- **msgMask**: Message data mask, set bits are compared and the message is presumed to be valid if the bits match with the data.
- **order**: 
  - 0: Any receive message must contain the data specified in `msgData`/`msgMask`
  - 1..0xFFFFFFFE: The numeric specified message must contain the data specified in `msgData`/`msgMask`, 1 is the oldest message
  - 0xFFFFFFFF: The last received message must contain the data specified in `msgData`/`msgMask`

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

—
