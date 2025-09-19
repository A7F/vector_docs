# ILNodeDisturbSignalGroupUpdateBit

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

### Note
- This function is not available for all OEM add-ons — depends on the CANoeIL.
- This function can be used in a global node outside the node context of the IL and in test modules.

## Function Syntax

```plaintext
long ILNodeDisturbSignalGroupUpdateBit(dbMsg aMessage, char aSigGroupName[], long disturbanceMode, long disturbanceCount, long disturbanceValue); // form 1
long ILNodeDisturbSignalGroupUpdateBit(char aMessageName[], char aSigGroupName[], long disturbanceMode, long disturbanceCount, long disturbanceValue); // form 2
long ILNodeDisturbSignalGroupUpdateBit (char aSignalGroupName[], long disturbanceMode, long disturbanceCount, long disturbanceValue); // form 3
```

## Description

Modifies the update bit of a signal group. Different fault injections are possible. This function influences a simulation node with an assigned CANoe interaction layer.

## Parameters

- **aMessage**: The symbolic name of message in the database containing the signal group.
- **aMessageName**: The name of message in the database containing the signal group. Supported qualification patterns for form 2: [DBName::][NodeName::]aMessageName
- **aSigGroupName**: Name of the signal group using an update bit. Supported qualification patterns for form 3: [DBName::][NodeName::][MessageName::]aSignalgroupName
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
// Sets the Signal Group Update Bit to 0

variables {
  long disturbanceMode  = 0; // The disturbance uses the value in disturbanceValue as Update Bit.
  int disturbanceCount  = 100;
  long disturbanceValue = 0;
}

on key 'a'{
  ILNodeDisturbSignalGroupUpdateBit(Message_A, "SignalGroup_A", disturbanceMode, disturbanceCount, disturbanceValue);
}
```
