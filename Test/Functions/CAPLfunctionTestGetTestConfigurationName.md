# testGetTestConfigurationName

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
testGetTestConfigurationName(char testConfigurationName[], long bufferSize);
```

## Description

Returns the name of the test configuration. After your call of this function the name will be inside the character array **testConfigurationName**. The maximum length of the name is the length of the character array. This length will be saved in **bufferSize**.

## Parameters

- **testConfigurationName**: This character array contains the answer after calling the function.
- **bufferSize**: This parameter saves the length of the character array.

## Example

```c
testcase TCExample()
{
  char name[100];

  testCaseComment("Test Configuration:");
  testGetTestConfigurationName(name, elcount(name));
  testCaseComment(name);
}
```
