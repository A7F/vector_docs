# ILNodeSetPDUAsrTxMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

### Note
- This function is only supported if the following components are used:
  - AUTOSAR PDU Interaction Layer (AsrPDUIL.dll) at the corresponding transmit node in the Simulation Setup.
  - AUTOSAR ≥ 4.2 database.
- This function can be used in a global node outside the node context of the IL and in test modules.

## Function Syntax

```plaintext
long ILNodeSetPDUAsrTxMode (dbMsg dbMessage, long mode, long disturbanceCount, long flags)
```

## Description

Overrides the current valid transmission mode of the PDU. The transmission mode can be **False** or **True**. The current transmission mode is defined by or-ing the current data filter condition value of all signal values of the PDU.

## Parameters

- **dbMessage**: The symbolic name of a PDU in the database.
- **mode**: Sets the **True** timing (**1**) or the **False** timing (**0**) to be active (regardless of the signal values).
- **disturbanceCount**: Reserved/unused; should be set to **-1** ("infinite").
- **flags**: Reserved; should be set to **0**.

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
