[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTApGetFBlockID.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostApGetFBlockID

# mostApGetFBlockID

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
long mostApGetFBlockID();
```

## Description

`mostApGetFBlockID` returns the FBlockID of the CAPL node. The function block must be assigned to the CAPL program exclusively via [mostApRegister(fblockID, instIDDefault)](CAPLfunctionMOSTApRegister.md) or the [database](../../../CANoeCANalyzer/MOST/MOSTSimulationDatabase.md).

## Parameters

—

## Return Values

- `>0`: Valid FBlockID
- `<0`: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—
