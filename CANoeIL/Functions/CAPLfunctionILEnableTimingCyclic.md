# ILEnableTimingCyclic

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**

- This function is not available for all OEM add-ons — depends on the CANoeIL.
- This function can be used in a global node outside the node context of the IL.

## Function Syntax

`long ILEnableTimingCyclic(char pduName[], int enable)`

## Description

Controls the cyclic timing of PDUs. The cyclic timing can be enabled/disabled. This function influences a simulation node with an assigned CANoe interaction layer.

## Parameters

- **aPDUName**: Name of the PDU that should be modified.
- **enable**:
  - 0 = disable
  - 1 = enable

## Return Values

- **0**: No error.
- **-1**: General error.

## Example

```c
// Disables the PDU Timing for 2000 ms

variables {
  int enable = 0;
  msTimer WaitTimer;
}

on key 'a'{
  enable = 0;
  ILEnableTimingCyclic ("PDU_A", enable);
  SetTimer(WaitTimer,2000);
}

on Timer WaitTimer {
  enable = 1;
  ILEnableTimingCyclic ("PDU_A", enable);
}
```
