# Iso11783OPLoadVersion

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long Iso11783OPLoadVersion( dword ecuHandle, char  versionName[] );
```

## Description

The function loads an object pool, which is stored on the Virtual Terminal. A **Load Version** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **versionName**: Designator of the version. For [VT version](CAPLfunctionIso11783OPSetProperty.md) smaller than 5 the name must be 7 characters long. For VT version 5 and higher a name with more than 7 characters is sent with the **Load Extended Version** command.

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPLoadVersion( handle, "POOL01A" );
```
