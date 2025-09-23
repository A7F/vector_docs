# TestValidateImplValueInRangeUInt

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long TestValidateImplValueInRangeUInt (char aTestStep[], valueHandle * value, qword aLowLimit, qword aHighLimit);
```

## Description

Checks the impl encoding of a **valueHandle** value against the condition. This function can only be used for **valueHandles** with an unsigned integer data type. It cannot be used for system variables or bus system signals.

aLowLimit \<= Value \<= aHighLimit

The test step is evaluated as either passed or failed depending on the results.

## Parameters

- **aTestStep**: Name of the test step for the test report.
- **value**: Value handle of a communication object or distributed object.
- **aLowLimit**: Lower limit of the value.
- **aHighLimit**: Higher limit of the value.

## Return Values

- **-2**: Type of the valueHandle is not valid
- **-1**: General error
- **0**: Correct functionality

## Example

```plaintext
long ret;
ret = testValidateImplValueInRangeUInt(MirrorStatus[CANoe].Temperature, 20, 30);

if (ret != 0)

TestStepFail("Error occurred!");
```

[TestValidateImplValueInRangeFloat](CAPLfunctionTestValidateImplValueInRangeFloat.md) • [TestValidateImplValueInRangeSInt](CAPLfunctionTestValidateImplValueInRangeSInt.md)
