# consumedServiceRef::IsServiceRequested (obsolete)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » consumedServiceRef::IsServiceRequested

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

dword [consumedServiceRef](../Objects/CAPLfunctionConsumedServiceRef.md)::IsServiceRequested();

## Description

Returns whether the service is currently requested by the consumer.

## Parameters

—

## Return Values

- **0**: Service is not currently requested
- **1**: Service is currently requested

## Example

```plaintext
val = MirrorAdjustment.consumerSide[CANoe,LeftMirror].IsServiceRequested();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [consumedServiceRef::ReleaseService](CAPLfunctionConsumedServiceRefReleaseService.md) • [consumedServiceRef::RequestService](CAPLfunctionConsumedServiceRefRequestService.md)
