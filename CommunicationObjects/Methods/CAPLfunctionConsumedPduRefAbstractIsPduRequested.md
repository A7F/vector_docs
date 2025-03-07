[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionConsumedPduRefAbstractIsPduRequested.md)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » consumedPduRef::AbstractIsPduRequested

# consumedPduRef::AbstractIsPduRequested (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

dword [consumedPDURef](../Objects/CAPLfunctionConsumedPDURef.md)::AbstractIsPDURequested();

## Description

Returns whether the specified service PDU is currently requested (if abstract binding is used).

## Parameters

—

## Return Values

- **0**: PDU is not currently requested
- **1**: PDU is currently requested

## Example

```plaintext
val = MirrorAdjustment.consumerSide[CANoe,LeftMirror].StatusPDU.AbstractIsPDURequested();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [consumedPduRef::AbstractReleasePdu](CAPLfunctionConsumedPduRefAbstractReleasePdu.md) • [consumedPduRef::AbstractRequestPdu](CAPLfunctionConsumedPduRefAbstractRequestPdu.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)