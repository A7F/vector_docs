[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTEclSequence.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostEclSequence

# OnMostEclSequence

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only available with MOST hardware VN2640.

## Function Syntax

`OnMostEclSequence(long state);`

## Description

The event procedure is called before the beginning and after the end of a sequence on the Electrical Control Line.

Within this event procedure the functions [mostEventChannel](../Functions/CAPLfunctionMOSTEvent.md), [mostEventTime](../Functions/CAPLfunctionMOSTEvent.md) and [mostEventOrigTime](../Functions/CAPLfunctionMOSTEvent.md) can be used to call up supplemental information.

## Parameters

- **state**  
  0: ECL sequence is stopped  
  1: ECL sequence is started

## Return Values

—

## Example

Output of ECL sequence changes with time stamp.

```c
OnMostEclSequence(long state)
{
    if(state == 0)
        write("ECL sequence stopped at %fs", MostEventTimeNs() / 1.0e9);
    else
        write("ECL sequence started at %fs", MostEventTimeNs() / 1.0e9);
}
```

[mostSetEcl](../Functions/CAPLfunctionMOSTSetGetEcl.md) • [mostSetEclGlitchFilter](../Functions/CAPLfunctionMOSTSetEclGlitchFilter.md) • [mostConfigureEclSequence](../Functions/CAPLfunctionMOSTConfigureEclSequence.md) • [mostGenerateEclSequence](../Functions/CAPLfunctionMOSTGenerateEclSequence.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
