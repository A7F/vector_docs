# TestWaitForUnlockEcu

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../../Diagnostics/CAPLfunctionsDiagnosticsOverview.md) » TestWaitForUnlockEcu

Valid for: CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestWaitForUnlockEcu(long securityLevel); // form 1`
- `long TestWaitForUnlockEcu(char ecuQualifier[], dword securityLevel); // form 2`

## Description

This function tries to unlock an ECU. It requests a seed, calculates the key with the Seed & Key DLL, and sends it to the ECU. The Seed & Key DLL must be configured in the [diagnostic configuration](../../../CANoeCANalyzer/Diagnostics/Special/DiagSecurityDLLAccess.md) dialog.

The message exchange can be monitored with [on DiagRequest](../../Diagnostics/EventProcedures/CAPLfunctionOnDiagRequest.md)/[on DiagResponse](../../Diagnostics/EventProcedures/CAPLfunctionOnDiagResponse.md) event handler.

## Parameters

- **securityLevel**: The required security level.
- **ecuQualifier**: Qualifier of the ECU or target as set in the diagnostic configuration dialog for the respective diagnostic description.

## Return Values

On success 0, otherwise [error code](../../Diagnostics/CAPLfunctionsDiagnosticsErrorCode.md).

## Example

—

[Test Feature Set CAPL Functions](../CAPLfunctionsTFSOverview.md)
