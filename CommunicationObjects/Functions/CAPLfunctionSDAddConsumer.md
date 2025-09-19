# SD_AddConsumer (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long SD_AddConsumer(service svc, char[] name, dword isSimulated, serviceConsumerRef * newConsumer);
```

## Description

Adds a consumer endpoint to a service communication object. The new endpoint may be real and detected through some protocol messages, or it may be simulated to test reaction of a provider to dynamic endpoint changes.

## Parameters

- **svc**: Service to which the endpoint shall be added.
- **name**: Name of the new consumer.
- **isSimulated**: 1 if the new consumer shall be simulated, 0 if it shall be real.
- **newConsumer**: Receives a reference to the new consumer.

## Return Values

- **0**: Success
- **1**: Service does not allow dynamic endpoint changes
- **2**: Name is already used for another endpoint
- **< 0**: Other error

## Example

```plaintext
SD_AddConsumer(MirrorAdjustment, "DiagConsole", 1, newConsumer);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [SD_AddProvider](CAPLfunctionSDAddProvider.md) • [SD_RemoveConsumer](CAPLfunctionSDRemoveConsumer.md)
