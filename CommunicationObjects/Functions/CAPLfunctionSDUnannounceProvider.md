# SD_UnannounceProvider (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

### Function Syntax

```plaintext
long SD_UnannounceProvider(serviceProviderRef * provider);
```

### Description

Announces over the network that a service provider is no longer running. This may be necessary for some bindings where a central service registry is used.

Note that the service provider will be unannounced automatically if you call **ReleaseService** on the endpoint.

### Parameters

- **provider**: Provider endpoint.

### Return Values

- **0**: Success
- **1**: Provider endpoint is not simulated
- **< 0**: Other error

### Example

```plaintext
SD_UnannounceProvider(myProvider);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [SD_AnnounceProvider](CAPLfunctionSDAnnounceProvider.md)
