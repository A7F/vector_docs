[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetOSEnvironmentVariableValue.md)

# GetOSEnvironmentVariableValue

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » GetOSEnvironmentVariableValue

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long GetOSEnvironmentVariableValue(char variableName[], char buffer[]);
```

## Description

Gets the value of an operating system environment variable (i.e. "PATH" or "USERNAME"). Note that these are not the CANoe DE product system variables.

## Parameters

- **variableName**: The name of the environment variable to be queried.
- **buffer**: Space for the return value of the environment variable. If it does not contain sufficient space for the result, it will remain unchanged and the function will return 1.

## Return Values

0 if the function completed successfully, else unequal 0. Possible reasons for failure are that the environment variable does not exist or that the buffer is not large enough to contain the result.

## Example

Get the current username on windows:

```c
char buffer[50];
GetOSEnvironmentVariableValue("USERNAME", buffer);
write("Username: %s", buffer);
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
