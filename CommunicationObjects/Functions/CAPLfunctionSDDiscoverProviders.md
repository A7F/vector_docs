# SD_DiscoverProviders (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
void SD_DiscoverProviders(serviceConsumerRef * consumer);
```

## Description

Starts service discovery by requesting over the network to be informed of all running providers of a service. You can react to the response(s) with an [on SD_provider_discovered](../EventProcedures/CAPLfunctionOnSDProviderDiscovered.md) handler.

## Parameters

- **consumer**: Consumer endpoint.

## Return Values

—

## Example

```
SD_DiscoverProviders(MirrorAdjustment[CANoe]);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
