[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTNwmFiEnableRingScan.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostNwmFiEnableRingScan

# mostNwmFiEnableRingScan

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostNwmFiEnableRingScan(long mode);
```

## Description

Can be called to change the ring scan behavior of CANoe’s NetworkMaster. The function is available for CAPL programs assigned to the NetworkMaster block in the Simulation Setup.

## Parameters

- **mode**  
  0: disable network scan  
  1: enable normal network scan behavior  
  2: terminate currently running network scan  
  3: trigger network scan once

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[OnMostFiAmsPreSend](../EventProcedures/CAPLfunctionOnMOSTFiAmsPreSend.md) • [OnMostFiAmsPreReceive](../EventProcedures/CAPLfunctionOnMOSTFiAmsPreReceive.md) • [mostNwmFiSetConfigState](CAPLfunctionMOSTNwmFiSetConfigState.md)
