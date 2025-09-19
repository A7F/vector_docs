# Abstract_GetProviderId (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long Abstract_GetProviderId(addressHandle address);
```

## Description

Returns an ID for a provider with an abstract binding pseudo address. Through the ID, you can identify the provider.

## Parameters

- **Address**: Address of the provider.

## Return Values

A unique ID for the provider.

## Example

```plaintext
id = Abstract_GetProviderId(newProvider.Address);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [SD_SetAddress](CAPLfunctionSDSetAddress.md) • [Abstract_CreateAddress](CAPLfunctionAbstractCreateAddress.md) • [Abstract_GetDisplayName](CAPLfunctionAbstractGetDisplayName.md)
