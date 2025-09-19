[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionOnAREthSDServerEventGroupStatusChangedIPv6.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » **OnAREthSDServerEventGroupStatusChangedIPv6**

# OnAREthSDServerEventGroupStatusChangedIPv6

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```c
void OnAREthSDServerEventGroupStatusChangedIPv6(dword serviceId, dword majorVersion, dword instanceId, dword eventGroupId, long status, byte newIpAddress[], dword newPort);
```

## Description

This callback function can be implemented in the CAPL program if a Service Server wants to be notified whenever a Subscriber is added. This function is called when a Client executes a subscribe eventgroup command.

## Parameters

- **serviceId**: ID of the service whose status has changed.
- **instanceId**: Instance ID
- **eventGroupId**: ID of the Event Group.
- **status**:
  - 0: not subscribed
  - 1: subscribed
- **newIpAddress**: IPv6 address via which the subscription was received.
- **newPort**: Source port via which the subscription was received.
- **majorVersion**: Service interface major version.

## Return Values

—

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
