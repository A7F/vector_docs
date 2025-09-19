[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionOnAREthSDClientEventGroupStatusChanged.md)

**CAPL Functions** » [Ethernet](../../CAPLEthernetStartPage.md) » [AUTOSAR Eth IL](../CAPLfunctionsAREthILOverview.md) » OnAREthSDClientEventGroupStatusChanged

# OnAREthSDClientEventGroupStatusChanged

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnAREthSDClientEventGroupStatusChanged( dword serviceId, dword instanceId, dword eventGroupId, long status );
```

## Description

This callback function can be implemented in the CAPL program if an Event Consumer (Client) wants to be notified of status changes to Event Groups. The function is called whenever the status of an Event Group changes. The callback function can only be called for status changes related to an Event Group that is consumed by this node.

## Parameters

- **serviceId**: ID of the service whose status has changed.
- **instanceId**: Instance ID
- **eventGroupId**: ID of the Event Group
- **status**:
  - 0: not subscribed
  - 1: subscribed

## Return Values

—

## Example

```plaintext
void OnAREthSDClientEventGroupStatusChanged( dword serviceId, dword instanceId, dword eventGroupId, long status)
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
- OnAREthEventReceived
- OnAREthFieldNotification
- OnAREthMethodError
- OnAREthMethodRequest
- OnAREthMethodResponse
- OnAREthPrepareEvent
- OnAREthClientAepConnected
- OnAREthClosedIPv6TCPConnection, OnAREthClosedIPv4TCPConnection, OnAREthClosedTCPConnection
- OnAREthClosedTLSConnection
- OnAREthEstablishedIPv6TCPConnection, OnAREthEstablishedIPv4TCPConnection, OnAREthEstablishedTCPConnection
- OnAREthEstablishedTLSConnection
- OnAREthMessage
- OnAREthNewServerAep
- OnAREthProcessRxMessage
- OnAREthProcessTxARPDU
- OnAREthProcessTxMessage
- OnAREthSDClientEventGroupStatusChanged
- OnAREthSDClientServiceStatusChanged
- OnAREthSDServerEventGroupStatusChanged
- OnAREthSDServerEventGroupStatusChangedIPv6
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
