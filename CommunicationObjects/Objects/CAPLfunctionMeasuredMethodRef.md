# measuredMethodRef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `measuredMethodRef * <var>; // form 1`
- `measuredMethodRef <Method> <var>; // form 2`
- `measuredMethodRef <Prototype> <var>; // form 3`

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- —

## Description

References a method measurement point, which means measuring a specific connection between consumer and provider for a service function.

## Parameters

- **Method**: Method, determining the data type of the object.
- **Prototype**: Data type of the object (a function prototype / signature).

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

- **measuredService**: The measurement point at the service.  
  Type: `measuredServiceRef *`  
  Access Limitation: Read only

- **LatestCall**: Information about the latest call measured at this point.  
  Type: `struct`  
  Access Limitation: Read only

- **LatestReturn**: Information about the latest return measured at this point.  
  Type: `struct`  
  Access Limitation: Read only

## Example

```plaintext
measuredMethodRef MirrorAdjustment.Adjust method;
method = MirrorAdjustment.measure[CANoe,LeftMirror].Adjust;
write("Latest x: %d", method.LatestCall.x);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
