# OpenWebSocketConnection

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

`MethodReturnValueType OpenWebSocketConnection ( )`

## Description

This function is used to open the websocket and underlying TCP/TLS connection of the respective participant.

The Charging Station tries to connect to the CSMS. The CSMS starts listening for new connections.

## Parameters

—

## Return Values

**MethodReturnValueType**

All function calls will return a MethodReturnValueType indicating whether the call was successful or not. Possible values:

- `0`: OK
- `1`: InvalidArgument
- `2`: NoMatchingElementFound
- `3`: UnknownError

## Example

—
