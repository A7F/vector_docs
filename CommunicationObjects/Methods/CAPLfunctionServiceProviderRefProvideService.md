[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionServiceProviderRefProvideService.md)

**CAPL Functions** » **Communication Objects** » **serviceProviderRef::ProvideService**

# serviceProviderRef::ProvideService (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

[int serviceProviderRef::ProvideService()](../Objects/CAPLfunctionServiceProviderRef.md)

## Description

Provides the service at the endpoint. This means that the binding will announce the service either by broadcast or at a central registry (depending on the binding) and that connection requests from consumers will be accepted.

## Parameters

—

## Return Values

- **0**: Success
- **!= 0**: Failure

## Example

```plaintext
MirrorAdjustment.providerSide[LeftMirror].ProvideService();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [serviceProviderRef::ReleaseService](CAPLfunctionServiceProviderRefReleaseService.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)