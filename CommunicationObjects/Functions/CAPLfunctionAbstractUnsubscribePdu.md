[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionAbstractUnsubscribePdu.md)

**CAPL Functions** » **Communication Objects** » **Abstract_UnsubscribePdu**

# Abstract_UnsubscribePdu (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long Abstract_UnsubscribePDU(consumedPDURef * pdu);
```

## Description

Unsubscribes for a service PDU if abstract binding is used. Note that this is more **low-level**; usually it's more convenient to call [consumedPduRef::AbstractReleasePdu](../Methods/CAPLfunctionConsumedPduRefAbstractReleasePdu.md) on the PDU.

## Parameters

- **pdu**: PDU which shall be unsubscribed.

## Return Values

- **0**: Success
- **1**: Endpoint is not simulated
- **2**: Communication object does not use abstract binding
- **< 0**: Other error, e.g. PDU variable is not initialized

## Example

```plaintext
Abstract_UnsubscribePDU(MirrorAdjustment.consumerSide[0,0].PositionPDU);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [Abstract_SubscribePdu](CAPLfunctionAbstractSubscribePdu.md) • [SOMEIP_UnsubscribeEventGroup](CAPLfunctionSOMEIPUnsubscribeEventGroup.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)