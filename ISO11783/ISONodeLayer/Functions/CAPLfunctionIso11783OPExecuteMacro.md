# Iso11783OPExecuteMacro

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPExecuteMacro( dword ecuHandle, dword macroID );
```

## Description

The function executes a macro object. An **Execute Macro** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **macroID**: Object ID of a macro object

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPExecuteMacro( handle, 1200 );
```
