# on SD_connection_requested (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

`on SD_connection_requested <ServiceProvider>;`

## Description

The event procedure is called when a connection is requested by a consumer.

**Note**: This is a **logical** connection which needs not correspond e.g. to a TCP connection.

## Parameters

- **`<ServiceProvider>`**: Designates the service provider on which the event procedure shall react.

## Selectors

- **consumer**: Consumer which requests the connection (the type is [serviceConsumerRef *](../Objects/CAPLfunctionServiceConsumerRef.md)).

## Example

```plaintext
on SD_connection_requested Mirrors::MirrorAdjustment.providerSide[LeftMirror]
{
  // react on the request with connection establishment
  SD_ConnectAsync(MirrorAdjustment.providerSide[this.consumer.ConsumerIndex, LeftMirror]);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [SD_ConnectAsync](../Functions/CAPLfunctionSDConnectAsync.md) • [on SD_connection_established](CAPLfunctionOnSDConnectionEstablished.md)
