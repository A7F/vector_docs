# ILNodeDisturbPduUpdateBit

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**

- This function is not available for all OEM add-ons — depends on the CANoeIL.
- This function can be used in a global node outside the node context of the IL and in test modules.

## Function Syntax

```plaintext
long ILNodeDisturbPduUpdateBit(dbMsg aPDU, long disturbanceCount, long disturbanceValue);
long ILNodeDisturbPduUpdateBit(char aPDUName[], long disturbanceCount, long disturbanceValue);
```

## Description

This function modifies the update bit of a PDU. Different fault injections are possible. This function influences a simulation node with an assigned CANoe interaction layer.

## Parameters

- **aPDU**: PDU, whose update bits will be disturbed.
- **aPDUName**: Name of the PDU, whose update bits will be disturbed.
  - Supported qualification patterns: [DBName::][NodeName::]aPDUName
- **disturbanceCount**:
  - `-1`: Infinite.
  - `0`: Stops the disturbance, e.g., an infinite disturbance.
  - `n`: Number of disturbances.
- **updateBit**: Desired disturbance value (0,1).

## Return Values

- **0**: No error
- **-1**: General error.

## Example

```plaintext
// Sets the PDU Update Bit 100 times to 0

variables {
  int disturbanceCount = 100;
  int updateBit = 0;
}

on key 'a'{
  ILNodeDisturbPduUpdateBit("PDU_A", disturbanceCount, updateBit);
}
```
