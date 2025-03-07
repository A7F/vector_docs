[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Objects/CAPLfunctionEventProviderRef.md)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » eventProviderRef

# eventProviderRef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `eventProviderRef * <var>;` // form 1
- `eventProviderRef <Event> <var>;` // form 2
- `eventProviderRef <Datatype> <var>;` // form 3

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

- [eventProviderRef::GetNrOfSubscribedConsumers](../Methods/CAPLfunctionEventProviderRefGetNrOfSubscribedConsumers.md)
- [eventProviderRef::GetSubscribedConsumer](../Methods/CAPLfunctionEventProviderRefGetSubscribedConsumer.md)
- [eventProviderRef::Trigger](../Methods/CAPLfunctionEventProviderRefTrigger.md)
- [eventProviderRef::SetProvider](../Methods/CAPLfunctionSetProvider.md)
- [eventProviderRef::GetProvider](../Methods/CAPLfunctionGetProvider.md)
- [eventProviderRef::GetProviderIndex](../Methods/CAPLfunctionGetProviderIndex.md)
- [eventProviderRef::SetEvent](../Methods/CAPLfunctionSetEvent.md)
- [eventProviderRef::Clear](../Methods/CAPLfunctionClear.md)

## Description

References an event provider endpoint.

## Parameters

- **Event**: Event of a service, determining the data type of the object.
- **DataType**: Data type of the object.

## Selectors

- **Name**: Name of the provider endpoint.  
  **Type**: `char[]`  
  **Access Limitation**: Read only

- **Path**: Full path of the provider endpoint (including namespaces).  
  **Type**: `char[]`  
  **Access Limitation**: Read only

- **IsConsistent**: Returns whether the object refers to an existing endpoint.  
  **Type**: `dword`  
  **Access Limitation**: Read only

- **IsValid**: Returns whether **IsConsistent** is true and the endpoint is accessible (it’s not set to **Remote** state for example).  
  **Type**: `dword`  
  **Access Limitation**: Read only

- **ProviderIndex**: Index of the provider. Note that the index may change if providers are added or removed.  
  **Type**: `dword`  
  **Access Limitation**: Read only

- **ServiceProvider**: Reference to the provider of the service containing the event.  
  **Type**: `serviceProviderRef*`  
  **Access Limitation**: Read only

## Example

```plaintext
eventProviderRef long event1;
event1 = MirrorAdjustment.providerSide[LeftMirror].CurrentPosition;
$event1 = newValue;
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)