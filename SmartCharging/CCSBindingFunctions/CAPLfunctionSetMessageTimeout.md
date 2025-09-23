# SetMessageTimeout

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

`MethodReturnValueType SetMessageTimeout (LastRxMessageIdType MessageType, uint32 TimeoutMs)`

## Description

This function overwrites the timeout the StateMachine will check against for the specified message.

## Parameters

- **MessageType**: ID of the message. See [MessageIDs](../Callbacks/SCC_MessageID.md) for more information.
- **TimeoutMs**: Timeout in ms.

## Return Values

**MethodReturnValueType**

All function calls (except for indications) will return a MethodReturnValueType indicating whether the call was successful or not. Possible values:

- `0`: OK
- `1`: InvalidArgument
- `2`: NoMatchingElementFound
- `3`: UnknownError

## Example

—
