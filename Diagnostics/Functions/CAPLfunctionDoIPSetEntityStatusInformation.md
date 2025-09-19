# DoIP_SetEntityStatusInformation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_SetEntityStatusInformation(long nodeType, dword maxRequestSize);
```

## Description

Configures the response sent for an entity status request.

## Parameters

- **nodeType**
  - -1: do not send a response for the request (default)
  - 0: gateway
  - 1: node
  - others: reserved

- **maxRequestSize**
  - 0: do not send this optional parameter in a response
  - 0xFFFFFFFF: send a value that is supported by this implementation. Currently 16777216 is sent (i.e. 16 MiB)
  - other: value sent in the response

## Return Values

—

## Example

```plaintext
// The ECU simulation will return type "node" and a maximum length supported
// by this protocol implementation
DoIP_SetEntityStatusInformation( 1, 0xFFFFFFFF);
```

[DoIP_SendEntityStatusRequest](CAPLfunctionDoIPSendEntityStatusRequest.md)
