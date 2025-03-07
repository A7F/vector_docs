[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xSetVerbosity.md)

**CAPL Functions** » **Car2x** » **C2xSetVerbosity**

# C2xSetVerbosity

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

```plaintext
long C2xSetVerbosity( long verbosity );
```

## Description

This function sets the verbosity level of the Car2x IL. The default setting is that only error messages are written to the Write Window of your CANoe DE product.

## Parameters

- **verbosity**: Verbosity level
  - 0: do not write messages to the Write Window
  - 1: write only error messages (default)
  - 2: write warning and error messages
  - 3: write information, warning and error messages

## Return Values

- **0**: Success
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

```plaintext
// do not print Car2x IL messages to Write Window
C2xSetVerbosity( 0 );
```

[See Also](javascript:void(0);)