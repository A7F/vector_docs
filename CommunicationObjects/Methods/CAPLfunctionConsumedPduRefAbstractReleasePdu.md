[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionConsumedPduRefAbstractReleasePdu.md)

## consumedPduRef::AbstractReleasePdu (obsolete)

**CAPL Functions** » **Communication Objects** » consumedPduRef::AbstractReleasePdu

**Valid for**: CANoe DE

### Method Syntax

```plaintext
int consumedPDURef::AbstractReleasePDU();
```

### Description

Releases the subscription of a specific service PDU if abstract binding is used: for the specified consumer from the specified provider. If the PDU is released, it will be unsubscribed and not automatically re-subscribed.

### Parameters

—

### Return Values

- **0**: Success
- **!= 0**: Failure

### Example

```plaintext
MirrorAdjustment.consumerSide[CANoe,LeftMirror].StatusPDU.AbstractReleasePDU();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [consumedPduRef::AbstractRequestPdu](CAPLfunctionConsumedPduRefAbstractRequestPdu.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
