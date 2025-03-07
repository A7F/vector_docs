[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DTI/Functions/CAPLfunctionDtiIsValid.md)

[CAPL Functions](../../CAPLfunctions.md) » [DTI](../CAPLfunctionsDTIOverview.md) » DtiIsValid

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)