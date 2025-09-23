[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTApUnregisterEx.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostApUnregisterEx

# mostApUnregisterEx

**Valid for**: CANoe DE

## Function Syntax

```plaintext
long mostApUnregisterEx(long fblockID, long instID);
```

## Description

Removes the function block with functional address {fblockID, instID} from the [Local FBlockList](../../../CANoeCANalyzer/MOST/MOSTSimulationApplicationSocketLocalFBlockList.md). It should be noted that CAPL nodes may only remove those function blocks you have previously registered with [mostApRegisterEx](CAPLfunctionMOSTApRegisterEx.md).

In network status 'ConfigOk' the device's NetBlock reports the new Local FBlockList to the NetworkMaster.

## Parameters

- **fblockID**: Function block identifier to be logged out.
- **instID**: Instance identifier to be logged out.

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—
