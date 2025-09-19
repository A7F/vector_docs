[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForPhysValueOutsideRangeUInt.md)

## TestWaitForPhysValueOutsideRangeUInt

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForPhysValueOutsideRangeUInt

### Function Syntax

```plaintext
long TestWaitForPhysValueOutsideRangeUInt(valueHandle * value, qword aLowLimit, qword aHighLimit, dword aTimeout);
```

### Description

Checks the phys encoding of a **valueHandle** value against the condition:

`aLowLimit > value or aHighLimit < value`

If this condition is already met when this function is called, it returns immediately without waiting.

This function can only be used for **valueHandles** with an unsigned integer data type. It cannot be used for system variables or bus system signals.

### Parameters

- **value**: Value handle of a communication object or distributed object.
- **aLowLimit**: Lower limit of the value.
- **aHighLimit**: Higher limit of the value.
- **aTimeout**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

### Return Values

- **-2**: Value variable is not valid
- **-1**: General error
- **0**: Wait state is exited due to a timeout
- **1**: Wait state is exited due to condition fulfillment

### Example

—

[TestWaitForPhysValueOutsideRangeFloat](CAPLfunctionTestWaitForPhysValueOutsideRangeFloat.md) • [TestWaitForPhysValueOutsideRangeSInt](CAPLfunctionTestWaitForPhysValueOutsideRangeSInt.md)

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
