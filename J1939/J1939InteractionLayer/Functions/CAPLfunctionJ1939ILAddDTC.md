[J1939ILAddDTC](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILAddDTC.md)

**CAPL Functions** » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILAddDTC

# J1939ILAddDTC

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939ILAddDTC(dword pgn, dword spn, byte fmi, byte occurrenceCount); // form 1
long J1939ILAddDTC(dbNode node, dword pgn, dword spn, byte fmi, byte occurrenceCount); // form 2
```

## Description

This function adds a diagnostics trouble code (DTC) to a diagnostics message. If the diagnostics message with the specified PGN is requested, the response contains the added DTC. The added DTC uses conversion method 4 (SPN represented as Intel format for all 19 bits with the SPN Conversion Method set to 0). You can remove an added DTC with function [J1939IL_RemoveDTC](CAPLfunctionJ1939ILRemoveDTC.md).

**Note**: You can use this function only if support of J1939 Diagnostics is enabled by function [J1939ILActivateDiagnosticsSupport](CAPLfunctionJ1939ILActivateDiagnosticsSupport.md).

## Parameters

- **spn**: Suspect Parameter Number of the deactivated DTC, 0..524287.
- **fmi**: Failure Mode Indicator of the deactivated DTC, 0..31.
- **State**: Returns the current state of the DTC.
  - 0: DTC is not active and hasn’t been previously active.
  - 1: DTC is active.
  - 2: DTC has been previously active.
- **occurrenceCount**: Occurrence Count of the activated DTC, 0..127.
- **pgn**: Parameter Group Number (PGN) of the message which shall contain the DTC. Possible values are:
  - FECAh: DM1 - Active Diagnostic Trouble Codes
  - FECBh: DM2 - Previously Active Diagnostic Trouble Codes
  - FECFh: DM6 - Emission-Related Pending Diagnostic Trouble Codes
  - FED4h: DM12 - Emission-Related MIL-On Diagnostic Trouble Codes
  - FDB5h: DM23 - Emission-Related Previously MIL-On Diagnostic Trouble Codes
  - FD82h: DM27 - All Pending DTCs
  - FD80h: DM28 - Emission-Related Permanent Diagnostic Trouble Codes
  - 9F00h: DM35 - Immediate Fault Status
  - FD5Fh: DM41 - DTCs - A, Pending
  - FD5Eh: DM42 - DTCs - A, Confirmed and Active
  - FD5Dh: DM43 - DTCs - A, Previously Active
  - FD5Ch: DM44 - DTCs - B1, Pending
  - FD5Bh: DM45 - DTCs - B1, Confirmed and Active
  - FD5Ah: DM46 - DTCs - B1, Previously Active
  - FD59h: DM47 - DTCs - B2, Pending
  - FD58h: DM48 - DTCs - B2, Confirmed and Active
  - FD57h: DM49 - DTCs - B2, Previously Active
  - FD56h: DM50 - DTCs - C, Pending
  - FD55h: DM51 - DTCs - C, Confirmed and Active
  - FD54h: DM52 - DTCs - C, Previously Active
- **node**: Simulation node to apply the function.

## Return Values

- **0**: success
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)
- **-803**: Failed to activate DTC because diagnostics support is not activated

## Example

—

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
