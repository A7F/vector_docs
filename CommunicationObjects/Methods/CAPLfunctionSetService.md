# SetService (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

- `long consumedServiceRef::SetService(service svc);`
- `long providedServiceRef::SetService(service svc);`
- `long serviceConsumerRef::SetService(service svc);`
- `long serviceProviderRef::SetService(service svc);`

## Description

Sets the referred-to service for the CO reference.

## Parameters

- **svc**: The new service.

## Return Values

- **0**: Success
- **3**: Given service doesn’t have the correct type
- **-1**: Given reference is invalid

## Example

```plaintext
consumedServiceRef Services::IMirrors csr;
csr.SetService(Services::Mirrors);
```
