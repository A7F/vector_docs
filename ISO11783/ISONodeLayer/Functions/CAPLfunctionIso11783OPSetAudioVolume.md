# Iso11783OPSetAudioVolume

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPSetAudioVolume( dword ecuHandle, dword volume );
```

## Description

The function sets the audio volume of the Virtual Terminal. A **Set Audio Volume** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **volume**: Volume, 0..100%

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPSetAudioVolume( handle, 100 );
```
