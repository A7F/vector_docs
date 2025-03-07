[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPDataInd.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » DoIP_DataInd

# DoIP_DataInd

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**: The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_DataInd( byte buffer[], dword count, dword ecuAddress, dword testerAddress);
```

## Description

This callback is called from the DoIP layer when new data is received.

## Parameters

- **buffer**: Buffer containing the received data.
- **count**: Size of the received data in bytes.
- **ecuAddress**: Logical DoIP address of the ECU the data was sent to.
- **testerAddress**: Logical DoIP address of the tester that sent/received the data.  
  (**Note**: before 8.2 SP4 the value of **testerAddress** is **0** always.)

## Return Values

—

## Example

```plaintext
void DoIP_DataInd( byte buffer[], dword count,
                   dword ecuAddress, dword testerAddress)
{
    // gateway processing here…
    // pass data up to the diagnostics layer
    Diag_DataInd( buffer, count, 0);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)