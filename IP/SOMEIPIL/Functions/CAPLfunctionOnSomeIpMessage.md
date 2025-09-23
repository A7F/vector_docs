# OnSomeIpMessage

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnSomeIpMessage( dword messageHandle );
```

## Description

This callback function can be implemented in the CAPL program to be notified when a SOME/IP message is received.

The function is called for all those SOME/IP messages that are received on the local Application Endpoint of the IL, see [SomeIpOpenLocalApplicationEndpoint](CAPLfunctionSomeIpOpenLocalApplicationEndpoint.md).

## Parameters

- **messageHandle**: Handle of the received SOME/IP message. The handle is needed for the functions that read out message data.

## Return Values

—

## Example

—

[See Also](javascript:void(0);)
