# ChkConfig_Init

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long ChkConfig_Init (char aRole[]);` // form 1: deprecated
- `long ChkConfig_Init ();` // form 2

## Description

Initializes TSL to be used subsequently.

If the function is used, then it is recommended to perform the initialization once during **preStart** section of the CAPL program.

The tester role (form 1) has no longer an effect.

## Parameters

- **aRole**: Allowed value range: **developer**, **user**

## Return Values

- **-1**: error
- **0**: successful

## Example

```c
// test is executed in the role of a developer
on preStart
{
   ChkConfig_Init();
}
```
