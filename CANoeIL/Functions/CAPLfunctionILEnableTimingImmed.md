[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANoeIL/Functions/CAPLfunctionILEnableTimingImmed.md)

[CAPL Functions](../../CAPLfunctions.md) » [CANoe IL](../CAPLfunctionsCANoeILOverview.md) » ILEnableTimingImmed

# ILEnableTimingImmed

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**

- This function is not available for all OEM add-ons — depends on the CANoeIL.
- This function can be used in a global node outside the node context of the IL.

## Function Syntax

```plaintext
long ILEnableTimingImmed (char pduName[], int enable);
```

## Description

Controls the immediate timing of PDUs. The immediate timing can be enabled/disabled. This function influences a simulation node with an assigned CANoe interaction layer.

## Parameters

- **aPDUName**: Name of the PDU that should be modified.
- **enable**: 
  - 0 = disable
  - 1 = enable

## Return Values

- **0**: No error.
- **-1**: General error.

## Example

```plaintext
// Disables the PDU Timing for 2000 ms

variables {
  int enable = 0;
  msTimer WaitTimer;
}

on key 'a'{
  enable = 0;
  ILEnableTimingImmed ("PDU_A", enable);
  SetTimer(WaitTimer,2000);
}

on Timer WaitTimer {
  enable = 1;
  ILEnableTimingImmed ("PDU_A", enable);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)