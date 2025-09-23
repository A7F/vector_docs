# TestValidatePhysValueUInt

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long TestValidatePhysValueFloat(char aTestStep[], valueHandle * value, qword awaitedValue);
```

## Description

Checks the phys encoding of a **valueHandle** value against the condition. This function can only be used for **valueHandles** with an unsigned integer data type. It cannot be used for system variables or bus system signals.

The test step is evaluated as either passed or failed depending on the results.

## Parameters

- **aTestStep**: Name of the test step for the test report.
- **value**: Value handle of a communication object or distributed object.
- **awaitedValue**: Value which is awaited.

## Return Values

- **-1**: General error
- **0**: Correct functionality

## Example

```plaintext
long ret;
ret = testValidatePhysValueUInt("Validate error signal", ErrorSignal[LeftMirror], 1);
```

[TestValidatePhysValueFloat](CAPLfunctionTestValidatePhysValueFloat.md) • [TestValidatePhysValueSInt](CAPLfunctionTestValidatePhysValueSInt.md)
