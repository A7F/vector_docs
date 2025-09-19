# AfdxGetLastError

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxGetLastError(void);
```

## Description

Returns the error code of the last called Afdx… function.

## Parameters

—

## Return Values

See [error code](../CAPLfunctionsAFDXErrorCodes.md).

## Example

```plaintext
char error[100];
long value;
long packetHandle;

value = AfdxGetTokenInt(packetHandle, "eth", "type");
if (AfdxGetLastError() == 0)
{
  write("Ethernet Type is 0x%x", value);
}
else
{
  AfdxGetLastErrorText(elCount(error), error);
  write("Error: %s", error);
}
```
