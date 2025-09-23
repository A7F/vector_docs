# testGetTestUnitName

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`testGetTestUnitName(char testUnitName[], long bufferSize);`

## Description

Returns the name of the test unit. After your call of this function the name will be inside the character array **testUnitName**. The maximum length of the name is the length of the character array. This length will be saved in **bufferSize**.

## Parameters

- **testUnitName**: This character array contains the answer after calling the function.
- **bufferSize**: This parameter saves the length of the character array.

## Example

```c
testcase TCExample()
{
  char name[100];

  testCaseComment("Test Unit:");
  testGetTestUnitName(name, elcount(name));
  testCaseComment(name);
}
```
