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
