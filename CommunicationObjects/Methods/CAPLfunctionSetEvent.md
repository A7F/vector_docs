# SetEvent (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

- `long consumedEventRef::SetEvent(Event event);`
- `long providedEventRef::SetEvent(Event event);`
- `long eventConsumerRef::SetEvent(Event event);`
- `long eventProviderRef::SetEvent(Event event);`

## Description

Sets the referred-to event for the CO reference.

## Parameters

- **Event**: The new event.

## Return Values

- **0**: Success
- **3**: Given event doesn’t have the correct type
- **-1**: Given reference is invalid

## Example

```plaintext
consumedEventRef long cer;
cer.SetEvent(Services::Mirrors.Position);
```
