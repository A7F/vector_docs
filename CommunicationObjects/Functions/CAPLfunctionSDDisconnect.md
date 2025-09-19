# SD_Disconnect (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `void SD_Disconnect(providedServiceRef * providedService);` // form 1
- `void SD_Disconnect(consumedServiceRef * consumedService);` // form 2

## Description

Disconnects a service provider and consumer. You can call the function from both the provider and the consumer side.

Note that you need this function only when you implement service discovery yourself. In most cases, there’s an internal CANoe model for simulated endpoints which handles the protocol.

## Parameters

- **providedService**: Endpoints, from provider side.
- **consumedService**: Endpoints, from consumer side.

## Return Values

—

## Example

```c
SD_Disconnect(consumedService);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [SD_ConnectAsync](CAPLfunctionSDConnectAsync.md)
