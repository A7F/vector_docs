[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionSDSetAddress.md)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » SD_SetAddress

# SD_SetAddress (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long SD_SetAddress(serviceConsumerRef * consumer, addressHandle address, serviceConsumerRef * simulatedEndpoint); // from 1`
- `long SD_SetAddress(serviceConsumerRef * consumer, addressHandle address, serviceProviderRef * simulatedEndpoint); // from 2`
- `long SD_SetAddress(serviceProviderRef * provider, addressHandle address, serviceConsumerRef * simulatedEndpoint); // from 3`
- `long SD_SetAddress(serviceProviderRef * provider, addressHandle address, serviceProviderRef * simulatedEndpoint); // from 4`

## Description

Sets the address for an endpoint, normally after it has been added dynamically to a service. The address can be created with binding specific functions. The third parameter is the simulated endpoint where the new endpoint has been discovered and where the address for the new endpoint is now known.

## Parameters

- **consumer**: Consumer endpoint of which the address shall be set.
- **provider**: Provider endpoint of which the address shall be set.
- **address**: Address for the endpoint.
- **simulatedEndpoint**: Endpoint from which the function is called.

## Return Values

- **0**: Success
- **1**: The service does not allow dynamic endpoint changes
- **< 0**: Other error, e.g. variable not initialized

## Example

```plaintext
SD_SetAddress(newProvider, Abstract_CreateAddress(MirrorAdjustment, "RearMirror"), MirrorAdjustment[CANoe]);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [Abstract_CreateAddress](CAPLfunctionAbstractCreateAddress.md) • [SD_AddProvider](CAPLfunctionSDAddProvider.md) • [SD_AddConsumer](CAPLfunctionSDAddConsumer.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)