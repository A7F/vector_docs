[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/EventProcedures/CAPLfunctionOnSDProviderDiscovered.md)

**CAPL Functions** » [Communication Objects](../CAPLfunctionsCOOverview.md) » on SD_provider_discovered

# on SD_provider_discovered (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `on SD_provider_discovered <Service>;` // form 1
- `on SD_provider_discovered <ServiceConsumer>;` // form 2

## Description

The event procedure is called when a new service provider is discovered.

## Parameters

- **<Service>**: Designates the service on which the event procedure shall react. In this case, the procedure is called for any simulated consumer that has discovered a new provider.
- **<ServiceConsumer>**: Designates the service consumer on which the event procedure shall react.

## Selectors

- **address**: (Generalized) address of the provider.

## Example

```plaintext
on SD_provider_discovered Mirrors::MirrorAdjustment
{
  char buffer[100];
  Abstract_GetDisplayName(this.address, buffer);
  write("New provider: %s", buffer);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [on SD_consumer_discovered](CAPLfunctionOnSDConsumerDiscovered.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)