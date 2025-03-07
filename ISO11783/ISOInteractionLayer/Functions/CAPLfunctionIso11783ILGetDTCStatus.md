[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILGetDTCStatus.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » **Iso11783IL_GetDTCStatus**

# Iso11783IL_GetDTCStatus

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_GetDTCStatus(dword spn, byte fmi, word& state, word& occurrenceCount); // form 1
long Iso11783IL_GetDTCStatus(dbNode node, dword spn, byte fmi, word& state, word& occurrenceCount); // form 2
```

## Description

This function returns the current occurrence count of a diagnostics trouble code (DTC).

The function checks the list of active DTCs and the list of previously active DTCs for the specified DTC.

**Note**: You can use this function only if support of ISO11783 Diagnostics is enabled by function [Iso11783IL_ActivateDiagnosticsSupport](CAPLfunctionIso11783ILActivateDiagnosticsSupport.md).

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

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)