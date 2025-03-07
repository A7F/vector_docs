[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionOnSomeIpEventReceived.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » `<OnSomeIpEventReceived>`

# `<OnSomeIpEventReceived>`

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void <OnSomeIpEventReceived>( dword cevHandle, dword messageHandle );
```

## Description

This callback function is called by SOME/IP IL when a notification message has been received for the Event specified in the **cevHandle** parameter.

A callback function with this signature must be passed to the CAPL function [SomeIpCreateEventConsumer](CAPLfunctionSomeIpCreateEventConsumer.md).

## Parameters

- **cevHandle**: Handle of the Event that triggered the callback, see [SomeIpCreateEventConsumer](CAPLfunctionSomeIpCreateEventConsumer.md).
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
  aep = SomeIpOpenLocalApplicationEndpoint(17, 50002);
  // create Service Instance
  csi = SomeIpCreateConsumedServiceInstance(aep,10,1);
  // create Eventgroup
  ceg = SomeIpAddConsumedEventGroup(csi,1);
  // create Event Consumer
  cev = SomeIpCreateEventConsumer(csi,32770,"CallbackEvent1 ");
}

void CallbackEvent1 (DWORD cevHandle, DWORD messageHandle)
{
  // this function is called if the Event was sent. Parameters can be evaluated here.
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)