[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Functions/CAPLfunctionFROutputDynFrame.md)

[CAPL Functions](../../CAPLfunctions.md) » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » frOutputDynFrame

# frOutputDynFrame

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
int ret = frOutputDynFrame( <frame var> );
```

## Description

This function updates the FlexRay Communication Controller's (CC) send buffer with the current data from the send object. This corresponds to a request to send.

Only frames in the dynamic segment can be sent using this function!

## Parameters

- `<frame var>`: Name of the variable referenced by the frame object. The variable name was defined when the object was created using [frFrame](../Objects/CAPLfunctionFRFrame.md).

## Return Values

- `0`: Ok, the request to send the frame is forwarded to the interface. This does not guarantee that the frame is really been sent. Refer to the FlexRay protocol rules.
- `-1`: Error, either the channel is not available or the slot ID is not in the dynamic segment.

## Example

For an example see function [frUpdateStatFrame](CAPLfunctionFRUpdateStatFrame.md).
