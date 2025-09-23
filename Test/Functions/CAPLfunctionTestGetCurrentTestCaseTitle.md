[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestGetCurrentTestCaseTitle.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » testGetCurrentTestCaseTitle

# testGetCurrentTestCaseTitle

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`testGetCurrentTestCaseTitle(char testCaseTitle[], long bufferSize);`

## Description

Returns the name of the current test case. After your call of this function the name will be inside the character array **testCaseTitle**. The maximum length of the name is the length of the character array. This length will be saved in **bufferSize**.

## Parameters

- **testCaseTitle**: This character array contains the answer after calling the function.
- **bufferSize**: This parameter saves the length of the character array.

## Example

```c
testcase TCExample()
{
  char title[100];

  testCaseComment("Test Case:");
  testGetCurrentTestCaseTitle(title, elcount(title));
  testCasecomment(title);
}
```
