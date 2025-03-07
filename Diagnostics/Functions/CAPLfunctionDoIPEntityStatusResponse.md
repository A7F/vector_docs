[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPEntityStatusResponse.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » _DoIP_EntityStatusResponse

# _DoIP_EntityStatusResponse

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**: The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```c
void _DoIP_EntityStatusResponse( char IPaddress[], WORD port, BYTE nodeType, BYTE maxConcurrentTCPsockets, BYTE currentlyOpenTCPsockets, DWORD maxDataSize);
```

## Description

A response for an entity status request was received.

## Parameters

- **IPaddress**: Address in text form, e.g. "169.254.32.1" (IPv4) or "2001::1" (IPv6).
- **port**: IP source port of the packet at the sender.
- **nodeType**: Type of the node. Currently 0 for gateway and 1 for node are defined.
- **maxConcurrentTCPsockets**: Maximum number of TCP connections the entity can handle simultaneously.
- **currentlyOpenTCPsockets**: Number of TCP sockets currently open and in use.
- **maxDataSize**: Maximum size of a diagnostics request this entity can process. **Note**: A value of 0 indicates that the response did not carry this optional parameter.

## Return Values

—

## Example

```c
// Process an entity status response
void _DoIP_EntityStatusResponse( char IPaddress[], WORD port, BYTE nodeType, BYTE maxConcurrentTCPsockets, BYTE currentlyOpenTCPsockets, DWORD maxDataSize)
{
  write( "_DoIP_EntityStatusResponse( '%s', %d, %d, %d, %d, %d)",
  IPaddress, port, nodeType, maxConcurrentTCPsockets,
  currentlyOpenTCPsockets, maxDataSize);
  testSupplyTextEvent( cTE_EntityStatusRespInd);
}

Testcase TC_EntityStatus()
{
  DoIP_SendEntityStatusRequest();
  testWaitForTextEvent( cTE_EntityStatusRespInd, 500);
}
```

[DoIP_SendEntityStatusRequest](CAPLfunctionDoIPSendEntityStatusRequest.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)