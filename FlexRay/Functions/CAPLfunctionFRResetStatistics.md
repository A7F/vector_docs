[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Functions/CAPLfunctionFRResetStatistics.md)

**CAPL Functions** » **FlexRay** » **frResetStatistics**

# frResetStatistics

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `void frResetStatistics();` // form 1
- `void frResetStatistics(long channel);` // form 2

## Description

Resets FlexRay cluster statistics. Both A and B channels are concerned.

**Note**

There are two ways to call this function:

- Calling this function **without the explicit channel** is only possible from a CAPL program defined in the Simulation/Test Setup. The statistics for the channel determined by the current [bus context](../../Other/Functions/CAPLfunctionGetBusContext.md) are reset.
- The function **with the explicit channel** can be called from a CAPL program defined in Measurement Setup only.

## Parameters

- **channel**: FlexRay cluster number (1-based)

## Return Values

—

## Example

```c
on key 'r' 
{ 
   // reset statistics for A and B channels in cluster 1
   frResetStatistics(1);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)