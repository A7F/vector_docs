# TestGetValueInput

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
double TestGetValueInput ();
```

## Description

Returns the result of the last successful call of [TestWaitForValueInput](CAPLfunctionTestWaitForValueInput.md).

## Parameters

—

## Return Values

- **= 0.0**  
  Possible error during the last call of `TestWaitForValueInput`. This can mean that the entry could not be correctly converted to a numeric value. This value is also returned if no previous call of `TestWaitForValueInput` occurred. But it is also possible that the user actually entered "0". This can be determined by checking the entry in text form which can be obtained via [TestGetStringInput](CAPLfunctionTestGetStringInput.md). Note that this value can only be the desired entry from the user if it was preceded by a successful call of `TestWaitForValueInput`, i.e. with the return value "1".

- **!= 0.0**  
  Last value queried from the tester with `TestWaitForValueInput`.

## Example

```plaintext
// ask for the test ID and report it in the Write Window
TestWaitForValueInput("Please enter the test ID", 5000);
Write("Test ID = %f", TestGetValueInput());
```
