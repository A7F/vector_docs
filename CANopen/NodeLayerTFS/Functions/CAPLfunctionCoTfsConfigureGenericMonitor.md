# coTfsConfigureGenericMonitor (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsConfigureGenericMonitor( dword canId, dword isRTR, dword dlc, dword msgData, qword msgMask, dword minOcc, dword maxOcc, char comment[], dword varContent );
```

## Description

This function configures and activates a generic message monitor. With the monitor you can check the occurrence count of a defined CAN message in the period between configuration and [coTfsDeactivateGenericMonitor](CAPLfunctionCoTfsDeactivateGenericMonitor.md). The evaluation is done in the [coTfsDeactivateGenericMonitor](CAPLfunctionCoTfsDeactivateGenericMonitor.md) function.

Between the two functions any other test functions can be used.

The monitored message needn't sent and received cyclically, no time check is executed.

Each received message with the correct CAN-ID and DLC and that fits to the mask, is stored (independent of the given mask) and can be compared with compare data (in function [coTfsCheckAndCompareGenericMonitorMessage](CAPLfunctionCoTfsCheckAndCompareGenericMonitorMessage.md)) at runtime or after a [coTfsDeactivateGenericMonitor](CAPLfunctionCoTfsDeactivateGenericMonitor.md) command.

The user can specify a descriptive comment for the monitored message. This comment is written to the test report and provides a better overview.

## Parameters

- **canId**: CAN-ID of the monitored message.
- **isRTR**:
  - 0: Message is a data frame
  - 1: Message is a remote frame
- **dlc**: Message length in byte, [0..8].
- **msgData**: If data frame: expected message data.
- **msgMask**: If data frame: message data mask; set bits are compared and the message is presumed to be valid if the bits match with the data.
- **minOcc**: Defines how often the expected message must be received at least.
- **maxOcc**: Defines how often the expected message is allowed to be received at a maximum.
- **comment[]**: User defined comment that is written to the report (max. 200 characters).
- **varContent**:
  - 0: The same messages is expected always
  - 1: The most significant bit of byte 0 of `msgData` is toggled after each successful reception of a message, the initial value is set by the value of the bit in `msgData`.
  - Other values: Reserved

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

—
