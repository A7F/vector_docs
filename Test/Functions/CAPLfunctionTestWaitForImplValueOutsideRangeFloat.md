[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForImplValueOutsideRangeFloat.md)

**CAPL Functions** » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForImplValueOutsideRangeFloat

# TestWaitForImplValueOutsideRangeFloat

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long TestWaitForPhysValueOutsideRangeFloat(valueHandle * value, float aLowLimit, float aHighLimit, dword aTimeout);
```

## Description

Checks the impl encoding of a **valueHandle** value against the condition:

aLowLimit > value or aHighLimit < value

If this condition is already met when this function is called, it returns immediately without waiting.

This function can only be used for **valueHandles** with a floating point data type. It cannot be used for system variables or bus system signals.

## Parameters

- **value**: Value handle of a communication object or distributed object.
- **aLowLimit**: Lower limit of the value.
- **aHighLimit**: Higher limit of the value.
- **aTimeout**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

## Return Values

- **-2**: Value variable is not valid
- **-1**: General error
- **0**: Wait state is exited due to a timeout
- **1**: Wait state is exited due to condition fulfillment

## Example

—

[TestWaitForImplValueOutsideRangeSInt](CAPLfunctionTestWaitForImplValueOutsideRangeSInt.md) • [TestWaitForImplValueOutsideRangeUInt](CAPLfunctionTestWaitForImplValueOutsideRangeUInt.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
