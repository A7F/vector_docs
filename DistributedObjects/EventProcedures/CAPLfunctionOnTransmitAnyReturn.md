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

- **`<Interface Member>`**: Designates the provided interface method for which the handler shall be called.

## Selectors

- **Selector**: object
  - **Type**: distObjRef <T>
  - **Access Limitation**: Read only

- **Selector**: context
  - **Type**: callContext <T>
  - **Access Limitation**: Read only

## Example

—
