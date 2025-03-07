[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionSDAddProvider.md)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » SD_AddProvider

# SD_AddProvider (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long SD_AddProvider(service svc, char[] name, dword isSimulated, serviceProviderRef * newProvider);
```

## Description

Adds a provider endpoint to a service communication object. The new endpoint may be real and detected through some protocol messages, or it may be simulated to test reaction of a consumer to dynamic endpoint changes.

## Parameters

- **svc**: Service to which the endpoint shall be added.
- **name**: Name of the new provider.
- **isSimulated**: 1 if the new provider shall be simulated, 0 if it shall be real.
- **newProvider**: Receives a reference to the new provider.

## Return Values

- **0**: Success
- **1**: Service does not allow dynamic endpoint changes
- **2**: Name is already used for another endpoint
- **< 0**: Other error

## Example

```plaintext
SD_AddProvider(MirrorAdjustment, "RearMirror", 1, newProvider);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [SD_AddConsumer](CAPLfunctionSDAddConsumer.md) • [SD_RemoveProvider](CAPLfunctionSDRemoveProvider.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)