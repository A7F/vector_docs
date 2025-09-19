[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/XCP/Functions/CAPLfunctionXCPConnect.md)

[CAPL Functions](../../CAPLfunctions.md) » [XCP](../CAPLfunctionsXCPOverview.md) » xcpConnect

# xcpConnect

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long xcpConnect (char ecuQualifier[]);
```

## Callback

```
void OnXcpConnect(char ecuQualifier[]);
```

## Description

Establishes a connection to the XCP/CCP device and starts the configured DAQ measurement.

If the connection is successfully depends on the response of the device.

Use [xcpIsConnected](CAPLfunctionXCPIsConnected.md) to be aware of the connection.

After establishing the connection and before start of the DAQ measurement the callback function `OnXcpConnect` is called.

## Parameters

- **ecuQualifier**: Name of the device, configured within the CANoe DE Family [XCP/CCP Window](../../../CANoeCANalyzer/AMDXCP/XCPConfiguration.md).

## Return Values

- **0**: OK
- **-1**: Device with this name is not existing
- **-2**: Operation not allowed – already connected

## Example

```c
testcase TC_ConnectToECU ()
{
  xcpConnect("ECU");
  ....
}

// Callback function:
void OnXcpConnect (char ecuQualifier[])
{
  // Set calibration page to RAM
  xcpSetCalPage(ecuQualifier, 0x83, 0, 0);
}
```

[xcpDisconnect](CAPLfunctionXCPDisconnect.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
