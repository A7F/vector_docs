[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/EventProcedures/CAPLfunctionOnTransmitAnyCall.md)

## on transmit_any_call

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » on transmit_any_call

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Function Syntax

`on transmit_any_call <Interface Member>;`

### Description

This handler is called whenever an instance of a consumed method member transmits a value via the [CAPL binding](../../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md).

If the member does not use the CAPL binding, the handler is ignored.

If there are multiple handlers for the same member, the measurement will be aborted.

### Parameters

- **<Interface Member>**: Designates the consumed interface method for which the handler shall be called.

### Selectors

- **object**: Parent object of the transmitted value.
  - Type: `distObjRef <T>`
  - Access Limitation: Read only

- **context**: Call context of the method call.
  - Type: `callContext <T>`
  - Access Limitation: Read only

### Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)