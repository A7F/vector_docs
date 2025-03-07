[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/AUTOSARpduIL/Functions/CAPLfunctionARILResetPDUTimingCyclic.md)

**CAPL Functions** » [AUTOSAR PDU IL](../CAPLfunctionsAUTOSARpduILOverview.md) » ARILResetPDUTimingCyclic

# ARILResetPDUTimingCyclic

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long ARILResetPDUTimingCyclic (dbMsg dbMessage, long TrueOrFalse);
```

## Description

Resets the **cyclic-timing** to the values from the database. Possibly two timings (**False** and **True**) exist in parallel and are selected upon the current transmission mode of the PDU.

## Parameters

- **dbMessage**: The symbolic name of a PDU in the database.
- **TrueOrFalse**:
  - 0: denotes the **False** timing
  - 1: denotes the **True** timing
  - 3: denotes the **True** and the **False** timing.

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

•  Technical References are only available in English

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)