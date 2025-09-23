# AREthGetLastError

[Valid for: CANoe DE • CANoe4SW DE](../../../../Shared/FeatureAvailability.md)

## Function Syntax

```plaintext
long AREthGetLastError();
```

## Description

This function can be used to check whether the last called function of AUTOSAR Eth IL has been successfully executed. The call of this function does **not** reset the saved error.

In the event of an error, a detailed error description can be read out using the [AREthGetLastErrorText](CAPLfunctionAREthGetLastErrorText.md) function.

## Parameters

—

## Return Values

- **0**: The last called function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

```plaintext
long retVal;

// resume sending messages
AREthILControlResume();

// check if last function was executed correct
if((retVal = AREthGetLastError()) != 0)
{
  write("AUTOSAR Eth IL error occurred: Error code: %d", retVal);
} // if
```

[See Also](javascript:void(0);)
