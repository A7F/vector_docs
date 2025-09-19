# measuredServiceRef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `measuredServiceRef * <var>;` // form 1
- `measuredServiceRef <Service> <var>;` // form 2
- `measuredServiceRef <Interface> <var>;` // form 3

## Method Syntax

—

## Description

References a service measurement point, which means measuring a specific connection between consumer and provider for a service.

## Parameters

- **Service**: Service, determining the data type of the object.
- **Interface**: Data type of the object (a service interface).

## Selectors

- **Name**: Name of the measurement endpoint
  - Type: `char[]`
  - Access Limitation: Read only

- **Path**: Full path of the measurement endpoint (including namespaces)
  - Type: `char[]`
  - Access Limitation: Read only

- **ConsumerIndex**: Index of the consumer. Note that the index may change if consumers are added or removed.
  - Type: `dword`
  - Access Limitation: Read only

- **ProviderIndex**: Index of the provider. Note that the index may change if providers are added or removed.
  - Type: `dword`
  - Access Limitation: Read only

## Example

```plaintext
measuredServiceRef MirrorAdjustment svc1;
svc1 = MirrorAdjustment.measure[CANoe,LeftMirror];
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
