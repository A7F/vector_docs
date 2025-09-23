[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/XCP/Functions/CAPLfunctionXCPDisconnect.md)

**CAPL Functions** » **XCP** » **xcpDisconnect**

# xcpDisconnect

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long xcpDisconnect(char ecuQualifier[]);
```

## Callback

```plaintext
void OnXcpDisconnect(char ecuQualifier[]);
```

## Description

Disconnects from a XCP/CCP device. Use [xcpIsConnected](CAPLfunctionXCPIsConnected.md) to be aware of the disconnection. The callback function `OnXcpDisconnect` is called after the ECU acknowledged the disconnect command.

## Parameters

- **ecuQualifier**: Name of the device, configured within the CANoe DE Family [XCP/CCP Window](../../../CANoeCANalyzer/AMDXCP/XCPConfiguration.md).

## Return Values

- **0**: OK
- **-1**: Device with this name is not existing
- **-2**: Operation not allowed – already disconnected

## Example

—

[xcpConnect](CAPLfunctionXCPConnect.md)
