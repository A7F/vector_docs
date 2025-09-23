# TestWaitForPhysValueInRangeUInt

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```c
long TestWaitForPhysValueInRangeUInt(valueHandle * value, qword aLowLimit, qword aHighLimit, dword aTimeout);
```

## Description

Checks the phys encoding of a **valueHandle** value against the condition:

aLowLimit \<= Value \<= aHighLimit

If this condition is already met when this function is called, it returns immediately without waiting.

This function can only be used for **valueHandles** with an unsigned integer data type. It cannot be used for system variables or bus system signals.

## Parameters

- **value**: Value handle of a communication object or distributed object.
- **aLowLimit**: Lower limit of the value.
- **aHighLimit**: Higher limit of the value.
- **aTimeout**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

## Return Values

- **-2**: Type of the valueHandle is not valid
- **-1**: General error
- **0**: Correct functionality
- **1**: Wait state is exited due to condition fulfillment

## Example

—

[TestWaitForPhysValueInRangeFloat](CAPLfunctionTestWaitForPhysValueInRangeFloat.md) • [TestWaitForPhysValueInRangeSInt](CAPLfunctionTestWaitForPhysValueInRangeSInt.md)
