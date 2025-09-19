[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTPMSetOverTemperature.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostPMSetOverTemperature, mostPMResetOverTemperature

# mostPMSetOverTemperature, mostPMResetOverTemperature

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long mostPMSetOverTemperature ();`
- `long mostPMResetOverTemperature ();`

## Description

`mostPMSetOverTemperature` notifies the PowerMaster in its own device that an over temperature of the device will be simulated. When setting the "over temperature status", the PowerMaster is prompted to not wake-up the ring after it has been shut down, if a MOST signal is detected at the Rx FOT.  
`mostPMResetOverTemperature` signals the PowerMaster that the device has again reached operating temperature.

**Note**  
No message that triggers the shutdown of the ring due to overheating is sent by setting the "overview temperature status" (NetBlock.Shutdown.Result(0x03)). If the "over temperature status" is reset, the ring is not automatically woken up by the PowerMaster. This must be performed by the application, if necessary.

## Parameters

—

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
