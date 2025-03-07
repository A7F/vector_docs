[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionServiceProviderRefReleaseService.md)

**CAPL Functions** » [Communication Objects](../CAPLfunctionsCOOverview.md) » serviceProviderRef::ReleaseService

# serviceProviderRef::ReleaseService (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

```plaintext
int serviceProviderRef::ReleaseService();
```

## Description

Releases the service at the endpoint. This means that the binding will stop announcing the service or unregister it from a central registry (depending on the binding) and that connection requests from consumers will be denied.

## Parameters

—

## Return Values

- **0**: Success
- **!= 0**: Failure

## Example

```plaintext
MirrorAdjustment.providerSide[LeftMirror].ReleaseService();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [serviceProviderRef::ProvideService](CAPLfunctionServiceProviderRefProvideService.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)