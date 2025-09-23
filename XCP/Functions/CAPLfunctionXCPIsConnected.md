[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/XCP/Functions/CAPLfunctionXCPIsConnected.md)

[CAPL Functions](../../CAPLfunctions.md) » [XCP](../CAPLfunctionsXCPOverview.md) » xcpIsConnected

# xcpIsConnected

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long xcpIsConnected (char ecuQualifier[]);
```

## Description

Returns the current connection status of a XCP/CCP device.

## Parameters

- **ecuQualifier**: Name of the device, configured within the CANoe DE Family [XCP/CCP Window](../../../CANoeCANalyzer/AMDXCP/XCPConfiguration.md).

## Return Values

- **0**: Not connected
- **1**: Connected
- **-1**: A device with this name does not exist

## Example

—

[xcpConnect](CAPLfunctionXCPConnect.md) • [xcpDisconnect](CAPLfunctionXCPDisconnect.md)
