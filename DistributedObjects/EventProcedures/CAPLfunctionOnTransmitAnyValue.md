[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/EventProcedures/CAPLfunctionOnTransmitAnyValue.md)

# on transmit_any_value

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » on transmit_any_value

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`on transmit_any_value <Interface Member>;`

## Description

This handler is called whenever an instance of a provided data, event, or field interface member transmits a value via the [CAPL binding](../../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md).

If the member does not use the CAPL binding, the handler is ignored.

If there are multiple handlers for the same member, the measurement will be aborted.

## Parameters

- **<Interface Member>**: Designates the provided data, event, or field interface member for which the handler shall be called.

## Selectors

- **object**: Parent object of the transmitted value.
  - Type: `distObjRef <T>`
  - Access Limitation: Read only

- **value**: New value
  - Type: `valueHandle <T>`
  - Access Limitation: Read only

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)