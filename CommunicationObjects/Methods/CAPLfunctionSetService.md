[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionSetService.md)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » SetService

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)