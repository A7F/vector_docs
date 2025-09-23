# Iso11783OPControlAudio

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long Iso11783OPControlAudio( dword ecuHandle, dword activations, dword frequency, dword onTime, dword offTime );
```

## Description

The function plays an acoustic signal on the Virtual Terminal. A **Control Audio Device** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **activations**: Number of tones
- **frequency**: Frequency in [Hz]
- **onTime**: Duration of the tone in [ms]
- **offTime**: Duration of the gaps between the tones

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPControlAudio( handle, 2, 2000, 100, 50 );
```
