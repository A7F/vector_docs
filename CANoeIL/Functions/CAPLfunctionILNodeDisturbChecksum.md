# ILNodeDisturbChecksum

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Note

- This function is not available for all OEM add-ons — depends on the CANoeIL.
- This function can be used in a global node outside the node context of the IL and in test modules.

## Function Syntax

```plaintext
long ILNodeDisturbChecksum(dbMsg aMessage, char aSigGroupName[], long checksumType, long disturbanceMode, long disturbanceCount, long disturbanceValue); // form 1

long ILNodeDisturbChecksum(char aMessageName[], char aSigGroupName[], long checksumType, long disturbanceMode, long disturbanceCount, long disturbanceValue); // form 2

long ILNodeDisturbChecksum(char sigGroupName[], long type, long disturbanceMode, long disturbanceCount, long disturbanceValue); // form 3

long ILNodeDisturbChecksum64(dbMsg aMessage, char aSigGroupName[], long checksumType, long disturbanceMode, long disturbanceCount, qword disturbanceValue); // form 4

long ILNodeDisturbChecksum64(char aMessageName[], char aSigGroupName[], long checksumType, long disturbanceMode, long disturbanceCount, qword disturbanceValue); // form 5

long ILNodeDisturbChecksum64(char sigGroupName[], long type, long disturbanceMode, long disturbanceCount, qword disturbanceValue); // form 6
```

## Description

This function modifies the checksum. Different fault injections are possible. This function influences a simulation node with an assigned CANoe interaction layer.

Use the ILNodeDisturbChecksum64 functions for 64-bit CRC values (e.g., in case of AUTOSAR PROFILE_07).

## Parameters

- **aMessage**: Message or PDU that should be modified.
- **aMsgName**: Name of the message or PDU that should be modified. Supported qualification patterns for form 2: [DBName::][NodeName::]aMessageName
- **aSigGroupName**: Some systems assign a checksum to a signal group. When specifying the signal group you can apply the disturbance to a dedicated signal group within a message or PDU. Use an empty character array if the checksum of the whole message or PDU should be affected. Supported qualification patterns for form 3: [DBName::][NodeName::][MessageName::]aSignalgroupName
- **checksumType**: The possible values are described in the corresponding OEM add-on manual.
- **disturbanceMode**: Identifies the disturbance mode:
  - **0**: Value - The disturbance uses the value in `disturbanceValue` as checksum.
  - **1**: Freeze - The current checksum value is transmitted.
  - **2**: Random - A random value is transmitted as checksum.
  - **3**: Offset - The checksum is incremented with the value in `disturbanceValue`.
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
// Disturbs the Checksum of a specific PDU, disturbance pattern: 20x fix value

variables {
  long checksumType = 0; // The possible values are described in the corresponding OEM add-on manual.
  long disturbanceMode = 0; // The disturbance uses the value in disturbanceValue as checksum.
  long disturbanceCount = 20;
  long disturbanceValue = 10;
}

on key 'a' {
  ILNodeDisturbChecksum("PDU_A", "", checksumType, disturbanceMode, disturbanceCount, disturbanceValue);
}
```
