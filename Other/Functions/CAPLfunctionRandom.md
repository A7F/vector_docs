[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionRandom.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » random

# random

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
dword random(dword num);
```

## Description

Calculates a random number between 0 and num-1.

## Parameters

Determines the interval.

## Return Values

Random number between 0 and num-1.

## Example

```plaintext
dword x;
// generate random number in the interval [0;99]
x = random(100);
```

[runError](CAPLfunctionRunError.md)
