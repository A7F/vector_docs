[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionSDDisconnect.md)

**CAPL Functions** » [Communication Objects](../CAPLfunctionsCOOverview.md) » SD_Disconnect

# SD_Disconnect (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `void SD_Disconnect(providedServiceRef * providedService);` // form 1
- `void SD_Disconnect(consumedServiceRef * consumedService);` // form 2

## Description

Disconnects a service provider and consumer. You can call the function from both the provider and the consumer side.

Note that you need this function only when you implement service discovery yourself. In most cases, there’s an internal CANoe model for simulated endpoints which handles the protocol.

## Parameters

- **providedService**: Endpoints, from provider side.
- **consumedService**: Endpoints, from consumer side.

## Return Values

—

## Example

```c
SD_Disconnect(consumedService);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [SD_ConnectAsync](CAPLfunctionSDConnectAsync.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)