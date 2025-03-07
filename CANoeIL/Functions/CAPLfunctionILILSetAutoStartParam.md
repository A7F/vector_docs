[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANoeIL/Functions/CAPLfunctionILILSetAutoStartParam.md)

**CAPL Functions** » **CANoe IL** » **ILSetAutoStartParam**

# ILSetAutoStartParam

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long ILSetAutoStartParam(dword autoStartParam)
```

## Description

Defines the behavior of the interaction layer at the start of measurement. If used at all, the function must be called within the [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md) event handler of a CAPL program.

## Parameters

- **autoStartParam**: State after measurement start (other values are reserved):
  - 0: Waiting
  - 1: Stopped
  - 2: Starting

**Note**: The default behavior (i.e. when `ILSetAutoStartParam` is omitted) is analogous to `ILSetAutoStartParam(2)`.

## Return Values

- **0**: No error
- **-1**: General error

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)