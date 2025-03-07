[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILRemoveDTC.md)

**CAPL Functions** » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILRemoveDTC

# J1939ILRemoveDTC

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long J1939ILRemoveDTC(dword pgn, dword spn, byte fmi); // form 1`
- `long J1939ILRemoveDTC(dword pgn, dword spn); // form 2`
- `long J1939ILRemoveDTC(dbNode node, dword pgn, dword spn, byte fmi); // form 3`
- `long J1939ILRemoveDTC(dbNode node, dword pgn, dword spn); // form 4`

## Description

This function removes a diagnostics trouble code (DTC) from a diagnostics message which has been added by [J1939ILAddDTC](CAPLfunctionJ1939ILAddDTC.md).

Form 2 and 4 removes all DTCs with the specified SPN (regardless of FMI).

A removed DTC is no longer reported by the message if the message is requested.

Note: You can use this function only if support of J1939 Diagnostics is enabled by function [J1939ILActivateDiagnosticsSupport](CAPLfunctionJ1939ILActivateDiagnosticsSupport.md).

## Parameters

- **pgn**: Parameter Group Number (PGN) of the message which shall contain the DTC.
- **spn**: Suspect Parameter Number of the deactivated DTC, 0..524287.
- **fmi**: Failure Mode Indicator of the deactivated DTC, 0.. 31.
- **node**: Simulation node to apply the function.

## Return Values

- **0**: success
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)
- **-803**: Failed to activate DTC because diagnostics support is not activated
- **-804**: Failed to activate DTC because DTC not found

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)