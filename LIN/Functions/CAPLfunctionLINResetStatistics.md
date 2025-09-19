[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINResetStatistics.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linResetStatistics

# linResetStatistics

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `void linResetStatistics(); // form 1`
- `void linResetStatistics(long channel); // form 2`

## Description

Resets LIN channel statistics.

**Note**

There are two ways to call this function:

- Calling this function **without the explicit channel** is only possible from a CAPL program defined in the Simulation/Test Setup. The statistics for the channel determined by the current [bus context](../../Other/Functions/CAPLfunctionGetBusContext.md) are reset.
- The function **with the explicit channel** can be called from a CAPL program defined in Measurement Setup only.

## Parameters

- **channel**: LIN channel (1-based)

## Return Values

—

## Example

```c
on key 'r' 
{ 
   // reset statistics on LIN 1
   linResetStatistics(1);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
