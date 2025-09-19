[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetRespDisturbance.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetRespDisturbance

# linSetRespDisturbance

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long linSetRespDisturbance (long frameId, long lengthInBits, 
 long level, long offsetInSixteenthBits);
```

## Description

Activates a disturbance in the response space of the specified LIN frame. A normal response by a simulated slave will be deactivated as long as the disturbance is active.

**Note:** The disturbance starts with the next occurrence of the specified frame. To stop the disturbance the functions [linResetRespDisturbance()](CAPLfunctionLINResetRespDisturbance.md) shall be used.

## Parameters

- **frameId**: LIN frame identifier in the range 0 .. 63.
- **lengthInBits**: The duration of the disturbance [in bit times].
- **level**: The level of the disturbance.
  - 0: dominant disturbance (inverts recessive bits)
  - 1: recessive disturbance (inverts dominant bits - requires mag-Cab/Piggyback and external power supply)
- **offsetInSixteenthBits**: The offset [in 1/16th bits] of the disturbance relative to the end of the header, i.e., to the PID byte.

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

On pressing 'c' key start corrupting the response space and the first databyte of the response for LIN frame **Motor1State_Cycl**.

```plaintext
on key 'c'
{
    linFrame Motor1State_Cycl mMotor1State_Cycl;
    if (0!=linSetRespDisturbance (mMotor1State_Cycl.id, 1, 0, 20))
    {
        // for the next the first bit of the response space 
        // or of the first databyte
        // (if the response space is zero) is inverted from recessive to dominant
    }
}
```

[linResetRespDisturbance](CAPLfunctionLINResetRespDisturbance.md) • [linStartDisturbance](CAPLfunctionLINStartDisturbance.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
