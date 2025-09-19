[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINGetMeasEdgeTimeDiffs.md)

**CAPL Functions** » **LIN** » **linGetMeasEdgeTimeDiffs**

# linGetMeasEdgeTimeDiffs

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
dword linGetMeasEdgeTimeDiffs(dword arrSize, float timeDiffs[]);
```

## Description

This function retrieves the result of a falling edge difference measurement which has been started with [linMeasEdgeTimeDiffs](CAPLfunctionLINMeasEdgeTimeDiffs.md). Note that for each byte measured four time differences will be returned, although all of them might be 0 (if there had been only one falling edge in the measured byte). This means that time differences 0 to 3 contain the values for the first measured byte, time differences 4 to 7 contain the values for the second measured byte, etc.

The results are sorted in ascending order by the indices of the measured bytes.

## Parameters

- **arrSize**: The size of the timeDiffs array.
- **timeDiffs**: The array which will receive the measured time differences. The unit of the measured times is nanoseconds. The first time difference of a byte always relates to the falling edge of the start bit.

## Return Values

Returns the number of time differences copied into the timeDiffs-array.

## Example

See example for [linMeasEdgeTimeDiffs](CAPLfunctionLINMeasEdgeTimeDiffs.md).

[LinMeasEdgeTimeDiffs](CAPLfunctionLINMeasEdgeTimeDiffs.md)

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
