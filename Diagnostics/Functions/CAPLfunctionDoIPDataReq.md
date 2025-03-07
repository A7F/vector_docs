[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPDataReq.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » DoIP_DataReq

# DoIP_DataReq

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**

The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```
void DoIP_DataReq( byte buffer[], dword count, dword vehicleAddress, dword testerAddress);
```

## Description

Request the transfer of the given data to the DoIP peer.

## Parameters

- **buffer**: Buffer containing the data to be transmitted.
- **count**: Size of data in bytes.
- **vehicleAddress**: Logical DoIP address of the ECU, i.e. the target in a tester and the source in an ECU simulation.
- **testerAddress**: An ECU simulation may specify the logical address of the tester to send to by giving a value other than **0** here. Otherwise and in tester nodes, **0** should be given. This will determine the tester’s address automatically, i.e. the configured value in a tester, or the sender address of the last request in an ECU simulation.

## Return Values

—

## Example

```
_Diag_DataRequest( BYTE data[], DWORD count, long furtherSegments)
{
    // send data via DoIP
    DoIP_DataReq( data, count, gDoIPAddress, 0);
}
```

[_Diag_DataRequest](CAPLfunctionDiagDataRequest.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)