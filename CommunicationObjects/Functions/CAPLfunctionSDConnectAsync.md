[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionSDConnectAsync.md)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » SD_ConnectAsync

# SD_ConnectAsync (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```c
void SD_ConnectAsync(providedServiceRef * providedService); // form 1
void SD_ConnectAsync(consumedServiceRef * consumedService); // form 2
```

## Description

Requests that a connection will be established between a service provider and a service consumer. The connection will be established asynchronously, i.e. after the call it will in the general case not be available immediately. You can react to the establishment of the connection with an [on SD_connection_established](../EventProcedures/CAPLfunctionOnSDConnectionEstablished.md) (or [on SD_connection_failed](../EventProcedures/CAPLfunctionOnSDConnectionFailed.md)) handler. You can call the function from both the provider and the consumer side.

Note that you need this function only when you implement service discovery yourself. In most cases, there’s an internal CANoe model for simulated endpoints which handles the protocol.

## Parameters

- **providedService**: Endpoints, from provider side.
- **consumedService**: Endpoints, from consumer side.

## Return Values

—

## Example

```c
SD_ConnectAsync(consumedService);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [SD_Disconnect](CAPLfunctionSDDisconnect.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)