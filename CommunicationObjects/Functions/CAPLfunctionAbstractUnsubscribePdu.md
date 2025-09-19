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
