[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILResetTCStatus.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_ResetTCStatus

# TCIL_ResetTCStatus

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_ResetTCStatus(); // form 1`
- `long TCIL_ResetTCStatus(dbNode tc); // form 2`

## Description

This function reverts changes made by [TCIL_SetTCStatus](CAPLfunctionIso11783TCILSetTCStatus.md) and turns back to the default behavior of the Task Controller IL.

## Parameters

- **tc**: TC simulation node to apply the function

## Return Values

—

## Example

Example form 2

```plaintext
pg TC12 tc12;
tc12.TCFunctionTCtoECU = 254;
tc12.SourceAdressOfActiveWSM = 1;
tc12.VisibleDataAlarmMaskID = 1000;
tc12.VisibleSoftKeyMaskID = 2000;
tc12.TCBusyCode1 = 0;
tc12.TCBusyCode2 = 0;
tc12.TCBusyCode3 = 0;
tc12.TCBusyCode4 = 0;
tc12.TCBusyCode8 = 0;
tc12.TCFunctionCode = 0;
if (TCIL_SetTCStatus( TC, 1000, tc12 ) < 0)
{
  TestStepFail("Failed to set TC Status");
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)