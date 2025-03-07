[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANstress/Functions/CAPLfunctionCANstressCreateServerDeviceAlias.md)

[CAPL Functions](../../CAPLfunctions.md) » [CANstresss](../CAPLfunctionsCANstressOverview.md) » CANstressCreateServer(DeviceAlias)

# CANstressCreateServer(DeviceAlias)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

**Note**  
This function must be called before all other CANstress CAPL functions!

## Function Syntax

```
long CANstressCreateServer (char[] deviceAlias);
```

## Description

Starts the CANstress software and establishes a connection to this COM server via the COM interface. The COM server generated only establishes a connection to the CANstress device defined in **deviceAlias**. Connected CANstress devices are mapped to an alias using the `canstress.INI` file. You will find this file in the CANstress software’s installation directory. If the call is successful, the device defined in **deviceAlias** will be set as the current device.

## Parameters

—

## Return Values

- **> 0**  
  If successful.  
  If the attempt to establish a connection to a COM server is successful, a handle required for the **CANstressSetDevice** function will be returned for the device. This handle will be a value greater than **0**.

- **-1**  
  In case of error.  
  If the call is not successful (because the CANstress software has not been registered as a COM server, for example), the value **-1** will be returned. The result of the test currently in progress will also be set to **failed**.

## Example

—

[CANstressCreateServer()](CAPLfunctionCANstressCreateServer.md)  •  [CANstressCreateServer(Device number)](CAPLfunctionCANstressCreateServerDeviceNr.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)