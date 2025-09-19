[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILDeactivateDTC.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_DeactivateDTC**

# VTIL_DeactivateDTC

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_DeactivateDTC(dword spn, byte fmi, dword options); // form 1`
- `long VTIL_DeactivateDTC(dword spn, dword options); // form 2`
- `long VTIL_DeactivateDTC(dbNode node, dword spn, byte fmi, dword options); // form 3`
- `long VTIL_DeactivateDTC(dbNode node, dword spn, dword options); // form 4`

## Description

This function deactivates a diagnostics trouble code (DTC) and removes it from the list of active DTCs.

A deactivated DTC is no longer reported in message DM1 (Active Diagnostic Trouble Codes, PGN FECAh) but it is moved to the list of previously active DTCs and is reported in the requestable message DM2 (Previously Active Diagnostic Trouble Codes, PGN FECBh).

**Note**: You can use this function only if support of ISO11783 Diagnostics is enabled by function [VTIL_ActivateDiagnosticsSupport](CAPLfunctionIso11783VTILActivateDiagnosticsSupport.md).

## Parameters

- **spn**: Suspect Parameter Number of the deactivated DTC, 0..524287.
- **fmi**: Failure Mode Indicator of the deactivated DTC, 0..31.
- **options**:
  - Bit 0 = 0: Send message DM1 as soon as possible.
  - Bit 0 = 1: Send message DM1 with next cycle.
- **node**: Simulation node to apply the function.

## Return Values

- **0**: success
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)
- **-803**: Failed to activate DTC because diagnostics support is not activated
- **-804**: Failed to activate DTC because DTC not found

## Example

—

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
