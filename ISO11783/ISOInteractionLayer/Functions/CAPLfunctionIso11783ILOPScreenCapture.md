[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPScreenCapture.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPScreenCapture

# Iso11783IL_OPScreenCapture

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPScreenCapture( dword itemRequested, dword path ); // form 1
long Iso11783IL_OPScreenCapture( dbNode implement, dword itemRequested, dword path ); // form 2
```

## Description

Sends a **Screen Capture** command to the Virtual Terminal to request a screen capture of the current screen image.

## Parameters

- **implement**: Simulation node to apply the function.
- **itemRequested**: Requested item
  - 0: Screen Image
  - 240-255: Manufacturer Proprietary
- **path**: Path of the request
  - 1: VT accessible storage/removable media
  - 240-255: Manufacturer Proprietary

## Return Values

- **0**: function has been executed successfully
- **< 0**: an error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
