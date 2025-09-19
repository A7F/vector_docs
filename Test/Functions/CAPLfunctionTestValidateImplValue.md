[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestValidateImplValue.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestValidateImplValue

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

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
