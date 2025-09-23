[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSetEclGlitchFilter.md)

**CAPL Functions** » **MOST** » **mostSetEclGlitchFilter**

# mostSetEclGlitchFilter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only available with MOST hardware VN2640.

## Function Syntax

```
long mostSetEclGlitchFilter (long channel, long durationus);
```

## Description

Configures the timing of the glitch filter for the ECL. For pulses which are shorter than the given time durations, the callback `<OnMostEcl>` will not be called, nor will those pulses appear in a Trace Window.

## Parameters

- **channel**: Channel of the connected interface.
- **durationus**: Minimum duration of a pulse in µs required to generate an event which calls `<OnMostECL>`. The value ranges from 50 µs to 50 ms (Default: 1 ms).

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

—

[mostSetEclTermination](CAPLfunctionMOSTSetGetEclTermination.md) • [mostWakeup](CAPLfunctionMOSTWakeup.md) • [OnMostEcl](../EventProcedures/CAPLfunctionOnMOSTEcl.md)
