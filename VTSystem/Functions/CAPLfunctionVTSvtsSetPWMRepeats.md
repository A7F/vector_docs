[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSvtsSetPWMRepeats.md)

**CAPL Functions** » **VT System** » **vtsSetPWMRepeats**

# vtsSetPWMRepeats

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe:lite DE

## Function Syntax

```plaintext
long vtsSetPWMRepeats (char Target[], dword numOfRepeats);
```

## Description

This function sets the number of stimulated PWM periods after the start of stimulation. If the number of cycles output is not limited, **numOfRepeats** must be set to **0**.

## Parameters

- **Target**: Name of the system variable/namespace that will be affected by this function call.
- **numOfRepeats**: Number of PWM periods to be stimulated.  
  Valid values: 0…65535.

## Return Values

- **0**: Successful call
- **-1**: Error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.
- **-3**: The specified number of repeats is not valid.

## Example

See example [vtsSetStimulationMode](CAPLfunctionVTSvtsSetStimulationMode.md)

[SetPWMRepeats](CAPLfunctionVTSSetPWMRepeats.md)
