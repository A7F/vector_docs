[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSetGetShutDownFlagUsage.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostSetShutDownFlagUsage, mostGetShutDownFlagUsage

# mostSetShutDownFlagUsage, mostGetShutDownFlagUsage

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

**Note**  
At least OptoLyzer G2 3150o firmware version V1.2 is required.

## Function Syntax

```
long mostSetShutDownFlagUsage(long channel, long mode);
long mostGetShutDownFlagUsage(long channel);
```

## Description

For test purposes the stress network interface controller in the OptoLyzer G2 3150o is able to suppress the shutdown flag for the next node by calling.  
mostSetShutDownFlagUsage with mode 0.

## Parameters

- **channel**: Channel of the connected interface
- **mode**:
  - 0: clear shutdown flag
  - 1: default mode

## Return Values

- **mostSetShutDownFlagUsage**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)
- **mostGetShutDownFlagUsage**:
  - \>=0: See mode parameter
  - \<0: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [OnMostShutdownFlag](../EventProcedures/CAPLfunctionOnMOSTShutdownFlag.md) • [mostWakeup](CAPLfunctionMOSTWakeup.md) • [mostShutDown](CAPLfunctionMOSTShutDown.md) • [mostSetSystemLockFlagUsage](CAPLfunctionMOSTSetGetSystemLockFlagUsage.md)
