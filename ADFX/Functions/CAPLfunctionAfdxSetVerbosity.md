# AfdxSetVerbosity

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxSetVerbosity( long verbosity );
```

## Description

This function sets the verbosity level of the AFDX IL. The default setting is that only error messages are written to the Write Window.

## Parameters

- **verbosity**: verbosity level
  - 0: do not write messages to the Write Window
  - 1: write only error messages (default)
  - 2: write warning and error messages
  - 3: write information, warning and error messages

## Return Values

- **0**: 
- **other value**: [error code](../CAPLfunctionsAFDXErrorCodes.md)

## Example

```plaintext
// do not print AFDX IL messages to Write Window
AfdxSetVerbosity( 0 );
```
