[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/AUTOSARpduIL/Functions/CAPLfunctionARILSetPDUTimingCyclic.md)

## CAPL Functions » AUTOSAR PDU IL » ARILSetPDUTimingCyclic

### ARILSetPDUTimingCyclic

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
long ARILSetPDUTimingCyclic (dbMsg dbMessage, long TrueOrFalse, long offset, long period, long disturbanceCount, long flags);
```

### Description

Overrides the defined **cyclic-timing** from the database. Possibly two timings (**False** and **True**) exist in parallel and are selected upon the current transmission mode of the PDU.

### Parameters

- **dbMessage**: The symbolic name of a PDU in the database.
- **TrueOrFalse**:
  - 0: denotes the **False** timing
  - 1: denotes the **True** timing
  - 3: denotes the **True** and the **False** timing
- **offset**: Defines the delay in [ms] from now when the first cyclic transmission will start.
- **period**: Defines the period in [ms] for the cyclic transmission.
- **disturbanceCount**: Reserved/unused; should be set to **-1** (**infinite**).
- **flags**: Reserved; should be set to **0**.

### Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

### Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)