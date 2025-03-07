[J1939ILSetLampStatus](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILSetLampStatus.md)

**CAPL Functions** » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILSetLampStatus

# J1939ILSetLampStatus

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long J1939ILSetLampStatus(dword pgn, word lampStatus); // form 1`
- `long J1939ILSetLampStatus(dbNode node, dword pgn, word lampStatus); // form 2`

## Description

This function sets the lamp status of a diagnostics message. If the diagnostics message with the specified PGN is requested, the response contains the specified lamp status. The lamp status is reported by the first two bytes of a diagnostics message.

**Note**: The diagnostics message is only sent if support of J1939 Diagnostics is enabled by function [J1939ILActivateDiagnosticsSupport](CAPLfunctionJ1939ILActivateDiagnosticsSupport.md).

## Parameters

- **pgn**: Parameter Group Number (PGN) of the message which shall contain the lamp status. Possible values are:
  - **FECAh**: DM1 - Active Diagnostic Trouble Codes
  - **FECBh**: DM2 - Previously Active Diagnostic Trouble Codes
  - **FECFh**: DM6 - Emission-Related Pending Diagnostic Trouble Codes
  - **FED4h**: DM12 - Emission-Related MIL-On Diagnostic Trouble Codes
  - **FDB5h**: DM23 - Emission-Related Previously MIL-On Diagnostic Trouble Codes
  - **FD82h**: DM27 - All Pending DTCs
  - **FD80h**: DM28 - Emission-Related Permanent Diagnostic Trouble Codes
  - **9F00h**: DM35 - Immediate Fault Status
  - **FD5Fh**: DM41 - DTCs - A, Pending
  - **FD5Eh**: DM42 - DTCs - A, Confirmed and Active
  - **FD5Dh**: DM43 - DTCs - A, Previously Active
  - **FD5Ch**: DM44 - DTCs - B1, Pending
  - **FD5Bh**: DM45 - DTCs - B1, Confirmed and Active
  - **FD5Ah**: DM46 - DTCs - B1, Previously Active
  - **FD59h**: DM47 - DTCs - B2, Pending
  - **FD58h**: DM48 - DTCs - B2, Confirmed and Active
  - **FD57h**: DM49 - DTCs - B2, Previously Active
  - **FD56h**: DM50 - DTCs - C, Pending
  - **FD55h**: DM51 - DTCs - C, Confirmed and Active
  - **FD54h**: DM52 - DTCs - C, Previously Active

- **lampStatus**: New lamp status of the diagnostics message.
  - **Byte 1**:
    - Bits 8-7: Malfunction Indicator Lamp
    - Bits 6-5: Red Stop Lamp
    - Bits 4-3: Amber Warning Lamp
    - Bits 2-1: Protect Lamp
  - **Byte 2**:
    - Bits 8-7: Flash Malfunction Indicator Lamp
    - Bits 6-5: Flash Red Stop Lamp
    - Bits 4-3: Flash Amber Warning Lamp
    - Bits 2-1: Flash Protect Lamp

- **node**: Simulation node to apply the function.

## Return Values

- **0**: success
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)
- **-803**: Failed to activate DTC because diagnostics support is not activated

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)