[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionSDRemoveConsumer.md)

# SD_RemoveConsumer (obsolete)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » SD_RemoveConsumer

**Valid for**: CANoe DE

## Function Syntax

```c
void SD_RemoveConsumer(serviceConsumerRef * consumer);
```

## Description

Removes a consumer endpoint from a service. You may call this to react to timeouts, or unannouncements from a real consumer, or to remove a simulated consumer endpoint.

## Parameters

- **consumer**: Consumer endpoint.

## Return Values

- **0**: Success
- **1**: The service does not allow dynamic endpoint changes
- **< 0**: Other error, e.g. variable not initialized

## Example

```c
SD_RemoveConsumer(newConsumer);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [SD_RemoveProvider](CAPLfunctionSDRemoveProvider.md) • [SD_AddConsumer](CAPLfunctionSDAddConsumer.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)