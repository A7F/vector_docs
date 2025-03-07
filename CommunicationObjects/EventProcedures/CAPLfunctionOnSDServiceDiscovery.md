[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/EventProcedures/CAPLfunctionOnSDServiceDiscovery.md)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » on SD_service_discovery

# on SD_service_discovery (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
on SD_service_discovery <Service>;
```

## Description

The event procedure is called when service discovery is triggered by a consumer.

## Parameters

- **<Service>**: Designates the Service on which the event procedure shall react.

## Selectors

- **consumer**: Consumer which triggered the service discovery, the type is [serviceConsumerRef *](../Objects/CAPLfunctionServiceConsumerRef.md)

## Example

```plaintext
on SD_service_discovery Mirrors::MirrorAdjustment
{
  dword i;
  for (i = 0; i < getNrOfCOProviders(MirrorAdjustment); ++i)
  {
    SD_AnnounceProvider(MirrorAdjustment.providerSide[this.consumer.ConsumerIndex, i]);
  }
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [on SD_consumer_discovered](CAPLfunctionOnSDConsumerDiscovered.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)