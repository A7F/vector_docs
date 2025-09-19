# ARILSetPDUTimingEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long ARILSetPDUTimingEvent (dbMsg dbMessage, long TrueOrFalse, long enable, long repetitionPeriod, long repetitionCount, long debounceDelay, long disturbanceCount, long flags);
```

## Description

Overrides the defined **event-timing** from the database. Possibly two timings (**False** and **True**) exist in parallel and are selected upon the current transmission mode of the PDU.

Only when an enabled event-timing exists, the PDU can be transmitted regardless of any cyclic timing if any transfer property of a signal or signal group is firing/triggering.

## Parameters

- **dbMessage**: The symbolic name of a PDU in the database.
- **TrueOrFalse**:
  - 0: denotes the **False** timing
  - 1: denotes the **True** timing
  - 3: denotes the **True** and the **False** timing
- **enable**: Enables (**1**) or disables (**0**) the appropriate event timing.
- **repetitionPeriod**: Defines the period in [ms] for the possible repeated transmissions (only valid and used, when **repetitionCount** > **0**).
- **repetitionCount**: Defines the amount of repeated transmissions after the event occurred (**0** means only one transmission without any repetition).
- **debounceDelay**: Defines the minimal distance in [ms] of any two transmissions of this PDU (bandwidth control). **0** means that PDU can be transmitted as fast as possible and possibly produces bursts.
- **disturbanceCount**: Reserved/unused; should be set to **-1** (**infinite**).
- **flags**: Reserved; should be set to **0**.

## Return Values

- **0**: No error.
- **Others**: [Error in module.](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md)

## Example

—
