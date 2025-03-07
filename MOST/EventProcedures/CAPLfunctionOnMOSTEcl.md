[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTEcl.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostEcl

# OnMostEcl

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only available with MOST hardware VN2640.

## Function Syntax

```
OnMostEcl(long eclState);
```

## Description

The event procedure is called when the state of the Electrical Control Line has changed.

Within this event procedure the functions [mostEventChannel](../Functions/CAPLfunctionMOSTEvent.md), [mostEventTime](../Functions/CAPLfunctionMOSTEvent.md) and [mostEventOrigTime](../Functions/CAPLfunctionMOSTEvent.md) can be used to call up supplemental information.

## Parameters

- **eclState**:  
  0: Low  
  1: High

## Return Values

—

## Example

Output of ECL changes with time stamp.

```c
OnMostEcl(long eclState)
{
   write("ECL state at %fs: %d", mostEventTimeNs() / 1.0e9, eclState);
}
```

[mostSetEcl](../Functions/CAPLfunctionMOSTSetGetEcl.md) • [mostSetEclGlitchFilter](../Functions/CAPLfunctionMOSTSetEclGlitchFilter.md) • [mostConfigureEclSequence](../Functions/CAPLfunctionMOSTConfigureEclSequence.md) • [OnMostEclSequence](CAPLfunctionOnMOSTEclSequence.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)