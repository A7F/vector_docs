[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILSetVTStatus.md)

## VTIL_SetVTStatus

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_SetVTStatus

### Tool Availability

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

### Function Syntax

- `long VTIL_SetVTStatus(dword cycleTime);` // form 1
- `long VTIL_SetVTStatus(dword cycleTime, pg VT12 pgWithNewContent);` // form 2
- `long VTIL_SetVTStatus(dbNode vt, dword cycleTime);` // form 3
- `long VTIL_SetVTStatus(dbNode vt, dword cycleTime, pg VT12 pgWithNewContent);` // form 4

### Description

- Forms (1) and (3): This function changes the cycle time of the VT Status message. The content of VT Status message stays unchanged.
- Forms (2) and (4): This function changes the content and cycle time of the VT Status message.

### Parameters

- **vt**: VT simulation node to apply the function
- **cycleTime**: Cycle time of the VT Status message [ms] (default: 1000)
- **pgWithNewContent**: Content of this message is used by the following VT Status messages sent by the VT IL

### Return Values

- **0**: Blocking of all messages has been stopped successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md).

### Example

Example form 3, 4

```plaintext
pg VT12 vt12;
vt12.VTFunctionVTtoECU = 254;
vt12.SourceAdressOfActiveWSM = 1;
vt12.VisibleDataAlarmMaskID = 1000;
vt12.VisibleSoftKeyMaskID = 2000;
vt12.VTBusyCode1 = 0;
vt12.VTBusyCode2 = 0;
vt12.VTBusyCode3 = 0;
vt12.VTBusyCode4 = 0;
vt12.VTBusyCode8 = 0;
vt12.VTFunctionCode = 0;
if (VTIL_SetVTStatus(VT, 1000, vt12) < 0)
{
  TestStepFail("Failed to set VT Status");
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
