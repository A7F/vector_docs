# ILNodeDisturbSignalUpdateBit

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

**Note**

- This function is not available for all OEM add-ons — depends on the CANoeIL.
- This function can be used in a global node outside the node context of the IL and in test modules.

## Function Syntax

```plaintext
long ILNodeDisturbSignalUpdateBit(dbSignal aSignal, long disturbanceMode, long disturbanceCount, long disturbanceValue);
long ILNodeDisturbSignalUpdateBit(char aMessageName[], char aSignalName[], long disturbanceMode, long disturbanceCount, long disturbanceValue);
```

## Description

This function modifies the update bit of a signal. Different fault injections are possible. This function influences a simulation node with an assigned CANoe interaction layer.

## Parameters

- **aMessageName**: Name of the message or PDU that should be modified.
- **aSignalName**: Name of the update bit signal.
- **aSignal**: Update bit signal.
- **disturbanceMode**: Identifies the disturbance mode:
  - **0**: Value - The disturbance uses the value in `disturbanceValue` as update bit.
  - **1**: Freeze - The current update bit value is transmitted.
  - **2**: Random - A random value is transmitted as update bit.
- **disturbanceCount**:
  - **-1**: Infinite.
  - **0**: Stops the disturbance, e.g., an infinite disturbance.
  - **n**: Number of disturbances.
- **disturbanceValue**: This value is used in combination with the `disturbanceMode`.

## Return Values

- **0**: No error
- **-10000**: Unspecific error
- **-10001**: Node or module not found
- **-10002**: No suitable module available
- **-10003**: Function is not supported by module
- **-10004**: Module returns illegal value
- **other**: Error in module

## Example

```plaintext
// Sets the Signal Update Bit to 0

variables {
  long disturbanceMode = 0; // The disturbance uses the value in disturbanceValue as Update Bit.
  int disturbanceCount = 100;
  long disturbanceValue = 0;
}

on key 'a'{
  ILNodeDisturbSignalUpdateBit("PDU_A", "Signal_A", disturbanceMode, disturbanceCount, disturbanceValue);
}
```
