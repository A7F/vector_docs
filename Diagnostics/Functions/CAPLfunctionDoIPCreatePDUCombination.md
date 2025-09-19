# DoIP_CreatePDUCombination

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
long DoIP_CreatePDUCombination();
```

## Description

Initialize the combination of several PDUs for sending as one block of data on the TCP connection. If PDUs were already stored they will be discarded.

## Parameters

—

## Return Values

- **0**: Success
- **Other**: Reserved

## Example

See [DoIP_SendPDUCombination](CAPLfunctionDoIPSendPDUCombination.md)

[DoIP_AddCombinedPDU](CAPLfunctionDoIPAddCombinedPDU.md) • [DoIP_SendPDUCombination](CAPLfunctionDoIPSendPDUCombination.md)
