# ILNodeSetOperationMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**

- This function is not available for all OEM add-ons — depends on the CANoeIL.
- This function can be used in a global node outside the node context of the IL and in test modules.

## Function Syntax

- `long ILNodeSetOperationMode(char aNodeName[], long mode, long param); // form 1`
- `long ILNodeSetOperationMode(dbMsg message, char signalGroupName[], long mode, long param); //(2)`
- `long ILNodeSetOperationMode(dbSignal signal, long mode, long param); // form 3`

## Description

- **Form 1:** Sets specific operation mode in the interaction layer of the specified simulation node. The specified node must be in the current bus context. In all other cases the function has no effect and will return with an error.
- **Form 2:** Sets specific operation mode in the interaction layer for the specified signal group of the specified message.
- **Form 3:** Sets specific operation mode in the interaction layer for the specified signal.

## Parameters

- **aNodeName:** Name of the node of which the specific operation mode should be set.
  - Supported qualification patterns for form 1: [DBName::]aNodeName
- **signalGroupName:** Name of the signal group.
- **message:** Message of which the specific operation mode should be set.
- **signal:** Name of the update bit signal of which the specific operation mode should be set.
- **mode:** 0: influences update bits; other values have currently no effect and are reserved.
- **param:** The effect of `param` depends on the parameter `mode`:

  - **Syntax form 1:**
    - **Mode Value 0:**
      - 0: all update bits will be set or reset depending on the signal updates
      - 1: all update bits will always be sent with value = 1

  - **Syntax form 2:**
    - **Mode Value 0:**
      - 0: the update bit of the signal group will be set or reset depending on the signal updates
      - 1: the update bit of the signal group will always be sent with value = 1

  - **Syntax form 3:**
    - **Mode Value 0:**
      - 0: the update bit will be set or reset depending on the signal updates
      - 1: the update bit will always be sent with value = 1

## Return Values

- **0:** No error
- **-10000:** Unspecific error
- **-10001:** Node or module not found
- **-10002:** No suitable module available
- **-10003:** Function is not supported by module
- **-10004:** Module returns illegal value
- **other:** Error in module

## Example

—
