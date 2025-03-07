[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionSDDiscoverProviders.md)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » SD_DiscoverProviders

# SD_DiscoverProviders (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
void SD_DiscoverProviders(serviceConsumerRef * consumer);
```

## Description

Starts service discovery by requesting over the network to be informed of all running providers of a service. You can react to the response(s) with an [on SD_provider_discovered](../EventProcedures/CAPLfunctionOnSDProviderDiscovered.md) handler.

## Parameters

- **consumer**: Consumer endpoint.

## Return Values

—

## Example

```
SD_DiscoverProviders(MirrorAdjustment[CANoe]);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)