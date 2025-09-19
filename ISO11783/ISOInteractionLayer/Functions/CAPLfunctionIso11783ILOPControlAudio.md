[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPControlAudio.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_OPControlAudio

# Iso11783IL_OPControlAudio

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPControlAudio( dword activations, dword frequency, dword onTime, dword offTime ); // form 1
long Iso11783IL_OPControlAudio( dbNode implement, dword activations, dword frequency, dword onTime, dword offTime ); // form 2
```

## Description

The function plays an acoustic signal on the Virtual Terminal. A **Control Audio Device** command is sent to the Virtual Terminal.

## Parameters

- **activations**: number of tones
- **frequency**: frequency in [Hz]
- **onTime**: duration of the tone in [ms]
- **offTime**: duration of the gaps between the tones
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: function has been executed successfully
- **< 0**: an error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_OPControlAudio( 2, 2000, 100, 50 );
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
