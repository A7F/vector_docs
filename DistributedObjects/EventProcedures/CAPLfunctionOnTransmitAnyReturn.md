[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/EventProcedures/CAPLfunctionOnTransmitAnyReturn.md)

**CAPL Functions** » **Distributed Objects** » **on transmit_any_return**

# on transmit_any_return

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
on transmit_any_return <Interface Member>;
```

## Description

This handler is called whenever an instance of a provided method member transmits a return via the [CAPL binding](../../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md).

- If the member does not use the CAPL binding, the handler is ignored.
- If there are multiple handlers for the same member, the measurement will be aborted.

## Parameters

- **<Interface Member>**: Designates the provided interface method for which the handler shall be called.

## Selectors

- **Selector**: object
  - **Type**: distObjRef <T>
  - **Access Limitation**: Read only

- **Selector**: context
  - **Type**: callContext <T>
  - **Access Limitation**: Read only

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)