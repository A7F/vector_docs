# Abstract_CreateAddress (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

`addressHandle Abstract_CreateAddress(CommunicationObject co, char[] name);`

## Description

Creates a pseudo address for a communication object endpoint if abstract binding is used. The address can be attached to an endpoint with [SD_SetAddress](CAPLfunctionSDSetAddress.md). For abstract binding, the address of an endpoint actually does not contain more information than a name which can be retrieved again through [Abstract_GetDisplayName](CAPLfunctionAbstractGetDisplayName.md).

The address is necessary for implementation of service discovery; e.g. in the handlers [on SD_consumer_discovered](../EventProcedures/CAPLfunctionOnSDConsumerDiscovered.md) and [on SD_provider_discovered](../EventProcedures/CAPLfunctionOnSDProviderDiscovered.md), the address is passed as a selector.

## Parameters

- **co**: Communication object (usually a service) for which the address shall be created.
- **name**: Name for the address (e.g. the name of the endpoint).

## Return Values

—

## Example

```plaintext
SD_SetAddress(newProvider, Abstract_CreateAddress(MirrorAdjustment, "RearMirror"), MirrorAdjustment[CANoe]);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [Abstract_ReleaseAddress](CAPLfunctionAbstractReleaseAddress.md) • [SD_SetAddress](CAPLfunctionSDSetAddress.md) • [Abstract_GetDisplayName](CAPLfunctionAbstractGetDisplayName.md)
