[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Functions/CAPLfunctionFRSetPayloadLengthInByte.md)

[CAPL Functions](../../CAPLfunctions.md) » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » frSetPayloadLengthInByte

# frSetPayloadLengthInByte

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
frSetPayloadLengthInByte( <frame var>, dword <dlc> );
```

## Description

This function sets the payload (data length) of the object in bytes. In the event of an uneven value, the length of the buffer will be set to the next even value.

The payload length can also be set using the FR_PayloadLength frame variables selector. However, in this case, the length is set in 16-bit words.

The data length can only be manipulated for frames sent in the dynamic segment!

## Parameters

- `<frame var>`: Name of the variable referenced by the frame object. The variable name was defined when the object was created using [frFrame](../Objects/CAPLfunctionFRFrame.md).
- `<dlc>`: Defines the payload (data length) in bytes.

## Return Values

—

## Example

For an example see function [frUpdateStatFrame](CAPLfunctionFRUpdateStatFrame.md).

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
