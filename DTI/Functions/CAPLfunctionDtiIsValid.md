# DtiIsValid

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

—

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
byte DtiPipe::IsValid();
```

## Description

The function returns `true` if the specified pipe is valid and ready to be used.

If you are using the function syntax, check the value returned by [DtiOpen](CAPLfunctionDtiOpen.md). If the value is equal to `0`, the pipe is invalid.

## Parameters

—

## Return Values

- **0**: False, i.e. the pipe is invalid.
- **1**: True, i.e. the pipe is valid.

## Example

```c
void openPipe()
{
  pipe = DtiPipe::Open(port);

  if (!pipe.IsValid())
    write("Failed to open the pipe!");
}
```
