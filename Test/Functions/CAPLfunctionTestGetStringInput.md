# TestGetStringInput

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long TestGetStringInput (char aAnswer[], dword aAnswerLen);
```

## Description

Returns the result of the last successful call of [TestWaitForStringInput](CAPLfunctionTestWaitForStringInput.md).

## Parameters

- **aAnswer**: Variable in which the entry of the user must be accepted.
- **aAnswerLen**: Length of variable which has to accept the user entry.

## Return Values

- **< 0**: General error, e.g. by calling outside of a test sequence or through no previously performed call of [TestWaitForStringInput](CAPLfunctionTestWaitForStringInput.md).
- **1**: Data were successfully queried.

## Example

```c
// ask for the users name and report it in the Write Window
char answer[100];
if (1 == TestWaitForStringInput("Please enter your name", 5000))
{
    TestGetStringInput(answer, 100);
    Write("name = %s", answer);
}
```
