[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestValidatePhysValueInRangeSInt.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestValidatePhysValueInRangeSInt

# TestValidatePhysValueInRangeSInt

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long TestValidatePhysValueInRangeSInt(char aTestStep[], valueHandle * value, int64 aLowLimit, int64 aHighLimit);
```

## Description

Checks the phys encoding of a **valueHandle** value against the condition. This function can only be used for **valueHandles** with a signed integer data type. It cannot be used for system variables or bus system signals.

aLowLimit <= Value <= aHighLimit

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
ret = testValidatePhysValueInRangeSInt(MirrorStatus[CANoe].Temperature, 20.0, 30.0);

if (ret != 0)

TestStepFail("Error occurred!");
```

[TestValidatePhysValueInRangeFloat](CAPLfunctionTestValidatePhysValueInRangeFloat.md) • [TestValidatePhysValueInRangeUInt](CAPLfunctionTestValidatePhysValueInRangeUInt.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
