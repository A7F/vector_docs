# testGetCurrentTestCaseID

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`testGetCurrentTestCaseID(char testCaseID[], long bufferSize);`

## Description

Returns the ID of the current test case. After the call of this function the ID will be inside the character array **testCaseID**. The maximum length of the ID is the length of the character array. This length will be saved in **bufferSize**.

## Parameters

- **testCaseID**: This character array contains the answer after calling the function.
- **bufferSize**: This parameter saves the length of the character array.

## Return Values

ID of the current test case.

## Example

```c
testcase TCExample()
{
  char id[100];
  testCaseComment("Test Case:");
  testGetCurrentTestCaseID(id, elcount(title));
  testCasecomment(id);
}
```
