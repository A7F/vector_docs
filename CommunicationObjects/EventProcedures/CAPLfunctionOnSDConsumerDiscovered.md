# on SD_consumer_discovered (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `on SD_consumer_discovered <Service>;` // form 1
- `on SD_consumer_discovered <ServiceProvider>;` // form 2

## Description

The event procedure is called when a new service consumer is discovered.

## Parameters

- **`<Service>`**: Designates the service on which the event procedure shall react. In this case, the procedure is called for any simulated provider which has discovered a new consumer.
- **`<ServiceProvider>`**: Designates the service provider on which the event procedure shall react.

## Selectors

- **address**: (Generalized) address of the consumer.

## Example

```plaintext
on SD_consumer_discovered Mirrors::MirrorAdjustment
{
  char buffer[100];
  Abstract_GetDisplayName(this.address, buffer);
  write("New consumer: %s", buffer);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [on SD_provider_discovered](CAPLfunctionOnSDProviderDiscovered.md)
