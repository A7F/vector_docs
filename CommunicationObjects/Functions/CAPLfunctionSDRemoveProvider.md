[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionSDRemoveProvider.md)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » SD_RemoveProvider

# SD_RemoveProvider (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```c
void SD_RemoveProvider(serviceProviderRef * provider);
```

## Description

Removes a provider endpoint from a service. You may call this to react to timeouts, or unannouncements from a real provider, or to remove a simulated provider endpoint.

## Parameters

- **provider**: Provider endpoint.

## Return Values

- **0**: Success
- **1**: The service does not allow dynamic endpoint changes
- **< 0**: Other error, e.g. variable not initialized

## Example

```c
SD_RemoveProvider(newProvider);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [SD_RemoveConsumer](CAPLfunctionSDRemoveConsumer.md) • [SD_AddProvider](CAPLfunctionSDAddProvider.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)