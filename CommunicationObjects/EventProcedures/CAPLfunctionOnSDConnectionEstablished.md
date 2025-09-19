# on SD_connection_established (obsolete)

**Valid for**: CANoe DE

## Function Syntax

- `on SD_connection_established <ServiceProvider>;` // form 1
- `on SD_connection_established <ServiceConsumer>;` // form 2
- `on SD_connection_established <ProvidedService>;` // form 3
- `on SD_connection_established <ConsumedService>;` // form 4

## Description

The event procedure is called when a connection is established between a consumer and a provider.

**Note**: This is a **logical** connection which needs not correspond e.g. to a TCP connection.

If you specify a single endpoint, the procedure is called for all connections of that endpoint and the other endpoint can be identified through the **service** selector of the **this** variable. If you specify both endpoints, the procedure is only called for the specific pair of consumer and provider and there is no **this** variable.

## Parameters

- `<ServiceProvider>`: Designates the service provider on which the event procedure shall react.
- `<ServiceConsumer>`: Designates the service consumer on which the event procedure shall react.
- `<ProvidedService>`: Designates the pair of consumer and provider on which the event procedure shall react on provider side.
- `<ConsumedService>`: Designates the pair of consumer and provider on which the event procedure shall react on consumer side.

## Selectors

- **service**: Object representing the logical connection (the type is [consumedServiceRef *](../Objects/CAPLfunctionConsumedServiceRef.md) on consumer side and [providedServiceRef *](../Objects/CAPLfunctionProvidedServiceRef.md) on provider side).

## Example

```plaintext
on SD_connection_established Mirrors::MirrorAdjustment.consumerSide[CANoe]
{
  // subscribe event
  Abstract_SubscribeEvent(MirrorAdjustment.consumerSide[CANoe, this.service.ProviderIndex].CurrentPosition);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [SD_ConnectAsync](../Functions/CAPLfunctionSDConnectAsync.md) • [on SD_connection_requested](CAPLfunctionOnSDConnectionRequested.md)
