# on SD_connection_failed (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `on SD_connection_failed <ServiceProvider>;` // form 1
- `on SD_connection_failed <ServiceConsumer>;` // form 2
- `on SD_connection_failed <ProvidedService>;` // form 3
- `on SD_connection_failed <ConsumedService>;` // form 4

## Description

The event procedure is called when a connection attempt between a consumer and a provider fails.

**Note**: This is a **logical** connection which needs not correspond e.g. to a TCP connection.

If you specify a single endpoint, the procedure is called for all connections of that endpoint and the other endpoint can be identified through the **address** selector of the **this** variable. If you specify both endpoints, the procedure is only called for the specific pair of consumer and provider and there is no **this** variable.

## Parameters

- `<ServiceProvider>`: Designates the service provider on which the event procedure shall react.
- `<ServiceConsumer>`: Designates the service consumer on which the event procedure shall react.
- `<ProvidedService>`: Designates the pair of consumer and provider on which the event procedure shall react on provider side.
- `<ConsumedService>`: Designates the pair of consumer and provider on which the event procedure shall react on consumer side.

## Selectors

- **address**: Generalized address of the counterpart with which the connection failed.

## Example

```plaintext
on SD_connection_failed Mirrors::MirrorAdjustment.consumerSide[CANoe]
{
  char buffer[100];
  Abstract_GetDisplayName(this.address, buffer);
  write("Connection failed with %s", buffer);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [SD_ConnectAsync](../Functions/CAPLfunctionSDConnectAsync.md) • [on SD_connection_requested](CAPLfunctionOnSDConnectionRequested.md) • [on SD_connection_established](CAPLfunctionOnSDConnectionEstablished.md)
