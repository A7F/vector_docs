[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILActivateDTC.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_ActivateDTC

# TCIL_ActivateDTC

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_ActivateDTC(dword spn, byte fmi, dword options); // form 1`
- `long TCIL_ActivateDTC(dword spn, byte fmi, byte occurrenceCount, dword options); // form 2`
- `long TCIL_ActivateDTC(dbNode node, dword spn, byte fmi, dword options); // form 3`
- `long TCIL_ActivateDTC(dbNode node, dword spn, byte fmi, byte occurrenceCount, dword options); // form 4`

## Description

This function activates a diagnostics trouble code (DTC) and adds it to the list of active DTCs. This list with active DTCs is reported in the message DM1. The occurrence count of the DTC is either determined automatically (form 1, 3) or set to a specific value (form 2, 4). Calling form 1 or 3 of the function increments the occurrence count of the DTC with every call. The DTC is uniquely identified by the combination of SPN and FMI. The activated DTC uses conversion method 4 (SPN represented as Intel format for all 19 bits with the SPN Conversion Method set to 0). If a previously active DTC (reported with DM2) is activated again then it is removed from the list of previous active DTCs (and therefore no more reported in message DM2). You can deactivate an activated DTC with [TCIL_DeactivateDTC](CAPLfunctionIso11783TCILDeactivateDTC.md).

**Note**: You can use this function only if support of ISO11783 Diagnostics is enabled by function [TCIL_ActivateDiagnosticsSupport](CAPLfunctionIso11783TCILActivateDiagnosticsSupport.md).

## Parameters

- **spn**: Suspect Parameter Number of the activated DTC, 0..524287.
- **fmi**: Failure Mode Indicator of the activated DTC, 0..31.
- **options**:
  - Bit 0 = 0: Send message DM1 as soon as possible.
  - Bit 0 = 1: Send message DM1 with next cycle.
- **occurrenceCount**: Occurrence Count of the activated DTC, 0..127. If a form without this parameter is used, then the occurrence count is determined automatically.
- **node**: Simulation node to apply the function.

## Return Values

- **0**: success
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)
- **-803**: Failed to activate DTC because diagnostics support is not activated

## Example

—

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
