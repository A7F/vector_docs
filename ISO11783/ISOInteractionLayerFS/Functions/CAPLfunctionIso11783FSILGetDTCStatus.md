[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILGetDTCStatus.md)

**CAPL Functions** » **ISO11783** » **File Server Interaction Layer (FS IL)** » **FSIL_GetDTCStatus**

# FSIL_GetDTCStatus

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long FSIL_GetDTCStatus(dword spn, byte fmi, word& state, word& occurrenceCount); // form 1
long FSIL_GetDTCStatus(dbNode node, dword spn, byte fmi, word& state, word& occurrenceCount); // form 2
```

## Description

This function returns the current occurrence count of a diagnostics trouble code (DTC). The function checks the list of active DTCs and the list of previously active DTCs for the specified DTC.

**Note**: You can use this function only if support of ISO11783 Diagnostics is enabled by function [FSIL_ActivateDiagnosticsSupport](CAPLfunctionIso11783FSILActivateDiagnosticsSupport.md).

## Parameters

- **spn**: Suspect Parameter Number of wanted DTC, 0..524287.
- **fmi**: Failure Mode Indicator of wanted DTC, 0.. 31.
- **state**: Returns the current state of the DTC.
  - 0: DTC is not active and hasn’t been previously active.
  - 1: DTC is active.
  - 2: DTC has been previously active.
- **occurrenceCount**: Returns the current occurrence count of the DTC. If DTC has never been active the returned occurrence count is 0.
- **node**: Simulation node to apply the function.

## Return Values

- **0**: success
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)
- **-803**: Failed to activate DTC because diagnostics support is not activated
- **-804**: Failed to get status of DTC because DTC not found

## Example

```plaintext
// Check the occurrence count and state for DTC with SPN=1208 and FMI=15
byte occurrenceCount, dtcState;
if (FSIL_GetDTCStatus(1208, 315, occurrenceCount, dtcState) == 0)
{
  If(dtcState == 1)
  {
    write("'EngPrefilterOilPress above normal (least severe)' is active, occurrence count is %d", occurrenceCount);
  }
  else If(dtcState == 2)
  {
    write("'EngPrefilterOilPress above normal (least severe)' has been previously active, occurrence count is %d", occurrenceCount);
  }
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)