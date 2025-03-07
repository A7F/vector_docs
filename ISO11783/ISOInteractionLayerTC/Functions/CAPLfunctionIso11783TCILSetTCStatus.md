[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILSetTCStatus.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_SetTCStatus**

# TCIL_SetTCStatus

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_SetTCStatus(dword cycleTime); // form 1`
- `long TCIL_SetTCStatus(dword cycleTime, pg PD); // form 2`
- `long TCIL_SetTCStatus(dbNode tc, dword cycleTime); // form 3`
- `long TCIL_SetTCStatus(dbNode tc, dword cycleTime, pg pgPD); // form 4`

## Description

This function changes the content and cycle time of the TC Status message.

Form 1 and 3: The content of TC Status message stays unchanged; only the cycle time is changed.

## Parameters

- **tc**: TC simulation node to apply the function
- **cycleTime**: Cycle time of the TC Status message [ms] (default: 1000)
- **pgPD**: Content of this message is used by the following TC Status messages sent by the TC IL

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 3

```c
pg PD pgPD;
pgPD.TCFunctionTCtoECU = 254;
pgPD.SourceAdressOfActiveWSM = 1;
pgPD.VisibleDataAlarmMaskID = 1000;
pgPD.VisibleSoftKeyMaskID = 2000;
pgPD.TCBusyCode1 = 0;
pgPD.TCBusyCode2 = 0;
pgPD.TCBusyCode3 = 0;
pgPD.TCBusyCode4 = 0;
pgPD.TCBusyCode8 = 0;
pgPD.TCFunctionCode = 0;
if (TCIL_SetTCStatus(TC, 1000, pgPD) < 0)
{
  TestStepFail("Failed to set TC Status");
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)