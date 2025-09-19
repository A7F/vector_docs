[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/EventProcedures/CAPLfunctionOnTransmitAnyUnannounce.md)

## CAPL Functions » Distributed Objects » on transmit_any_unannounce

### Function Syntax

`on transmit_any_unannounce <Interface Member>;`

### Description

This handler is called whenever an instance of a provided data, event, or field member transmits an unannounce via the [CAPL binding](../../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md).

If the member does not use the CAPL binding, the handler is ignored.

If there are multiple handlers for the same member, the measurement will be aborted.

Inside the handler the [this](../../Other/EventProcedures/CAPLfunctionKeywordThis.md) expression refers to the parent object of the member.

### Parameters

- **`<Interface Member>`**: Designates the provided data, event, or field interface member for which the handler shall be called.

### Selectors

—

### Example

—

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
