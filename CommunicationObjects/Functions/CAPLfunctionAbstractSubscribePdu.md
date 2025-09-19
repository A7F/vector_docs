# Abstract_SubscribePdu (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
long Abstract_SubscribePDU(consumedPDURef * pdu);
```

## Description

Subscribes for a service PDU if abstract binding is used. Note that this is more **low-level**; usually it's more convenient to call [consumedPduRef::AbstractRequestPdu](../Methods/CAPLfunctionConsumedPduRefAbstractRequestPdu.md) on the PDU.

## Parameters

- **pdu**: PDU which shall be subscribed.

## Return Values

- **0**: Success
- **1**: Endpoint is not simulated
- **2**: Communication object does not use abstract binding
- **< 0**: Other error, e.g. PDU variable is not initialized

## Example

```
Abstract_SubscribePDU(MirrorAdjustment.consumerSide[0,0].PositionPDU);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [Abstract_UnsubscribePdu](CAPLfunctionAbstractUnsubscribePdu.md) • [SOMEIP_SubscribeEventGroup](CAPLfunctionSOMEIPSubscribeEventGroup.md)
