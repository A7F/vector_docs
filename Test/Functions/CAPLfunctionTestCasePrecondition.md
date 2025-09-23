[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestCasePrecondition.md)

**CAPL Functions** » **Test Feature Set** » **testCasePrecondition**

# testCasePrecondition

**Valid for**: CANoe DE • CANoe4SW DE • CANoe:lite DE • CANoe4SW:lite DE

## Function Syntax

```
testCasePrecondition (caplFunction);
```

## Description

Sets a precondition to be fulfilled. This must be passed as a lambda function with a dword as return value. The precondition must not set a verdict and the function must be called at the beginning of the test case.

## Parameters

- **caplFunction**: CAPL function to execute the precondition. The return value type of the function must be dword and returns a 0 for the positive case or a 1 for the negative case.

## Return Values

- **0**: An error occurred during the execution of the precondition.
- **1**: Precondition was executed successfully.

## Example

```plaintext
export testcase TestCasePreconditionIsFalse()
{
  testCasePrecondition(delegate dword(){
    testCaseComment("This is called inside some capl precondtion!");
    return 1;
  });

  testCaseComment("This is called after some precondition!");
}

export testcase TestCasePreconditionIsTrue()
{
  testCasePrecondition(delegate dword(){
    testCaseComment("This is called inside some capl precondtion!");
    return 0;
  });

  testCaseComment("This is called after some precondition!");
}
```
