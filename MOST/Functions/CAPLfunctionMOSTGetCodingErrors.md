[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetCodingErrors.md)

**CAPL Functions** » **MOST** » **mostGetCodingErrors**

# mostGetCodingErrors

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only available with MOST hardware VN2600/VN2610/VN2640.

## Function Syntax

```
long mostGetCodingErrors (long channel);
```

## Description

Returns the number of coding errors since measurement start or the last time this function was called.

**Note**  
Calling this function resets the counter in the hardware! The total number of coding errors during measurement is displayed in [Bus Statistics Window](../../../CANoeCANalyzer/Windows/BusStatistic/BusStatisticWindowMOST.md).

## Parameters

- **channel**: Channel of the connected interface

## Return Values

- **>= 0**: Number of coding errors.
- **< 0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—
