[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTApGetInstID.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostApGetInstID

# mostApGetInstID

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostApGetInstID();
```

## Description

Returns the InstID of the CAPL node. The function block must be assigned to the CAPL program exclusively via [mostApRegister](CAPLfunctionMOSTApRegister.md) (fblockID, instIDDefault) or the [database](../../../CANoeCANalyzer/MOST/MOSTSimulationDatabase.md).

## Parameters

—

## Return Values

- **\> 0**: Valid InstID
- **\< 0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[OnMostApInstID](../EventProcedures/CAPLfunctionOnMOSTApInstID.md)
