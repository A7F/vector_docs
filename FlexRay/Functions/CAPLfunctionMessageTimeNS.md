[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Functions/CAPLfunctionMessageTimeNS.md)

[CAPL Functions](../../CAPLfunctions.md) » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » MessageTimeNS (FR)

# MessageTimeNS (FR)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
float ns = MessageTimeNS( this );
```

## Description

This function returns the receive time of the frame or slot in nanoseconds.

## Parameters

- **this**  
  The function can only be used in the context of the following event procedures:
  - [on frFrame](../EventProcedures/CAPLfunctionOnFRFrame.md)
  - [on frNullFrame](../EventProcedures/CAPLfunctionOnFRNnullFrame.md)
  - [on frFrameError](../EventProcedures/CAPLfunctionOnFRFrameError.md)
  - [on frSlot](../EventProcedures/CAPLfunctionOnFRSlot.md)
  - [on frStartCycle](../EventProcedures/CAPLfunctionOnFRStartCycle.md)

  `this` references the corresponding receive object in the event procedure.

## Return Values

Receive time in nanoseconds since start of message.

## Example

For an example see event procedure [on frFrame](../EventProcedures/CAPLfunctionOnFRFrame.md).

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
