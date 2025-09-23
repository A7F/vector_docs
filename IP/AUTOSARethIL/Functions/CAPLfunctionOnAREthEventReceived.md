[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionOnAREthEventReceived.md)

**CAPL Functions** » [Ethernet](../../CAPLEthernetStartPage.md) » [AUTOSAR Eth IL](../CAPLfunctionsAREthILOverview.md) » `<OnAREthEventReceived>`

# `<OnAREthEventReceived>`

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void <OnAREthEventReceived>( dword cevHandle, dword messageHandle );
```

## Description

This callback function is called by AUTOSAR Eth IL when a notification message has been received for the Event specified in the **cevHandle** parameter.

A callback function with this signature must be passed to the CAPL function [AREthCreateEventConsumer](CAPLfunctionAREthCreateEventConsumer.md).

## Parameters

- **cevHandle**: Handle of the Event that triggered the callback, see [AREthCreateEventConsumer](CAPLfunctionAREthCreateEventConsumer.md).
- **messageHandle**: Message handle of the SOME/IP Event.

## Return Values

—

## Example

```plaintext
variables
{
  DWORD aep; // Application Endpoint handle
  DWORD csi; // consumed Service Instance handle
  DWORD ceg; // consumed Eventgroup handle
  DWORD cev; // consumed Event handle
}

on start()
{
  // open Application Endpoint
  aep = AREthOpenLocalApplicationEndpoint(17, 50002);
  // create Service Instance
  csi = AREthCreateConsumedServiceInstance(aep,10,1);
  // create Eventgroup
  ceg = AREthAddConsumedEventGroup(csi,1);
  // create Event Consumer
  cev = AREthCreateEventConsumer(csi,1,"CallbackEvent1 ");
}

void CallbackEvent1 (DWORD cevHandle, DWORD messageHandle)
{
  // this function is called if the Event was sent. Parameters can be evaluated here.
}
```

[See Also](javascript:void(0);)
