# ILNodeControlResume

**Valid for**: CANoe DE • CANoe4SW DE

**Note**

- This function is not available for all OEM add-ons — depends on the CANoeIL.
- This function can be used in a global node outside the node context of the IL and in test modules.

## Function Syntax

```plaintext
long ILNodeControlResume(char aNodeName[]); // form 1
long ILNodeControlResume(char aNodeName[],dword flags); // form 2
```

## Description

Restarts the interaction layer of the specified simulation node. Cyclical sending of messages is restarted. The specified node must be in the current bus context. In all other cases the function has no effect and will return with an error.

## Parameters

- **aNodeName**: Name of the node of which the interaction layer should be started.
- **flags**:
  - 0: Signals/PDUs are sent with the last current values (of the latest updated buffer content).
  - 1: Signals/PDUs are sent with **Init** value, corresponds to form 1.

## Return Values

- **0**: No error
- **-10000**: Unspecific error
- **-10001**: Node or module not found
- **-10002**: No suitable module available
- **-10003**: Function is not supported by module
- **-10004**: Module returns illegal value
- **other**: Error in module

## Example

—
