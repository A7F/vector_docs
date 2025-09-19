# ILNodeDisturbAllUpdateBits

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

### Note

- This function is not available for all OEM add-ons — depends on the CANoeIL.
- This function can be used in a global node outside the node context of the IL and in test modules.

## Function Syntax

```plaintext
long ILNodeDisturbAllUpdateBits(dbNode aNode, long flags, long disturbanceMode, long disturbanceCount, long disturbanceValue);
long ILNodeDisturbAllUpdateBits(char aNodeName[], long flags, long disturbanceMode, long disturbanceCount, long disturbanceValue);
```

## Description

Modifies all update bits of signals/signal groups of a node. Different fault injections are possible. This function influences a simulation node with an assigned CANoe interaction layer.

## Parameters

- **aNode**: The symbolic name of a node in the database, whose update bits will be disturbed.
- **aNodeName**: The name of a node in the database, whose update bits will be disturbed.
- **flags**: The lowest two bits of this parameter are evaluated:
  - `0`: Update bits of signals and signal groups are disturbed.
  - `1`: Only signal update bits are disturbed.
  - `2`: Only signal group update bits are disturbed.
- **disturbanceMode**: Identifies the disturbance mode:
  - `0`: Value - The disturbance uses the value in `disturbanceValue` as update bit.
  - `1`: Freeze - The current update bit value is transmitted.
  - `2`: Random - A random value is transmitted as update bit.
- **disturbanceCount**:
  - `-1`: Infinite.
  - `0`: Stops the disturbance, e.g., an infinite disturbance.
  - `n`: Number of disturbances.
- **disturbanceValue**: This value is used in combination with the `disturbanceMode`.

## Return Values

- `0`: No error
- `-10000`: Unspecific error
- `-10001`: Node or module not found
- `-10002`: No suitable module available
- `-10003`: Function is not supported by module
- `-10004`: Module returns illegal value
- `other`: Error in module

## Example

—
