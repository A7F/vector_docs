# TestValidateImplValue

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long TestValidateImplValue(char aTestStep[], valueHandle * value, ValueType awaitedValue);
```

## Description

Checks the impl encoding of a **valueHandle** value against the condition. This function can only be used for **valueHandles** with a ValueType data type. It cannot be used for system variables or bus system signals.

The test step is evaluated as either passed or failed depending on the results.

## Parameters

- **aTestStep**: Name of the test step for the test report.
- **value**: Value handle of a communication object or distributed object.
- **awaitedValue**: Value which is awaited.

## Return Values

- **-1**: General error
- **0**: Correct functionality

## Example

```c
struct Mirrors::Position pos;
long ret;
pos.x = 100;
pos.y = 50;
ret = testValidateImplValue("Validate position", MirrorAdjustment.consumerSide[0,0].CurrentPosition, pos);
```

[TestValidateImplValueFloat](CAPLfunctionTestValidateImplValueFloat.md) • [TestValidateImplValueSInt](CAPLfunctionTestValidateImplValueSInt.md) • [TestValidateImplValueString](CAPLfunctionTestValidateImplValueString.md) • [TestValidateImplValueUInt](CAPLfunctionTestValidateImplValueUInt.md)
