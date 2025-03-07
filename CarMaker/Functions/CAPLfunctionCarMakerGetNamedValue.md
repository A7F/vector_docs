[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CarMaker/Functions/CAPLfunctionCarMakerGetNamedValue.md)

[CAPL Functions](../../CAPLfunctions.md) » [CarMaker Interface](../CAPLfunctionsCarMakerOverview.md) » CarMaker_GetNamedValue

# CarMaker_GetNamedValue

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE •

## Function Syntax

```plaintext
long CarMaker_GetNamedValue(char name[], char buffer[], long bufferSize);
```

## Description

Copies the current value with the given name into the buffer provided by the caller. If the size of the buffer is insufficient the value will be truncated and zero terminated.

## Parameters

- **name**: Name of the named value.
- **buffer**: Output buffer for the current value.
- **bufferSize**: Size of the output buffer.

## Return Values

[APO return code](../CAPLfunctionsCarMakerReturnCodes.md)

## Example

```c
void printStatus()
{
  char statusBuf[256]= "";
  gErrorState = CarMaker_GetNamedValue("Status", statusBuf, elcount(statusBuf));
  write("Status: \"%s\"", statusBuf);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)