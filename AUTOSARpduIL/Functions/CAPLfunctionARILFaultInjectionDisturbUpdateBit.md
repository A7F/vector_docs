# ARILFaultInjectionDisturbUpdateBit

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long ARILFaultInjectionDisturbUpdateBit (dbSignal, long disturbanceMode, long disturbanceCount, long disturbanceValue);
```

```plaintext
long ARILFaultInjectionDisturbUpdateBit (dbMsg dbMessage, char signalGroupName[], long disturbanceMode, long disturbanceCount, long disturbanceValue);
```

## Description

Disturbs the Update Bit of a signal or signal group (see [Update Bit](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILFeatures.md#UpdateBit)).

The function without the parameter for the signal group will only disturb update bits of signals.

The function with the parameter for the signal group will only disturb update bits of signal groups.

## Parameters

- **dbSignal**: The symbolic name of an update bit signal in the database. The update bit signal names have the same name as the signal or the signal group they control followed by the suffix **_UB**.
- **dbMessage**: The symbolic name of a PDU in the database.
- **signalGroupName**: The symbolic full name of the signal group.
- **disturbanceMode**: Defines the function for the disturbance:
  - **0**: Value - Sets the update bit fix to the value of parameter **disturbanceValue**.
  - **1**: Freeze - Current signal value is used (**disturbanceValue** is not used).
  - **2**: Random - Random value is used for setting and resetting the update bit (**disturbanceValue** is not used).
  - **3**: Opposite - Signal value is set when update bit should be cleared and is cleared when update bit should be set.
  - **4**: Random Set - The update bit will randomly be not set but will always after transmission be cleared (**disturbanceValue** is not used).
  - **5**: Random Reset - The update bit will always correctly be set but randomly not reset (**disturbanceValue** is not used).
- **disturbanceCount**: 
  - **-1**: Infinite - Disturbance is continuously applied.
  - **0**: Stop - An active disturbance is stopped and the CRC will be calculated again appropriately.
  - **n > 0**: Count - Do exactly n disturbances.
- **disturbanceValue**: According to the disturbance mode the update bit will optionally be set to this value.

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—
