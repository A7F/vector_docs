# SD_AnnounceProvider (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `long SD_AnnounceProvider(serviceProviderRef * provider); // form 1`
- `void SD_AnnounceProvider(providedServiceRef * providedService); // form 2`

### Description

Announces over the network that a service provider is running. You can pass either a provider endpoint, which will announce it generally (to a service registry or to all known consumers or by broadcast, depending on the binding protocol). Or you can pass a specific endpoint combination, which will announce it only to the given consumer endpoint.

Note that the provider will be automatically announced if you call **ProvideService** on the endpoint.

### Parameters

- **provider**: provider endpoint.
- **providedService**: Service provided by an endpoint for a consumer.

### Return Values

- **0**: Success
- **1**: Provider endpoint is not simulated
- **< 0**: Other error

### Example

```c
SD_AnnounceProvider(newProvider);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [SD_UnannounceProvider](CAPLfunctionSDUnannounceProvider.md)
