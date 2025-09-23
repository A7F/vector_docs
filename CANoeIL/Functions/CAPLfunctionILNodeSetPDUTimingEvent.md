[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANoeIL/Functions/CAPLfunctionILNodeSetPDUTimingEvent.md)

## ILNodeSetPDUTimingEvent

[CAPL Functions](../../CAPLfunctions.md) » [CANoe IL](../CAPLfunctionsCANoeILOverview.md) » ILNodeSetPDUTimingEvent

**Valid for:** [CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

### Note

- This function is only supported if the following components are used:
  - AUTOSAR PDU Interaction Layer (AsrPDUIL.dll) at the corresponding transmit node in the Simulation Setup.
  - AUTOSAR ≥ 4.2 database.
- This function can be used in a global node outside the node context of the IL and in test modules.

### Function Syntax

```plaintext
long ILNodeSetPDUTimingEvent (dbMsg dbMessage, long TrueOrFalse, long enable, long repetitionPeriod, long repetitionCount, long debounceDelay, long disturbanceCount, long flags)
```

### Description

Overrides the defined event timing from the database. Possibly two timings (**False** and **True**) exist in parallel and are selected upon the current transmission mode of the PDU.

Only when an enabled event timing exists, the PDU can be transmitted regardless of any cyclic timing if any transfer property of a signal or signal group is firing/triggering.

### Parameters

- **dbMessage**: The symbolic name of a PDU in the database.
- **TrueOrFalse**:
  - 0: denotes the **False** timing
  - 1: denotes the **True** timing
  - 3: denotes the **True** and the **False** timing
- **enable**: Enables (**1**) or disables (**0**) the appropriate event timing.
- **repetitionPeriod**: Defines the period in [ms] for the possible repeated transmissions (only valid and used, when **repetitionCount** > **0**).
- **repetitionCount**: Defines the amount of repeated transmissions after the event occurred (**0** means only one transmission without any repetition).
- **debounceDelay**: Defines the minimal distance in [ms] of any two transmissions of this PDU (bandwidth control). **0** means that PDU can be transmitted as fast as possible and possibly produces bursts.
- **disturbanceCount**: Reserved/unused; should be set to **-1** ("infinite").
- **flags**: Reserved; should be set to **0**.

### Return Values

- **0**: No error
- **-10000**: Unspecific error
- **-10001**: Node or module not found
- **-10002**: No suitable module available
- **-10003**: Function is not supported by module
- **-10004**: Module returns illegal value
- **other**: Error in module

### Example

—
