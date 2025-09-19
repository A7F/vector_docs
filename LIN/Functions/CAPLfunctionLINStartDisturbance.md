[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINStartDisturbance.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linStartDisturbance

# linStartDisturbance

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long linStartDisturbance(dword length, dword level);
```

## Description

Starts a disturbance on the bus.

Note that disturbances shorter than 64 bit times:

- Cannot be stopped with [linStopDisturbance()](CAPLfunctionLINStopDisturbance.md).
- May fail, if the hardware simultaneously transmits on this channel.

## Parameters

- **length**: Length of the disturbance in bit times.
  - `-1`: permanent disturbance

- **level**: The level of the disturbance.
  - `0`: dominant disturbance (inverts recessive bits)
  - `1`: recessive disturbance (inverts dominant bits - requires mag-Cab/Piggyback and external power supply)

## Return Values

On success a value unequal to zero, otherwise zero.

## Example

—

[linStopDisturbance](CAPLfunctionLINStopDisturbance.md) • [linSetRespDisturbance](CAPLfunctionLINSetRespDisturbance.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
