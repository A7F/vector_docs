[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionOnAREthSDServerEventGroupStatusChanged.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » **OnAREthSDServerEventGroupStatusChanged**

# OnAREthSDServerEventGroupStatusChanged

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnAREthSDServerEventGroupStatusChanged( dword serviceId, dword instanceId, dword eventGroupId, long status, dword newIpAddress, dword newPort ); // form 1

void OnAREthSDServerEventGroupStatusChanged( dword serviceId, dword majorVersion, dword instanceId, dword eventGroupId, long status, dword newIpAddress, dword newPort ); // form 2
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
- **newIpAddress**: IPv4 address via which the subscription was received.
- **newPort**: Source port via which the subscription was received.
- **majorVersion**: Service interface major version.

## Return Values

—

## Example

```c
void OnAREthSDServerEventGroupStatusChanged( dword serviceId, dword instanceId, dword eventGroupId, long status, dword newIpAddress, dword newPort)
{
  char buffer[100];
  if(status == 0)
  {
    snprintf(buffer,elcount(buffer),"not subscribed");
  }
  else if(status == 1)
  {
    snprintf(buffer,elcount(buffer),"subscribed");
  }
  else
  {
    snprintf(buffer,elcount(buffer),"Undefined status");
  }
  write("Event group (ID %d), of service %d (instance %d): %s",eventGroupId,serviceId,instanceId,buffer);
}
```

[See Also](javascript:void(0);)
```markdown
- [OnAREthEventReceived](CAPLfunctionOnAREthEventReceived.md#aanchor30368)
- [OnAREthFieldNotification](CAPLfunctionOnAREthFieldNotification.md#aanchor14184)
- [OnAREthMethodError](CAPLfunctionOnAREthMethodError.md#aanchor22451)
- [OnAREthMethodRequest](CAPLfunctionOnAREthMethodRequest.md#aanchor9214)
- [OnAREthMethodResponse](CAPLfunctionOnAREthMethodResponse.md#aanchor30036)
- [OnAREthPrepareEvent](CAPLfunctionOnAREthPrepareEvent.md#aanchor2386)
- [OnAREthClientAepConnected](CAPLFunctionOnAREthClientAepConnected.md#aanchor24508)
- [OnAREthClosedIPv6TCPConnection](CAPLfunctionOnAREthClosedIPv6TCPConnection.md#aanchor22267)
- [OnAREthClosedTLSConnection](CAPLfunctionOnAREthClosedTLSConnection.md#aanchor20038)
- [OnAREthEstablishedIPv6TCPConnection](CAPLfunctionOnAREthEstablishedIPv6TCPConnection.md#aanchor12103)
- [OnAREthEstablishedTLSConnection](CAPLfunctionOnAREthEstablishedTLSConnection.md#aanchor8074)
- [OnAREthMessage](CAPLfunctionOnAREthMessage.md#aanchor19976)
- [OnAREthNewServerAep](CAPLFunctionOnAREthNewServerAep.md#aanchor11168)
- [OnAREthProcessRxMessage](CAPLfunctionOnAREthProcessRxMessage.md#aanchor5203)
- [OnAREthProcessTxARPDU](CAPLfunctionOnAREthProcessTxARPDU.md#aanchor10839)
- [OnAREthProcessTxMessage](CAPLfunctionOnAREthProcessTxMessage.md#aanchor20914)
- [OnAREthSDClientEventGroupStatusChanged](CAPLfunctionOnAREthSDClientEventGroupStatusChanged.md#aanchor27568)
- [OnAREthSDClientServiceStatusChanged](CAPLfunctionOnAREthSDClientServiceStatusChanged.md#aanchor8205)
- [OnAREthSDServerEventGroupStatusChanged](#aanchor7786)
- [OnAREthSDServerEventGroupStatusChangedIPv6](CAPLfunctionOnAREthSDServerEventGroupStatusChangedIPv6.md#aanchor23205)
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)