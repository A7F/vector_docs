[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSimulateETFCollision.md)

**CAPL Functions** » **LIN** » **linSimulateETFCollision**

# linSimulateETFCollision

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword linSimulateETFCollision (dword etfId); // form 1`
- `dword linSimulateETFCollision (dword etfId, dword respLength, dword numCollisions, byte dataBytes[]); // form 2`

## Description

This function can be used to cause collisions for next coming header(s) of an event-triggered frame.

## Parameters

- **etfId**: LIN frame identifier in the range 0 .. 59
- **respLength**: Number of databytes to be sent as the response on the header of the event-triggered frame. Value range: 1..9. Default: 1
- **numCollisions**: Number of times the specified response has to be applied. Value range: 1..255. Default: 1
- **Databytes**: Array of databytes to be sent as the response. The size of the array shall correspond to the respLength parameter. Default: NULL

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linSetRespLength](CAPLfunctionLINSetRespLength.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
