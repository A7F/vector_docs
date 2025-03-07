[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPSendEntityStatusRequest.md)

**CAPL Functions** » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » DoIP_SendEntityStatusRequest

# DoIP_SendEntityStatusRequest

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_SendEntityStatusRequest();
void DoIP_SendEntityStatusRequest(char IPaddress[]);
```

## Description

Sends an entity status request as limited broadcast or to the given address.

## Parameters

- **IPaddress**: Address to send to, i.e. not a limited broadcast. May be a directed broadcast address.

## Return Values

—

## Example

```plaintext
void _DoIP_EntityStatusResponse( char IPaddress[], WORD port, BYTE nodeType, BYTE maxConcurrentTCPsockets, BYTE currentlyOpenTCPsockets, DWORD maxDataSize)
{
  write( "_DoIP_EntityStatusResponse( '%s', %d, %d, %d, %d, %d)",
    IPaddress, port, nodeType, maxConcurrentTCPsockets,
    currentlyOpenTCPsockets, maxDataSize);
  testSupplyTextEvent( cTE_EntityStatusRespInd);
}

// Send an entity status request and wait for the first response
Testcase TC_EntityStatus()
{
  DoIP_SendEntityStatusRequest();
  testWaitForTextEvent( cTE_EntityStatusRespInd, 500);
}
```

[_DoIP_EntityStatusResponse](CAPLfunctionDoIPEntityStatusResponse.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)