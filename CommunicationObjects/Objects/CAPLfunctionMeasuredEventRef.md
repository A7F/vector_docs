# measuredEventRef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `measuredEventRef * <var>;` // form 1
- `measuredEventRef <Event> <var>;` // form 2
- `measuredEventRef <Datatype> <var>;` // form 3

## Method Syntax

—

## Description

References an event measurement point, which means measuring a specific connection between consumer and provider for a service event.

## Parameters

- **Event**: Event, determining the data type of the object.
- **Datatype**: Data type of the object.

## Selectors

- **Name**: Name of the measurement endpoint  
  Type: `char[]`  
  Access Limitation: Read only

- **Path**: Full path of the measurement endpoint (including namespaces)  
  Type: `char[]`  
  Access Limitation: Read only

- **ConsumerIndex**: Index of the consumer. Note that the index may change if consumers are added or removed.  
  Type: `dword`  
  Access Limitation: Read only

- **ProviderIndex**: Index of the provider. Note that the index may change if providers are added or removed.  
  Type: `dword`  
  Access Limitation: Read only

- **SubscriptionState**: State of the event subscription:
  - Unknown: the event subscription was not observed yet
  - Unsubscribed: the event is not subscribed
  - Subscribed: the event is subscribed  
  Type: `enum`  
  Access Limitation: Read only

## Example

```plaintext
measuredEventRef MirrorAdjustment.Position event;
event = MirrorAdjustment.measure[CANoe,LeftMirror].Position;
write("Latest x: %d", $event.x);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
