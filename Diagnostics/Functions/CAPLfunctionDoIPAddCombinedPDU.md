[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPAddCombinedPDU.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » DoIP_AddCombinedPDU

# DoIP_AddCombinedPDU

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

`long DoIP_AddCombinedPDU(dword payloadType, byte payload[], dword payloadLen);`

## Description

Append another well-formed PDU to the PDU combination buffer for later sending with DoIP_SendPDUCombination. The currently configured protocol version byte will be used for the PDU.

## Parameters

- **payloadType**: [0; 0xFFFF] type to send, i.e. this can be any value.
- **payload**: The data following the generic DoIP header.
- **payloadLen**: Length of the data following the header.

## Return Values

- **-10**: Invalid parameter: the payload type or PDU given is too large.
- **-5**: Initialization error
- **0**: Success
- **Other**: Reserved

## Example

See [DoIP_SendPDUCombination](CAPLfunctionDoIPSendPDUCombination.md)

[DoIP_CreatePDUCombination](CAPLfunctionDoIPCreatePDUCombination.md) • [DoIP_SendPDUCombination](CAPLfunctionDoIPSendPDUCombination.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)