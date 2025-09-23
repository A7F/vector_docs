[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTAsRgGetSize.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostAsRgGetSize

# mostAsRgGetSize

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostAsRgGetSize(long regsel);
```

## Description

Determines the number of entries in the registry.

## Parameters

- **regsel**  
  1: Local FBlockList  
  2: Bus registry

## Return Values

- **\>\= 0**  
  Number
- **\\\< 0**  
  See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostAsRgGetRxTxLog](CAPLfunctionMOSTAsRgGetRxTxLog.md) • [mostAsRgGetFBlockID](CAPLfunctionMOSTAsRgGetFBlockID.md) • [mostAsRgGetInstID](CAPLfunctionMOSTAsRgGetInstID.md) • [OnMostAsRegistry](../EventProcedures/CAPLfunctionOnMOSTAsRegistry.md)
