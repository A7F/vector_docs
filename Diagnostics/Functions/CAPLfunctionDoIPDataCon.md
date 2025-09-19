# DoIP_DataCon

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**: The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_DataCon( dword count);
```

## Description

This callback is called from the DoIP/TP layer when the data to be sent was successfully handed over to the DoIP/TP layer.

**Note**: The physical transmission of the data might not have been completed by the DoIP/TP layer (maybe not even been started) when this callback is called.

## Parameters

- **count**: Size of the sent data in bytes.

## Return Values

—

## Example

```plaintext
void DoIP_DataCon( dword count)
{
   // pass up to the diagnostics layer
   Diag_DataCon( count);
}
```

[Diag_DataCon](CAPLfunctionDiagDataCon.md)
